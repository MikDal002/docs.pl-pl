---
title: Używanie elementu ExpressionTextBox w Projektancie działań niestandardowych
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: 87f1052b5bf2c7c4e260aa606cb03b978726bb77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587872"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Używanie elementu ExpressionTextBox w Projektancie działań niestandardowych
Ten przykład ilustruje sposób używania <xref:System.Activities.Presentation.View.ExpressionTextBox> w Projektancie działań niestandardowych. Niestandardowe działanie `MultiAssign`, przypisuje dwóch wartości ciągu do dwóch zmiennych ciągu. Niektóre <xref:System.Activities.Presentation.View.ExpressionTextBox> powiązać formanty <xref:System.Activities.InArgument>s, a niektóre powiązać <xref:System.Activities.OutArgument>s.

## <a name="sample-details"></a>Przykład szczegółów
 `ArgumentToExpressionConverter` Jest konwertera typów używane podczas tworzenia powiązania wyrażeń do argumentów. `ConverterParameter` Musi być równa `In` lub `Out` odpowiednio. `InOut` nie jest obsługiwane.

 `UseLocationExpression` Atrybut jest używany na `OutArgument`s, aby określić, że wyrażenie powinny być wyrażenie L-wartość ("po lewej stronie wartość" lub "lokalizacji wartość"). W większości przypadków wyrażenie L-wartością jest prawidłowym identyfikatorem języka Visual Basic, używany do wskazania, że `OutArgument` zwracana jest nazwa zmiennej lub argumentu.

 `MaxLines` Ma ustawioną wartość atrybutu w tym przykładzie i `MinLines` nie jest ustawiona. Oznacza to, że <xref:System.Activities.Presentation.View.ExpressionTextBox> ma stały rozmiar jeden wiersz, niezależnie od ilości tekst wpisany przez użytkownika. Aby umożliwić <xref:System.Activities.Presentation.View.ExpressionTextBox> się zwiększać w celu dopasowania danych wejściowych użytkownika, ustaw `MaxLines` większa `MinLines`.

 Elementu ExpressionTextBox może być powiązana tylko z argumentów i nie można powiązać z właściwości aparatu CLR.

#### <a name="to-use-this-sample"></a>Aby użyć tego przykładu

1.  Za pomocą programu Visual Studio 2010, otwórz plik ExpressionTextBoxSample.sln.

2.  Aby skompilować rozwiązanie, naciśnij klawisze CTRL + SHIFT + B.

#### <a name="to-run-this-sample"></a>Aby uruchomić ten przykład

1.  Dodaj nową aplikację konsoli przepływu pracy do rozwiązania.

2.  Dodaj odwołanie do **ExpressionTextBoxSample** projektu z nowy projekt aplikacji konsoli przepływu pracy.

3.  Skompiluj rozwiązanie.

4.  Przeciągnij **MultiAssign** działania z przybornika i upuść go w przepływie pracy.

> [!IMPORTANT]
>  Przykłady może już być zainstalowany na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do strony [Windows Communication Foundation (WCF) i przykłady Windows Workflow Foundation (WF) dla platformy .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) do pobierania wszystkich Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykładów. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [Tworzenie aplikacji przy użyciu Projektanta przepływu pracy](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
