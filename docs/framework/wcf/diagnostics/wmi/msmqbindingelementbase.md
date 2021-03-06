---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: a0e2ac250da3837b41134d3a04a21579a2fe923a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569040"
---
# <a name="msmqbindingelementbase"></a>MsmqBindingElementBase
MsmqBindingElementBase  
  
## <a name="syntax"></a>Składnia  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a>Metody  
 Klasa MsmqBindingElementBase nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  
 Klasa MsmqBindingElementBase ma następujące właściwości:  
  
### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue  
 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Identyfikator URI, który zawiera lokalizację kolejki utraconych wiadomości dla każdej aplikacji, gdzie umieszcza komunikaty wygasły lub mają niepowodzeniem transferu lub dostarczania.  
  
### <a name="deadletterqueue"></a>DeadLetterQueue  
 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wyliczenia, który wskazuje na typ używanej kolejki utraconych wiadomości.  
  
### <a name="durable"></a>trwałe  
 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość, która wskazuje, czy komunikaty przetwarzane przez to powiązanie są trwałe lub zmienne.  
  
### <a name="exactlyonce"></a>exactlyOnce  
 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna wskazująca, czy komunikaty przetwarzane przez to powiązanie są odbierane dokładnie raz.  
  
### <a name="maxretrycycles"></a>MaxRetryCycles  
 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba ponownych prób cyklów próby dostarczenia komunikatów do aplikacji odbierającej.  
  
### <a name="receiveerrorhandling"></a>receiveErrorHandling  
 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Ustawienia obsługi Zarządzanie skażonymi komunikatami.  
  
### <a name="receiveretrycount"></a>ReceiveRetryCount  
 Typ danych: sint32  
  
 Typ dostępu: tylko do odczytu  
  
 Maksymalna liczba natychmiastowego ponawiania próby w wiadomości, które są odczytywane z kolejki aplikacji.  
  
### <a name="retrycycledelay"></a>RetryCycleDelay  
 Typ danych: Data i godzina  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość wskazująca czas opóźnienia między cykle przy próbie dostarczenia komunikatu, którego nie można dostarczyć natychmiast.  
  
### <a name="timetolive"></a>TimeToLive  
 Typ danych: Data i godzina  
  
 Typ dostępu: tylko do odczytu  
  
 Przedział czasu, która wskazuje, jak długo komunikaty przetwarzane przez to powiązanie mogą znajdować się w kolejce, zanim wygasną.  
  
### <a name="usemsmqtracing"></a>UseMsmqTracing  
 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna, która wskazuje, czy komunikaty przetwarzane przez to powiązanie powinny być śledzone.  
  
### <a name="usesourcejournal"></a>UseSourceJournal  
 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość logiczna wskazująca, czy kopie komunikatów przetwarzanych przez to powiązanie powinny być przechowywane w kolejce dziennika źródła.  
  
## <a name="requirements"></a>Wymagania  
  
|MOF|Zadeklarowana w Servicemodel.mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
