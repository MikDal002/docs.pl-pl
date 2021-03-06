---
title: <remove> element dla NameValueSectionHandler i DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: c86d231a4e3e8e15df94017a6ca461b365643ea5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267420"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Usuń >, element dla NameValueSectionHandler i DictionarySectionHandler

Usuwa ustawienie uprzednio zdefiniowany.

[**\<Konfiguracja >**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Składnia

```xml
<add remove="key" />
```

## <a name="attribute"></a>Atrybut

|           | Opis |
| --------- | ----------- |
| **Klucz**   | Atrybut wymagany.<br><br>Określa nazwę ustawienie, aby usunąć. |

## <a name="parent-element"></a>Element nadrzędny

| Element | Opis |
| ------- | ------------|
| [**\<parametrami sectionName >** — Element](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | Definiuje ustawienia powiązane z sekcji konfiguracji niestandardowej, korzystających z <xref:System.Configuration.NameValueSectionHandler> i <xref:System.Configuration.DictionarySectionHandler> klasy. |

## <a name="child-elements"></a>Elementy podrzędne

Brak

## <a name="remarks"></a>Uwagi

Możesz użyć  **\<Usuń >** elementu do usunięcia ustawień z poziomu aplikacji, które zostały zdefiniowane na wyższym poziomie w hierarchii plików konfiguracji.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak używać  **\<Usuń >** elementu w pliku konfiguracyjnym aplikacji, aby usunąć ustawienia wcześniej zdefiniowane w pliku konfiguracji komputera.

Poniższy kod pliku konfiguracji maszyny deklaruje sekcji  **\<mySection >** i dodaje dwa ustawienia `key1` i `key2`, do niego:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

Poniższy kod pliku konfiguracji aplikacji usuwa `key2` z  **\<mySection >**:

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>Plik konfiguracji

Ten element może być użyty w pliku konfiguracyjnym aplikacji, plik konfiguracji komputera (*Machine.config*), a *Web.config* pliki, które nie są na poziomie katalogu aplikacji.

## <a name="see-also"></a>Zobacz także

- [Schemat pliku konfiguracji dla programu .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
