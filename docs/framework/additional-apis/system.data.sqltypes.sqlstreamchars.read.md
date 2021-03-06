---
title: Metoda SqlStreamChars.Read (Char [], Int32, Int32) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: da891ac1fcff0247a690770665ef1f3e487497b8
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825371"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a>Metoda SqlStreamChars.Read (Char [], Int32, Int32)

W przypadku przesłonięcia w klasie pochodnej, odczytuje następny zestaw znaków ze strumienia wejściowego. Zestaw, który zawiera tę metodę ma relację zaprzyjaźniona z SQLAccess.dll. Jest przeznaczony do użytku przez program SQL Server. W przypadku innych baz danych użyj mechanizmu hostowania, pod warunkiem, że ta baza danych.

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parametry

`buffer`\
Tablicy znaków do odczytania.

`offset`\
Przesunięcie względem źródła.

`count`\
Liczba znaków, które mają być odczytywane z bieżącego strumienia.

## <a name="returns"></a>Zwraca

<xref:System.Int32>\
Całkowita liczba znaków czytanych w buforze.

## <a name="remarks"></a>Uwagi

> [!WARNING]
> `SqlStreamChars.Read` Metoda jest prywatny i nie jest przeznaczona do użycia bezpośrednio w kodzie.
>
> Firma Microsoft obsługuje korzystanie z tego pola w aplikacji produkcyjnej w żadnym wypadku.

## <a name="requirements"></a>Wymagania

**Namespace:** <xref:System.Data.SqlTypes>

**Zestaw:** Dane systemowe (w System.Data.dll)

**Wersje programu .NET framework:** Dostępne od wersji 2.0.