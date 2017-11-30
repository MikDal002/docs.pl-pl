---
title: "CoEEShutDownCOM — Funkcja"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d6d9e3d650f65ef084c63104980bca0ac77f1bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="70226-102">CoEEShutDownCOM — Funkcja</span><span class="sxs-lookup"><span data-stu-id="70226-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="70226-103">Wymusza środowisko uruchomieniowe języka wspólnego (CLR), aby zwolnić wszystkie wskaźniki interfejsu, którą przechowuje wewnątrz wywoływane otoki środowiska uruchomieniowego (otoki RCW).</span><span class="sxs-lookup"><span data-stu-id="70226-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="70226-104">To ustawienie zwalnia wszystkie otoki RCW pamięci podręcznych.</span><span class="sxs-lookup"><span data-stu-id="70226-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="70226-105">Ta funkcja globalna jest przestarzała w [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70226-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="70226-106">W zamian użyj punkt wejścia dla określonego środowiska wykonawczego.</span><span class="sxs-lookup"><span data-stu-id="70226-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70226-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="70226-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="70226-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="70226-108">Remarks</span></span>  
 <span data-ttu-id="70226-109">`CoEEShutDownCOM` Funkcji najpierw zwalnia wszystkie RCWs we wszystkich kontekstach i wszystkich usług pamięć podręczna i spowoduje usunięcie wszystkich istniejących w Instalatorze powiadomień zakończenia.</span><span class="sxs-lookup"><span data-stu-id="70226-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="70226-110">Występuje, nie zwalnianie biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="70226-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="70226-111">Ta funkcja ma wpływ na wszystkie środowiska uruchomieniowe, które są ładowane do procesu.</span><span class="sxs-lookup"><span data-stu-id="70226-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="70226-112">Począwszy od [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], wywołaj punkt wejścia dla tej funkcji na określonych ma wpływ na środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="70226-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="70226-113">Aby uzyskać punktu wejścia, należy wywołać [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) metodę i określić "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="70226-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70226-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70226-114">Requirements</span></span>  
 <span data-ttu-id="70226-115">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70226-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70226-116">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70226-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70226-117">**Biblioteka:** uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70226-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70226-118">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70226-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70226-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="70226-119">See Also</span></span>  
 [<span data-ttu-id="70226-120">Statyczne funkcje globalne metadanych</span><span class="sxs-lookup"><span data-stu-id="70226-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)