---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: b63f8917d7af21c165a16bd45a83e774bcec6e1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551608"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Tworzy wystąpienie [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) klasy.  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a>Parametry  
  
## <a name="parameter-values"></a>Wartości parametrów  
 *operationDescription*  
  
 Opisuje operacji do wykonania działania przepływu pracy, który ma zostać wygenerowane, łącznie z nazwą operacji, zwracany typ i informacje o parametrze. Wartość tego parametru nie może być **null**. Powinien on zawierać synchroniczne operacji, który używa kontraktu komunikatu i używa argumentu z jednej wiadomości. Jeśli te warunki nie są spełnione, wynik środowiska wykonawczego przy użyciu konstruktora i inne metody tej klasy jest nieokreślona.  
  
 *configurationName*  
  
 Określa nazwę konfiguracji punktu końcowego. Wartość tego parametru nie może być albo **null** lub jest pusty. Jeśli te warunki nie są spełnione, wynik środowiska wykonawczego przy użyciu konstruktora i inne metody tej klasy jest nieokreślona.  
  
 *proxyNamespace*  
  
 Określa obszar nazw usługi dla operacji. Wartość tego parametru nie może być albo **null** lub jest pusty. Jeśli te warunki nie są spełnione, wynik środowiska wykonawczego przy użyciu konstruktora i inne metody tej klasy jest nieokreślona.  
  
## <a name="see-also"></a>Zobacz także
- [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
