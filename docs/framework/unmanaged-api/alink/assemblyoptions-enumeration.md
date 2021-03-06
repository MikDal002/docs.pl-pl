---
title: AssemblyOptions — Wyliczenie
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 939e815f4d3adc5f6e1c8b8fc85c9f4b89372501
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571486"
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions — Wyliczenie
Wylicza opcje zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Pola  
  
|Pole|Opis|  
|-----------|-----------------|  
|optAssemTitle|String — reprezentuje tytuł zestawu.|  
|optAssemDescription|String — zawiera opis zestawu.|  
|optAssemConfig|String — zawiera konfigurację zestawu.|  
|optAssemOS|Parametry - zakodowanymi w formacie: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|String — zawiera zestaw ustawień regionalnych.|  
|optAssemVersion|Parametry - zakodowanymi w formacie: "Główna.pomocnicza.kompilacja.poprawka".|  
|optAssemCompany|String — zawiera firmy.|  
|optAssemProduct|String — zawiera nazwę produktu.|  
|optAssemProductVersion|Ciąg (znany także jako InformationalVersion).|  
|optAssemCopyright|String — zawiera informacje o prawach autorskich.|  
|optAssemTrademark|String — zawiera informacje o znakach towarowych.|  
|optAssemKeyFile|String (nazwa pliku).|  
|optAssemKeyName|Ciąg (nazwa klucza).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Wartość logiczna (określana także jako DelaySign).|  
|optAssemFileVersion|Parametry - zakodowanymi w formacie "Główna.pomocnicza.kompilacja.poprawka"--takie same jak ProductVersion.|  
|optAssemSatelliteVer|Parametry - zakodowanymi w formacie "Główna.pomocnicza.kompilacja.poprawka".|  
|optLastAssemOption|Licznik liczby elementów.|  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** alink.h  
  
 **Biblioteka**: alink.dll  
  
## <a name="see-also"></a>Zobacz także
- [Al.exe (konsolidator zestawów)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
