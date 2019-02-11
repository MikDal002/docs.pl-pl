---
title: Podstawowe pojęcia do trenowania modelu w ML.NET
description: W tym artykule opisano podstawowe pojęcia dotyczące *trenowania modelu* w ML.NET. Nie wszystkie pojęcia są istotne dla prostych scenariuszy *prognozowania z wykorzystaniem istniejącego modelu*.
ms.date: 11/06/2018
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: cff833b45583bc752bb42616820a95ca6c5c6b12
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155439"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a>Podstawowe pojęcia do trenowania modelu w ML.NET

W tym artykule opisano podstawowe pojęcia dotyczące *trenowania modelu* w ML.NET. 
Nie wszystkie pojęcia są istotne dla prostych scenariuszy *prognozowania z wykorzystaniem istniejącego modelu*.

## <a name="model-training-concepts"></a>Pojęcia dotyczące szkolenia modelu

W tym dokumencie opisano następujące pojęcia związane z szkolenia modelu w ML.NET:

- [*Dane* ](#data) reprezentowane przez interfejs `IDataView`.
  - W ML.NET dane są podobne do widoku SQL: Są wywoływane w momencie zapotrzebowania na nie, niemodyfikowalne, różnorodne oraz usystematyzowane. 
  - Doskonałym materiałem na temat intefejsu danych są [zasady projektowania IDataView](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).
- [*Transformator* ](#transformer) reprezentowany przez interfejs `ITransformer`.
  - Transformator jest komponentem, który pobiera dane, przekształca je i zwraca nowe dane.
  - Dla przykładu możesz myśleć, że model uczenia maszynowego jest transformatorem: przyjmuje pewne właściwości i zwraca prognozy.
  - Inny przykład: tokenizator tekstu przyjmuje pojedynczy wiersz tekstu a zwraca wektora z pojedynczymi wyrazami wyodrębnionymi z tekstu.
- [*Czytnik danych* ](#data-reader) reprezentowany przez interfejs `IDataReader<T>`.
  - Czytnik danych jest komponentem ML.NET do tworzenia danych. Bierze obiekt typu `T` i zwraca dane z tego obiektu. 
  - Na przykład *TextLoader* to `IDataReader<FileSource>`. Pobiera zawartość pliku i tworzy dane. 
- [*Szacownik (Estymator)* ](#estimator) reprezentowany przez interfejs `IEstimator<T>`.
  - Jest to obiekt, który uczy się na podstawie danych. Wynikiem uczenia się jest *transformator*.
  - Możesz traktować *algorytm* uczenia maszynowego jako narzędzie do szacowania, które uczy się na danych i *model* uczenia maszynowego.
- [*Funkcja prognozująca* ](#prediction-function) reprezentowana przez klasę `PredictionFunction<TSrc, TDst>`.
  - Funkcja prognozująca może być traktowana jako maszyna, która potrafi zastosować *transformator* do pojedynczego wiersza.

## <a name="data"></a>Dane

W strukturze ML.NET dane są podobne do widoku SQL: Jest opóźnieniem ocenianą, informatycznych cursorable heterogenicznych, zestawu danych.

- Ma ona *schematu* (wystąpienie `ISchema` interfejsu) zawierający informacje dotyczące kolumny widoku danych.
  - Każda kolumna ma *nazwa*, *typu*i dowolnego zestawu *metadanych* skojarzonych z nim.
  - W kolumnie *metadanych* zawiera informacje, takie jak miejsce nazwy kolumny wektora i podobne. Metadane, sama jest reprezentowany jako innego jednowierszowym *danych* unikatowy dla każdej kolumny.
  - Widok danych to źródło *kursory*. Reakcji kursorów SQL: Kursor jest obiekt, który iteruje po danych jeden wiersz w czasie i przedstawia dostępne dane.
  - Oczywiście dane mogą mieć dowolną liczbę aktywnych kursorów nad nią zgodnie z potrzebami. Ponieważ dane są niezmienne, kursory są naprawdę niezależne.
  - Kursory zwykle dostęp tylko podzbiór kolumn: W celu zwiększenia wydajności w strukturze ML.NET oblicza tylko wartości kolumn, które są wymagane przez kursor.

## <a name="transformer"></a>Transformer

Transformer jest składnikiem, który pobiera dane, niektóre pracować nad nim i zwraca nowy przekształconych danych.

Większość transformatory w strukturze ML.NET mają tendencję do działania na jednym *kolumny wejściowej* w czasie i wygenerować *kolumnę wyjściową*. Na przykład `new HashTransformer("foo", "bar")` przyjmuje wartości z kolumny "foo" hash je i umieść je w kolumnie "bar". 

Jest również typowe, że nazwy kolumn wejściowych i wyjściowych są takie same. W tym przypadku starego kolumny jest zastępowany nowym. Na przykład `new HashTransformer("foo")` pobiera wartości z kolumny "foo", skrót je i umieść je z powrotem do "foo". 

Wszelkie transformer, oczywiście, tworzy nowe dane widoku, kiedy `Transform` jest wywoływana. Należy pamiętać, że widoki danych są niezmienne.

Innym ważnym zagadnieniem jest fakt, że ponieważ opóźnieniem szacowania danych *transformatory są powolne zbyt*. Zasadniczo po wywołaniu

```csharp
var newData = transformer.Transform(oldData)
```

nie rzeczywiste obliczenia się nie dzieje. Tylko wtedy, gdy otrzymasz kursora z `newData` i rozpoczęcie używania wartość `newData` wywołania `transformer` logiki przekształcania (a nawet tego tylko wtedy, gdy `transformer` jest zagrożona niezbędnych do wyprodukowania żądanej kolumny).

### <a name="transformer-chains"></a>Łańcuchy transformatora

Jest przydatne właściwość transformatora *można frazę kolejność stosowania transformatorów transformatora jako kolejny*:

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

Ta właściwość jest często używana w strukturze ML.NET: zazwyczaj uczonego modelu w strukturze ML.NET jest łańcuch transformatory, który jest na wszystkich intents i purposes, *transformatora*. 

## <a name="data-reader"></a>Czytnik danych

Czytnik danych jest składnikiem strukturze ML.NET, aby utworzyć dane: Trwa wystąpienie `T` i zwraca dane z niej.

Interesujące właściwości, należy pamiętać, jest, czy można utworzyć czytnika danych, dołączając transformatora do istniejących czytnik danych. W ten sposób może mieć czytnik z działaniem przekształcania wbudowanymi:

```c#
var newReader = reader.Append(transformer1).Append(transformer2)
```

Inny podobieństwa do transformatory jest fakt, że ponieważ opóźnieniem szacowania danych *czytniki są powolne*: nie (lub minimalny) rzeczywiste odczytu się dzieje, gdy wywołujesz `dataReader.Read()`: tylko gdy kursor jest wymagane w danych wynikowych jest Czytnik rozpocząć pracę.

## <a name="estimator"></a>Narzędzie do szacowania

*Narzędzie do szacowania* jest obiektem, który uzyskuje informacje o dane. Jest wynikiem szkoleniowe *transformatora*.

W strukturze ML.NET, ta właściwość umożliwia tworzenie potoków uczenia, połączonych ze sobą różnych aplikacjom:

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = new CopyColumnsEstimator(mlContext, "FareAmount", "Label")
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "VendorId"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "RateCode"))
.Append(mlContextml.Transforms.Categorical.OneHotEncoding(mlContext, "PaymentType"))
.Append(new ColumnConcatenatingEstimator(mlContext, "Features", "VendorId", "RateCode", "PassengerCount", "TripTime", "TripDistance", "PaymentType"))
.Append(mlContext.Regression.Trainers.FastTree("Label", "Features"));

var model = pipeline.Fit(dataView);
```

Co ważne właściwości aplikacjom jest fakt, że *aplikacjom to eager, nie z opóźnieniem*: każde wywołanie `Fit` powoduje uczenia się i tak się stanie, co jest potencjalnie czasochłonna operacja.

## <a name="prediction-function"></a>Funkcja prognozowania

Funkcja prognozowania może być traktowany jako maszynie, która dotyczy transformatora jeden wiersz.

Po pobraniu modelu ( *transformatora* uczony albo za pośrednictwem `Fit()`, lub załadowany z innej lokalizacji), służy do tworzyć prognozy przy użyciu normalnych wywołania `model.Transform(data)`. Jednak jeśli używasz tego modelu w scenariuszu rzeczywistych często nie masz wiele przykładów do prognozowania na. Zamiast tego ma przykładem w czasie i musisz prognozowania aktualnych na nich od razu.

Oczywiście może to zmniejszyć do prognozowania usługi batch:

- Utwórz widok danych przy użyciu dokładnie jeden wiersz.
- Wywołaj `model.Transform(data)` do wyświetlania warunków prognozowanych danych.
- Pobieranie kursora nad dane wynikowe.
- Przejdź jeden krok kursora, aby przejść do wiersza pierwszą (i jedyną).
- Wyodrębnij przewidywane wartości z niej.

Poprzedni algorytm można zaimplementować przy użyciu [zrozumienie schematu](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), za pomocą dwóch obiektów zdefiniowanych przez użytkownika `InputExample` i `OutputPrediction` w następujący sposób:

```c#
var inputData = env.CreateDataView(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = outputData.AsDynamic.AsEnumerable<OutputPrediction>(env, reuseRowObject: false).Single();
```

Ale to jest skomplikowana względem i ponosi koszty wydajności. Zamiast tego obiektu funkcji prognozowania wykonuje takie same pracy, ale szybciej i łatwiej za pomocą metody rozszerzenia `MakePredictionFunction`:

```c#
var predictionFunc = model.MakePredictionFunction<InputExample, OutputPrediction>(env);
var output = predictionFunc.Predict(example);
```

Funkcja prognozowania *nie wielobieżnej / wątkowo*. Jeśli chcesz przeprowadzić prognoz jednocześnie z wielu wątków, musisz mieć funkcji prognozowania na wątek.
