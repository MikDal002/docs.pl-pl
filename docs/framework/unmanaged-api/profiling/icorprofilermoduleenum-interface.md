---
title: "ICorProfilerModuleEnum — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 43cc6afc42fc1a02fd7d7b3df2973cc9b3e31251
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="bda21-102">ICorProfilerModuleEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="bda21-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="bda21-103">Udostępnia metody sekwencyjnie iterowania po kolekcji moduły załadowane przez profiler lub aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bda21-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bda21-104">Metody</span><span class="sxs-lookup"><span data-stu-id="bda21-104">Methods</span></span>  
  
|<span data-ttu-id="bda21-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="bda21-105">Method</span></span>|<span data-ttu-id="bda21-106">Opis</span><span class="sxs-lookup"><span data-stu-id="bda21-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bda21-107">Clone — metoda</span><span class="sxs-lookup"><span data-stu-id="bda21-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="bda21-108">Pobiera wskaźnika interfejsu kopię `ICorProfilerModuleEnum` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="bda21-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="bda21-109">GetCount — metoda</span><span class="sxs-lookup"><span data-stu-id="bda21-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="bda21-110">Pobiera liczbę modułów zarządzanych, które zostały załadowane do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bda21-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="bda21-111">Next — metoda</span><span class="sxs-lookup"><span data-stu-id="bda21-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="bda21-112">Pobiera określoną liczbę modułów ciągłe z sekwencyjną kolekcją obiektów, zaczynając od modułu wyliczającego bieżącej pozycji w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bda21-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="bda21-113">Reset — metoda</span><span class="sxs-lookup"><span data-stu-id="bda21-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="bda21-114">Przesuwa kursor modułu wyliczającego pozycji początkowej sekwencji.</span><span class="sxs-lookup"><span data-stu-id="bda21-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="bda21-115">SKIP — metoda</span><span class="sxs-lookup"><span data-stu-id="bda21-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="bda21-116">Zmienia pozycję kursora modułu wyliczającego, dzięki czemu określoną liczbę elementów są pomijane.</span><span class="sxs-lookup"><span data-stu-id="bda21-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bda21-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bda21-117">Remarks</span></span>  
 <span data-ttu-id="bda21-118">`ICorProfilerModuleEnum` Interfejs jest moduł wyliczający.</span><span class="sxs-lookup"><span data-stu-id="bda21-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="bda21-119">Umożliwia odbiorcy tablicy do ściągania elementów od nadawcy szybkością, który jest odpowiedni dla odbiornika.</span><span class="sxs-lookup"><span data-stu-id="bda21-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="bda21-120">Innymi słowy odbiorca jest w stanie jawnie sterowanie przepływem elementów tablicy, zapobiegając problemów związanych z przekazywanie dużych tablic jako parametrów metody.</span><span class="sxs-lookup"><span data-stu-id="bda21-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda21-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bda21-121">Requirements</span></span>  
 <span data-ttu-id="bda21-122">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda21-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda21-123">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bda21-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bda21-124">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bda21-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bda21-125">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda21-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda21-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bda21-126">See Also</span></span>  
 [<span data-ttu-id="bda21-127">ICorProfilerInfo — interfejs</span><span class="sxs-lookup"><span data-stu-id="bda21-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="bda21-128">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="bda21-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="bda21-129">EnumModules — metoda</span><span class="sxs-lookup"><span data-stu-id="bda21-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)