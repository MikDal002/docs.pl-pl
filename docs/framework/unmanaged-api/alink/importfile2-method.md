---
title: ImportFile2 — Metoda
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3c145bae61922894f4893d532923319ccf16f85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499015"
---
# <a name="importfile2-method"></a>ImportFile2 — Metoda
Importuje zestawów i modułów niepowiązanej. Ta metoda przypomina [importfile — metoda](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), ale wtedy, gdy importowanego pliku nie istnieje na dysku.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszFilename`  
 Nazwa pliku do zaimportowania.  
  
 `pszTargetName`  
 Nazwa pliku wyjściowego opcjonalny, którego można zmienić nazwy pliku, ponieważ jest on połączony do zestawu.  
  
 `pAssemblyScopeIn`  
 Opcjonalne zakresu [imetadataassemblyimport — interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfejsu.  
  
 `fSmartImport`  
 W przypadku opcji TRUE importtypes — jest używana, w przeciwnym razie importowanie muszą być wykonywane ręcznie.  
  
 `pImportToken`  
 Odbiera identyfikator pliku lub zestawu.  
  
 `ppAssemblyScope`  
 Odbiera [imetadataassemblyimport — interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfejsu. Wartość NULL, jeśli plik nie jest zestawem.  
  
 `pdwCountOfScopes`  
 Odbiera znaleziono plików i/lub zakresów zaimportowane.  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca wartość S_OK, jeśli metoda zakończy się powodzeniem.  
  
## <a name="requirements"></a>Wymagania  
 Wymaga alink.h.  
  
## <a name="see-also"></a>Zobacz także
- [IALink, interfejs](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2, interfejs](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink, interfejs API](../../../../docs/framework/unmanaged-api/alink/index.md)
