---
title: <servicePointManager> — Element (Ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: 3a18f9eb3d38ef272b7a4df58d8588b622662184
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277553"
---
# <a name="servicepointmanager-element-network-settings"></a>\<ServicePointManager — >, Element (ustawienia sieci)
Służy do konfigurowania połączeń z zasobami sieciowymi.  
  
 \<Konfiguracja >  
\<system.net>  
\<settings>  
\<servicePointManager>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|**Atrybut**|**Opis**|  
|-------------------|---------------------|  
|`checkCertificateName`|Określa, czy system należy sprawdzić, czy nazwa w certyfikacie jest zgodna nazwa hosta serwera przed rozpoczęciem korzystania z certyfikatu. Wartość domyślna to `true`.|  
|`checkCertificateRevocationList`|Określa, czy system należy sprawdzić, czy certyfikat został odwołany przed rozpoczęciem korzystania z certyfikatu. Wartość domyślna to `false`.|  
|`dnsRefreshTimeout`|Określa, ile domeny nazwa usługi (DNS) rozwiązania są buforowane w połączeniu z opcją DNS okrężnego w milisekundach. Wartość domyślna to 120 000 milisekund (dwie minuty).|  
|`enableDnsRoundRobin`|Określa, czy nazwy rozwiązania DNS hosta z wieloma adresami Internet Protocol (IP), zwracany, wszystkie adresy lub tylko pierwszy z nich. Wartość domyślna to `false`.|  
|`encryptionPolicy`|Określa zasady szyfrowania, zastosowane do sesji SSL/TLS w <xref:System.Net.ServicePointManager> wystąpienia. Możliwe wartości to odpowiednikiem wartości <xref:System.Net.Security.EncryptionPolicy> wyliczenia. Korzystanie z <xref:System.Security.Authentication.CipherAlgorithmType.Null> jest wymagany, jeśli ustawiono zasady szyfrowania `NoEncryption`. Wartość domyślna to `RequireEncryption`.|  
|`expect100Continue`|Określa, czy metody POST należy się spodziewać otrzymać `100-continue` odpowiedzi z serwera. Wartość domyślna to `true`.|  
|`useNagleAlgorithm`|Określa, czy kontrolowane przez usługę Menedżer punktu połączenia używają algorytmu Nagle'a. Wartość domyślna to `true`.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|**Element**|**Opis**|  
|-----------------|---------------------|  
|[Ustawienia](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguruje opcje sieciowe podstawowe dla <xref:System.Net> przestrzeni nazw.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="configuration-files"></a>Pliki konfiguracji  
 Ten element może być użyty w pliku konfiguracji aplikacji lub w pliku konfiguracji komputera (Machine.config).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Schemat ustawień sieci](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
