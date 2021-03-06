---
title: IMetaDataImport::ResolveTypeRef — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c69c67c5c9d996bd746d82ea86caf4a396c0b10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625240"
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef — Metoda
Rozpoznaje <xref:System.Type> reprezentowany przez określony token TypeRef odwołania.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `tr`  
 [in] Token TypeRef metadanych do zwrócenia informacji o typie odwołania.  
  
 `riid`  
 [in] IID interfejsu do zwrócenia w `ppIScope`. Zazwyczaj powinien to być IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Interfejs do zakresu modułu, w którym zdefiniowano typ odwołania.  
  
 `ptd`  
 [out] Wskaźnik do TypeDef token, który reprezentuje typ odwołania.  
  
## <a name="remarks"></a>Uwagi  
  
> [!IMPORTANT]
>  Nie należy używać tej metody, jeśli wiele domen aplikacji są ładowane. Metoda respektują granice domen aplikacji. Jeśli wiele wersji zestawu zostaną załadowane i zawierają ten sam typ o tej samej przestrzeni nazw, metoda zwraca zakres modułu pierwszego typu, które znajdzie.  
  
 `ResolveTypeRef` Metoda wyszukiwania dla definicji typu w innych modułach. Jeśli zostanie znaleziony w definicji typu, `ResolveTypeRef` zwraca interfejs do tego zakresu modułu, a także token element TypeDef dla typu.  
  
 Jeśli odniesienie typu, które mają zostać rozwiązane, ma zakres rozpoznawania elementu AssemblyRef, `ResolveTypeRef` metoda szuka dopasowania tylko w przypadku zakresów metadanych, które już zostały otwarte przy użyciu wywołań albo [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)metody lub [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) metody. Jest to spowodowane `ResolveTypeRef` nie może ustalić z tylko zakres elementu AssemblyRef miejsce na dysku lub w globalnej pamięci podręcznej zestawu przechowywania.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** COR.h  
  
 **Biblioteka:** Dołączony jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [IMetaDataImport, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
