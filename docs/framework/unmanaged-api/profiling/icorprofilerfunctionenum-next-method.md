---
title: "ICorProfilerFunctionEnum::Next — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Next Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6cf37beced15305de60c3f57edb701adc7379a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="63d89-102">ICorProfilerFunctionEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="63d89-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="63d89-103">Pobiera określoną liczbę funkcji ciągłego z sekwencyjną kolekcją funkcji, zaczynając od modułu wyliczającego bieżącej pozycji w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="63d89-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d89-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="63d89-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63d89-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="63d89-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="63d89-106">[in] Liczbę funkcji do pobrania.</span><span class="sxs-lookup"><span data-stu-id="63d89-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="63d89-107">[out] Tablica `COR_PRF_FUNCTION` wartości, z których każdy reprezentuje funkcję pobrane.</span><span class="sxs-lookup"><span data-stu-id="63d89-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="63d89-108">[out] Wskaźnik do liczbę faktycznie zwracane w funkcji `ids` tablicy.</span><span class="sxs-lookup"><span data-stu-id="63d89-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63d89-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="63d89-109">Return Value</span></span>  
 <span data-ttu-id="63d89-110">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="63d89-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="63d89-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63d89-111">HRESULT</span></span>|<span data-ttu-id="63d89-112">Opis</span><span class="sxs-lookup"><span data-stu-id="63d89-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63d89-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="63d89-113">S_OK</span></span>|<span data-ttu-id="63d89-114">`celt`elementy zostały zwrócone.</span><span class="sxs-lookup"><span data-stu-id="63d89-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="63d89-115">WARTOŚCI S_FALSE</span><span class="sxs-lookup"><span data-stu-id="63d89-115">S_FALSE</span></span>|<span data-ttu-id="63d89-116">Mniej niż `celt` elementy zostały zwrócone, co oznacza, że wyliczenia została zakończona.</span><span class="sxs-lookup"><span data-stu-id="63d89-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63d89-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="63d89-117">Requirements</span></span>  
 <span data-ttu-id="63d89-118">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d89-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d89-119">**Nagłówek:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63d89-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63d89-120">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d89-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d89-121">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d89-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d89-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="63d89-122">See Also</span></span>  
 [<span data-ttu-id="63d89-123">ICorProfilerFunctionEnum — interfejs</span><span class="sxs-lookup"><span data-stu-id="63d89-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="63d89-124">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="63d89-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)