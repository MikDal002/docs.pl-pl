---
title: Wywołanie metod asynchronicznych za pomocą interfejsu IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01001d68b4bee42453fcb84725507b0cf61184a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610516"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>Wywołanie metod asynchronicznych za pomocą interfejsu IAsyncResult
Typy w .NET Framework i biblioteki klas w innych firm może zapewnić metody, które umożliwiają aplikacji do kontynuowania wykonywania podczas wykonywania operacji asynchronicznych w wątkach, innym niż wątku głównego aplikacji. W poniższych sekcjach opisano i zawierają przykłady kodu, które pokazują różne sposoby, można wywoływać metod asynchronicznych, które używają <xref:System.IAsyncResult> wzorca projektowego.  
  
-   [Blokowanie wykonywania aplikacji poprzez zakończenie operacji asynchronicznej](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
-   [Blokowanie wykonania aplikacji za pomocą właściwości AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
-   [Sondowanie stanu operacji asynchronicznej](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
-   [Używanie delegata AsyncCallback do kończenia operacji asynchronicznej](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>Zobacz także

- [Asynchroniczny wzorzec oparty na zdarzeniach (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Asynchroniczny wzorzec oparty na zdarzeniach — omówienie](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
