---
title: "ICorDebugGCReferenceEnum::Next — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 55a02b88076d6097415d108d58f74565d1f426de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="f96b6-102">ICorDebugGCReferenceEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="f96b6-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="f96b6-103">Pobiera określoną liczbę [cor_gc_reference —](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) wystąpień, które zawierają informacje o obiektach, które mają być zbierane z pamięci.</span><span class="sxs-lookup"><span data-stu-id="f96b6-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f96b6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f96b6-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f96b6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f96b6-105">Parameters</span></span>  
 <span data-ttu-id="f96b6-106">celt</span><span class="sxs-lookup"><span data-stu-id="f96b6-106">celt</span></span>  
 <span data-ttu-id="f96b6-107">[in] Liczba głównych, które mają zostać pobrane.</span><span class="sxs-lookup"><span data-stu-id="f96b6-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="f96b6-108">elementy główne</span><span class="sxs-lookup"><span data-stu-id="f96b6-108">roots</span></span>  
 <span data-ttu-id="f96b6-109">[out] Tablicy wskaźników, z których każdy wskazuje [cor_gc_reference —](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) obiekt, który reprezentuje katalog główny obiekt, aby być zbierane z pamięci.</span><span class="sxs-lookup"><span data-stu-id="f96b6-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="f96b6-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="f96b6-110">pceltFetched</span></span>  
 <span data-ttu-id="f96b6-111">[out] Wskaźnik do liczby [cor_gc_reference —](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) obiekty zwrócone faktycznie w `roots`.</span><span class="sxs-lookup"><span data-stu-id="f96b6-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="f96b6-112">Ta wartość może być `null` Jeśli `celt` 1.</span><span class="sxs-lookup"><span data-stu-id="f96b6-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f96b6-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f96b6-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f96b6-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f96b6-114">Requirements</span></span>  
 <span data-ttu-id="f96b6-115">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f96b6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f96b6-116">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f96b6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f96b6-117">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f96b6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f96b6-118">**Wersje programu .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f96b6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96b6-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f96b6-119">See Also</span></span>  
 [<span data-ttu-id="f96b6-120">ICorDebugGCReferenceEnum — interfejs</span><span class="sxs-lookup"><span data-stu-id="f96b6-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 [<span data-ttu-id="f96b6-121">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="f96b6-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)