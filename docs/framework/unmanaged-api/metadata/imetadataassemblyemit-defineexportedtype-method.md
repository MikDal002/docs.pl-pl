---
title: IMetaDataAssemblyEmit::DefineExportedType — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 071466858c79fdb74d9055fed09990cdb02a88b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624352"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType — Metoda
Tworzy `ExportedType` struktury zawierającej metadanych dla określonego wyeksportować typu, a następnie zwraca token skojarzone metadane.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szName`  
 [in] Nazwa typu do wyeksportowania. Dla wersji 1.1 środowisko uruchomieniowe języka wspólnego, nazwa typu wyeksportowanego musi dokładnie odpowiadać nazwa nadana `TypeDef` dla typu.  
  
 `tkImplementation`  
 [in] Token, określający, gdzie typ eksportowany jest zaimplementowana. Prawidłowe wartości i ich znaczenie skojarzone są:  
  
-   `mdFile` Typ jest zaimplementowana w innym pliku w tym zestawie.  
  
-   `mdAssemblyRef` Typ jest zaimplementowana w innym zestawie.  
  
-   `mdExportedTYpe` Typ jest zagnieżdżony w ramach innego typu.  
  
-   `mdFileNil` Typ znajduje się w tym samym pliku manifestu i nie jest typem zagnieżdżonym.  
  
 `tkTypeDef`  
 [in] Token metadanych, który określa typ do wyeksportowania. Ta wartość jest wprowadzana w `TypeDef` tabeli w pliku, który implementuje ten typ. i ma zastosowanie tylko wtedy, gdy ten plik znajduje się w tym zestawie.  
  
 `dwExportedTypeFlags`  
 [in] Bitowa kombinacja [cortypeattr —](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) wartości wyliczenia, które definiują ustawienia właściwości typu wyeksportowanego.  
  
 `pmdct`  
 [out] Wskaźnik do tokenu zwróconych metadanych, który określa typ eksportowany.  
  
## <a name="remarks"></a>Uwagi  
 `ExportedType` Struktury metadanych musi być zdefiniowana dla każdego typu, który jest udostępniany przez ten zestaw i jest implementowana w module innym niż zawierającego manifest.  
  
## <a name="requirements"></a>Wymagania  
 **Platforma:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** COR.h  
  
 **Biblioteka:** Używany jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [IMetaDataAssemblyEmit, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
