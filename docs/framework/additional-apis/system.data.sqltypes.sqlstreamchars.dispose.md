---
title: Metoda SqlStreamChars.Dispose(Boolean) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4e6cfd6d4c04b1a2835b6e34b82c95b564dea588
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826866"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a>Metoda SqlStreamChars.Dispose(Boolean)

W przypadku przesłonięcia w klasie pochodnej, zwalnia zasoby używane przez strumień. Zestaw, który zawiera tę metodę ma relację zaprzyjaźniona z SQLAccess.dll. Jest przeznaczony do użytku przez program SQL Server. W przypadku innych baz danych użyj mechanizmu hostowania, pod warunkiem, że ta baza danych.

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a>Parametry

`disposing`\
`true` Aby zwolnić zasoby zarządzane i niezarządzane; `false` aby zwolnić tylko niezarządzane zasoby.

## <a name="remarks"></a>Uwagi

> [!WARNING]
> `SqlStreamChars.Dispose` Metoda jest prywatny i nie jest przeznaczona do użycia bezpośrednio w kodzie.
>
> Firma Microsoft obsługuje korzystanie z tego pola w aplikacji produkcyjnej w żadnym wypadku.

## <a name="requirements"></a>Wymagania

**Namespace:** <xref:System.Data.SqlTypes>

**Zestaw:** Dane systemowe (w System.Data.dll)

**Wersje programu .NET framework:** Dostępne od wersji 2.0.