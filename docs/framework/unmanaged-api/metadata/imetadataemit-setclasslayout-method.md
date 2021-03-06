---
title: IMetaDataEmit::SetClassLayout — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dc1664551683066a33fb52e16e4909506601f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588694"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout — Metoda
Kończy układ pól dla klasy, która została zdefiniowana przez wcześniejsze wywołanie [definetypedef — metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `td`  
 [in] `mdTypeDef` Tokenu, który określa klasy, która ma być rozmieszczony.  
  
 `dwPackSize`  
 [in] Rozmiar pakowania: 1, 2, 4, 8 lub 16 bajtów. Rozmiar pakowania to liczbę bajtów między sąsiadujące pola.  
  
 `rFieldOffsets`  
 [in] Tablica [cor_field_offset —](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) struktur, z których każdy określa pola klasy i przesunięcie w klasie. Zakończenie tablicy przy użyciu `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Rozmiar w bajtach klasy.  
  
## <a name="remarks"></a>Uwagi  
 Klasa jest wstępnie zdefiniowana przez wywołanie metody [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) metoda i określając jeden z trzech układów pola klasy: automatyczny, sekwencyjnych lub jawnego. Zwykle będzie Użyj automatycznego układu i pozwól środowiska uruchomieniowego wybierasz najlepszą metodę, aby zmienić układ pól.  
  
 Jednakże możesz zechcieć pola rozmieszczony zgodnie z rozmieszczenie niezarządzany kod używa. W takim przypadku wybierz Sekwencyjna lub jawnego układu i wywołania `SetClassLayout` do ukończenia układ pól:  
  
-   Sekwencyjne układu: Określ rozmiar pakowania. Pole jest wyrównany zgodnie z rozmiarem fizyczne lub rozmiar pakowania, niezależnie od wyników w mniejszych przesunięcie pola. Ustaw `rFieldOffsets` i `ulClassSize` do zera.  
  
-   Jawnego układu: Określ przesunięcie każdego pola lub określić rozmiar klasy i rozmiarem pakowania.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** COR.h  
  
 **Biblioteka:** Używany jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [IMetaDataEmit, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
