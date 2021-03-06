---
title: Liczniki wydajności w punkcie końcowym
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: de750b3e5ee61b6bfc5b387fb7de84b74171d8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501964"
---
# <a name="endpoint-performance-counters"></a>Liczniki wydajności w punkcie końcowym
Liczniki wydajności w punkcie końcowym przechwytywania danych, która ujawnia się, jak punkt końcowy jest akceptowanie komunikatów. Można go znaleźć w `ServiceModelEndpoint 4.0.0.0` obiekt wydajności podczas wyświetlania przy użyciu Monitora wydajności. Wystąpienia są nazywane użycia tego wzorca:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Dane są podobne do zebranych dla poszczególnych działań, ale tylko jest agregowana dla punktu końcowego.  
  
> [!CAUTION]
>  Obowiązuje limit długości nazwy wystąpienia licznika wydajności. Gdy nazwę wystąpienia licznika Windows Communication Foundation (WCF) przekracza maksymalną długość, WCF zastępuje część nazwy wystąpienia z wartością skrótu.  
  
## <a name="see-also"></a>Zobacz także
- [Liczniki wydajności](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
