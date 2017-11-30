---
title: "ICLRRuntimeInfo::SetDefaultStartupFlags — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.SetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1732073b9799453bd32447e7a688b0280e66f1ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="3a648-102">ICLRRuntimeInfo::SetDefaultStartupFlags — Metoda</span><span class="sxs-lookup"><span data-stu-id="3a648-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="3a648-103">Ustawia flagi uruchamiania i pliku konfiguracji hosta, który będzie używany do uruchomienia środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="3a648-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="3a648-104">Ta metoda zastępuje użycie `startupFlags` parametru w [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) i [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funkcji.</span><span class="sxs-lookup"><span data-stu-id="3a648-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a648-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="3a648-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a648-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="3a648-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="3a648-107">[in] Flagi uruchomienia hosta można ustawić.</span><span class="sxs-lookup"><span data-stu-id="3a648-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="3a648-108">Użyj tego samego flagi jako z [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) i [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funkcji.</span><span class="sxs-lookup"><span data-stu-id="3a648-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="3a648-109">[in] Ścieżka katalogu pliku konfiguracji hosta, aby ustawić.</span><span class="sxs-lookup"><span data-stu-id="3a648-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a648-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3a648-110">Return Value</span></span>  
 <span data-ttu-id="3a648-111">Ta metoda zwraca następujące HRESULT określonych oraz HRESULT błędów, które wskazuje niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="3a648-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3a648-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a648-112">HRESULT</span></span>|<span data-ttu-id="3a648-113">Opis</span><span class="sxs-lookup"><span data-stu-id="3a648-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a648-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a648-114">S_OK</span></span>|<span data-ttu-id="3a648-115">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3a648-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a648-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3a648-116">Remarks</span></span>  
 <span data-ttu-id="3a648-117">Wielowątkowe hosta należy synchronizować wywołania tej metody.</span><span class="sxs-lookup"><span data-stu-id="3a648-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="3a648-118">W przeciwnym razie może wywołać wątku A `SetStartupFlags` metody wywołania zakończone wątku B `SetStartupFlags` i przed wątku B uruchamia środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="3a648-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a648-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3a648-119">Requirements</span></span>  
 <span data-ttu-id="3a648-120">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a648-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a648-121">**Nagłówek:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3a648-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3a648-122">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a648-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a648-123">**Wersje programu .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a648-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a648-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3a648-124">See Also</span></span>  
 [<span data-ttu-id="3a648-125">ICLRRuntimeInfo — interfejs</span><span class="sxs-lookup"><span data-stu-id="3a648-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="3a648-126">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="3a648-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3a648-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="3a648-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)