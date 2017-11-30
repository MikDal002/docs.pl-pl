---
title: "CorGCReferenceType — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45ca1e9c6123a4b22a1645d151e49a0dd65addbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="ca461-102">CorGCReferenceType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="ca461-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="ca461-103">Określa źródło obiektu być zbierane z pamięci.</span><span class="sxs-lookup"><span data-stu-id="ca461-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca461-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ca461-104">Syntax</span></span>  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="ca461-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="ca461-105">Members</span></span>  
  
|<span data-ttu-id="ca461-106">Nazwa elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="ca461-106">Member name</span></span>|<span data-ttu-id="ca461-107">Opis</span><span class="sxs-lookup"><span data-stu-id="ca461-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="ca461-108">Dojście do silne odwołanie z tabeli uchwyt obiektu.</span><span class="sxs-lookup"><span data-stu-id="ca461-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="ca461-109">Dojście do przypiętych silne odwołanie z tabeli uchwyt obiektu.</span><span class="sxs-lookup"><span data-stu-id="ca461-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="ca461-110">Dojście do słabe odwołanie z tabeli uchwyt obiektu.</span><span class="sxs-lookup"><span data-stu-id="ca461-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="ca461-111">Dojście do obiektu zliczane Odwołanie słabe z tabeli uchwyt obiektu.</span><span class="sxs-lookup"><span data-stu-id="ca461-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="ca461-112">Dojście do obiektu zliczane odwołanie z tabeli uchwyt obiektu.</span><span class="sxs-lookup"><span data-stu-id="ca461-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="ca461-113">Dojście do obiektu zależnego z tabeli uchwyt obiektu.</span><span class="sxs-lookup"><span data-stu-id="ca461-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="ca461-114">Asynchroniczny obiekt przypiętych z tabeli uchwyt obiektu.</span><span class="sxs-lookup"><span data-stu-id="ca461-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="ca461-115">Dojście silne podtrzymujące przybliżone zbiorowe zamknięcia wszystkich obiektów i katalogi główne obiektu w momencie kolekcji pamięci.</span><span class="sxs-lookup"><span data-stu-id="ca461-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="ca461-116">Odwołanie z zarządzanego stosu.</span><span class="sxs-lookup"><span data-stu-id="ca461-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="ca461-117">Odwołanie z kolejki finalizatora.</span><span class="sxs-lookup"><span data-stu-id="ca461-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="ca461-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="ca461-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="ca461-119">Zwraca tylko silne odwołania z tabeli dojścia.</span><span class="sxs-lookup"><span data-stu-id="ca461-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="ca461-120">Ta wartość jest używana przez [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) tylko metody.</span><span class="sxs-lookup"><span data-stu-id="ca461-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="ca461-121">Zwraca tylko słabego odwołania z tabeli dojścia.</span><span class="sxs-lookup"><span data-stu-id="ca461-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="ca461-122">Ta wartość jest używana przez [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) tylko metody.</span><span class="sxs-lookup"><span data-stu-id="ca461-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="ca461-123">Zwraca wszystkie odwołania z tabeli dojścia.</span><span class="sxs-lookup"><span data-stu-id="ca461-123">Return all references from the handle table.</span></span> <span data-ttu-id="ca461-124">Ta wartość jest używana przez [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) tylko metody.</span><span class="sxs-lookup"><span data-stu-id="ca461-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca461-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ca461-125">Remarks</span></span>  
 <span data-ttu-id="ca461-126">`CorGCReferenceType` Wyliczenie jest używane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="ca461-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="ca461-127">Jako wartość `type` pole [cor_gc_reference —](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) struktury wskazuje źródło dojście lub odwołanie.</span><span class="sxs-lookup"><span data-stu-id="ca461-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="ca461-128">Jako `types` argument [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) metody Określa typy dojść do uwzględnienia w wyliczeniu.</span><span class="sxs-lookup"><span data-stu-id="ca461-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca461-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ca461-129">Requirements</span></span>  
 <span data-ttu-id="ca461-130">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca461-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca461-131">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca461-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca461-132">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca461-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca461-133">**Wersje programu .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca461-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca461-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ca461-134">See Also</span></span>  
 [<span data-ttu-id="ca461-135">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="ca461-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)