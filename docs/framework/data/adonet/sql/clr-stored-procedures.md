---
title: Procedury składowane CLR
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: a1a37ac1257594913c6d06cb08df2882e8773da8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554637"
---
# <a name="clr-stored-procedures"></a>Procedury składowane CLR
Procedury składowane są procedury, które nie mogą być używane w wyrażenia skalarne. One zwrócenia jej klientowi wyniki tabelaryczne i komunikaty, wywołaj języka definicji danych (DDL) i instrukcje języka (DML) manipulacji danych i zwracać parametry wyjściowe.  
  
> [!NOTE]
>  Microsoft Visual Basic nie obsługuje parametrów wyjściowych w taki sam sposób, który Microsoft Visual C# wykonuje. Należy określić, Przekaż parametr według odwołania, a następnie zastosować \<Out() > atrybut do reprezentowania parametr wyjściowy, co przedstawiono poniżej:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Aby uzyskać szczegółowe informacje, zobacz wersję [dokumentacji programu SQL Server](/sql) dla wersji programu SQL Server jest używany.
  
 **Dokumentacja programu SQL Server**

1. [Procedury składowane CLR](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Zobacz także
- [Tworzenie obiekty programu SQL Server 2005 w kodzie zarządzanym](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)
- [ADO.NET zarządzanego dostawcy i Centrum deweloperów zestawu danych](https://go.microsoft.com/fwlink/?LinkId=217917)
