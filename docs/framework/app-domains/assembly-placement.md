---
title: Umieszczanie zestawu
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2168c167c89f989f70a10d5832e70c93a8f90f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529898"
---
# <a name="assembly-placement"></a>Umieszczanie zestawu
W przypadku większości aplikacji .NET Framework można umieścić zestawy, które tworzą aplikację w katalogu aplikacji, w podkatalogu katalogu aplikacji lub w globalnej pamięci podręcznej (Jeśli zestaw jest udostępniana). Można zastąpić, których środowisko uruchomieniowe języka wspólnego szuka zestawu, za pomocą [ \<codeBase > Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) w pliku konfiguracji. Jeśli zestaw nie ma silnej nazwy, lokalizacji określonej przy użyciu [ \<codeBase > Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) jest ograniczony do katalogu aplikacji lub podkatalog. Jeśli zestaw ma silną nazwą, [ \<codeBase > Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) mogą określić dowolną lokalizację, na komputerze lub w sieci.  
  
 Podobne zasady dotyczą lokalizowanie zestawów podczas pracy z kodem niezarządzanym lub aplikacje międzyoperacyjne COM: Jeśli zestaw zostanie udostępniony przez wiele aplikacji, należy zainstalować w globalnej pamięci podręcznej. Zestawy używane z kodem niezarządzanym musi być wyeksportowany jako bibliotekę typów i zarejestrowana. Zespoły korzystają z modelu COM musi być zarejestrowana w wykazie, chociaż w niektórych przypadkach rejestracja odbywa się automatycznie.  
  
## <a name="see-also"></a>Zobacz także
- [Sposoby lokalizowania zestawów przez środowisko uruchomieniowe](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurowanie aplikacji](../../../docs/framework/configure-apps/index.md)
- [Współdziałanie z kodem niezarządzanym](../../../docs/framework/interop/index.md)
- [Zestawy w środowisku uruchomieniowym CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
