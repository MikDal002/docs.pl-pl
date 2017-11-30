---
title: "ICLRRuntimeInfo::IsLoadable — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoadable
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ada33942af97f476de25c2ea3243818808e2dc9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="b12cb-102">ICLRRuntimeInfo::IsLoadable — Metoda</span><span class="sxs-lookup"><span data-stu-id="b12cb-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="b12cb-103">Wskazuje, czy środowisko uruchomieniowe skojarzone z tym interfejsem, mogą zostać załadowane do bieżącego procesu, biorąc pod uwagę innych środowisk uruchomieniowych, który może być już załadowany do procesu.</span><span class="sxs-lookup"><span data-stu-id="b12cb-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12cb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b12cb-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b12cb-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b12cb-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="b12cb-106">[out] `true` Jeżeli to środowisko uruchomieniowe może być załadowane do bieżącego procesu; w przeciwnym razie `false`.</span><span class="sxs-lookup"><span data-stu-id="b12cb-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b12cb-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b12cb-107">Return Value</span></span>  
 <span data-ttu-id="b12cb-108">Ta metoda zwraca następujące określonych wyników HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="b12cb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b12cb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b12cb-109">HRESULT</span></span>|<span data-ttu-id="b12cb-110">Opis</span><span class="sxs-lookup"><span data-stu-id="b12cb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b12cb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b12cb-111">S_OK</span></span>|<span data-ttu-id="b12cb-112">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b12cb-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="b12cb-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b12cb-113">E_POINTER</span></span>|<span data-ttu-id="b12cb-114">`pbLoadable`ma wartość null.</span><span class="sxs-lookup"><span data-stu-id="b12cb-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b12cb-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b12cb-115">Remarks</span></span>  
 <span data-ttu-id="b12cb-116">Jeśli innego środowiska wykonawczego został już załadowany do procesu i mogą być ładowane skojarzone z tym interfejs środowiska uruchomieniowego w trakcie wykonywania side-by-side, `pbLoadable` zwraca `true`.</span><span class="sxs-lookup"><span data-stu-id="b12cb-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="b12cb-117">Jeśli dwóch środowisk uruchomieniowych nie można uruchomić side-by-side w procesie, `pbLoadable` zwraca `false`.</span><span class="sxs-lookup"><span data-stu-id="b12cb-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="b12cb-118">Na przykład środowisko uruchomieniowe języka wspólnego (CLR) w wersji 4, można uruchomić side-by-side w tym samym procesie z CLR w wersji 2.0 lub CLR w wersji 1.1.</span><span class="sxs-lookup"><span data-stu-id="b12cb-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="b12cb-119">Jednak CLR w wersji 1.1 i CLR w wersji 2.0 nie mogą uruchamiać side-by-side w procesie.</span><span class="sxs-lookup"><span data-stu-id="b12cb-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="b12cb-120">Jeśli żadnych środowisk uruchomieniowych są ładowane do procesu, ta metoda zawsze zwraca `true`.</span><span class="sxs-lookup"><span data-stu-id="b12cb-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12cb-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b12cb-121">Requirements</span></span>  
 <span data-ttu-id="b12cb-122">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b12cb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b12cb-123">**Nagłówek:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b12cb-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b12cb-124">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b12cb-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b12cb-125">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b12cb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12cb-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b12cb-126">See Also</span></span>  
 [<span data-ttu-id="b12cb-127">ICLRRuntimeInfo — interfejs</span><span class="sxs-lookup"><span data-stu-id="b12cb-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="b12cb-128">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="b12cb-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="b12cb-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="b12cb-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)