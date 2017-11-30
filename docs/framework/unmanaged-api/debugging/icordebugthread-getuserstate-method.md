---
title: "ICorDebugThread::GetUserState — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetUserState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 48a86317774a3ebba4ed600b880110a7adaa02a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="7b637-102">ICorDebugThread::GetUserState — Metoda</span><span class="sxs-lookup"><span data-stu-id="7b637-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="7b637-103">Pobiera bieżący stan to ICorDebugThread użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7b637-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b637-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7b637-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b637-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7b637-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="7b637-106">[out] Wskaźnik do bitowe połączenie wartości wyliczenia CorDebugUserState, które opisują bieżący stan użytkownika tego wątku.</span><span class="sxs-lookup"><span data-stu-id="7b637-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b637-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7b637-107">Remarks</span></span>  
 <span data-ttu-id="7b637-108">Stanu użytkownika w wątku jest stan wątku, gdy jest on analizowane przez program, który jest debugowany.</span><span class="sxs-lookup"><span data-stu-id="7b637-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="7b637-109">Wątek może mieć wiele bitów stanu.</span><span class="sxs-lookup"><span data-stu-id="7b637-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b637-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7b637-110">Requirements</span></span>  
 <span data-ttu-id="7b637-111">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b637-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b637-112">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b637-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b637-113">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b637-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b637-114">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b637-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>