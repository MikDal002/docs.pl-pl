---
title: "IMetaDataEmit::SetEventProps — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 167e56052550fa844d1265802455b3cbf6368ba3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="310fe-102">IMetaDataEmit::SetEventProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="310fe-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="310fe-103">Ustawia lub aktualizuje określoną funkcję wynika z wcześniejszym wywołaniu zdarzenia [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="310fe-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="310fe-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="310fe-104">Syntax</span></span>  
  
```  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,   
    [in]  DWORD       dwEventFlags,   
    [in]  mdToken     tkEventType,   
    [in]  mdMethodDef mdAddOn,   
    [in]  mdMethodDef mdRemoveOn,   
    [in]  mdMethodDef mdFire,   
    [in]  mdMethodDef rmdOtherMethods[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="310fe-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="310fe-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="310fe-106">[in] Token zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="310fe-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="310fe-107">[in] Flagi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="310fe-107">[in] Event flags.</span></span> <span data-ttu-id="310fe-108">To jest maską bitów z `CorEventAttr` wartości.</span><span class="sxs-lookup"><span data-stu-id="310fe-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="310fe-109">[in] Token dla klasy zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="310fe-109">[in] The token for the event class.</span></span> <span data-ttu-id="310fe-110">Jest to `mdTypeDef` lub `mdTypeRef` tokenu.</span><span class="sxs-lookup"><span data-stu-id="310fe-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="310fe-111">[in] Metoda użyta do subskrybowania zdarzenia lub wartość null.</span><span class="sxs-lookup"><span data-stu-id="310fe-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="310fe-112">[in] Metoda używana do anulowania subskrypcji zdarzeń lub wartość null.</span><span class="sxs-lookup"><span data-stu-id="310fe-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="310fe-113">[in] Metoda używana (przez klasę pochodną), aby wywołać zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="310fe-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="310fe-114">[in] Tablica dla innych metod, skojarzone ze zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="310fe-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="310fe-115">Musi być ostatnim elementem tablicy `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="310fe-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="310fe-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="310fe-116">Requirements</span></span>  
 <span data-ttu-id="310fe-117">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="310fe-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="310fe-118">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="310fe-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="310fe-119">**Biblioteka:** używany jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="310fe-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="310fe-120">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="310fe-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="310fe-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="310fe-121">See Also</span></span>  
 [<span data-ttu-id="310fe-122">IMetaDataEmit — interfejs</span><span class="sxs-lookup"><span data-stu-id="310fe-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="310fe-123">IMetaDataEmit2 — interfejs</span><span class="sxs-lookup"><span data-stu-id="310fe-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)