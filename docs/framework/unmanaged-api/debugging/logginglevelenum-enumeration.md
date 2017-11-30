---
title: "LoggingLevelEnum — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoggingLevelEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: LoggingLevelEnum
helpviewer_keywords: LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f6041f429c057cea9607df34ec5691be84e2d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="106e5-102">LoggingLevelEnum — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="106e5-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="106e5-103">Wskazuje poziom ważności opisowym komunikatem, które są zapisywane w dzienniku zdarzeń, gdy zarządzanego wątku rejestruje zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="106e5-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="106e5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="106e5-104">Syntax</span></span>  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="106e5-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="106e5-105">Members</span></span>  
  
|<span data-ttu-id="106e5-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="106e5-106">Member</span></span>|<span data-ttu-id="106e5-107">Opis</span><span class="sxs-lookup"><span data-stu-id="106e5-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="106e5-108">Komunikat jest poziom śledzenia 0.</span><span class="sxs-lookup"><span data-stu-id="106e5-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="106e5-109">Komunikat jest poziom śledzenia 1.</span><span class="sxs-lookup"><span data-stu-id="106e5-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="106e5-110">Komunikat jest poziom śledzenia 2.</span><span class="sxs-lookup"><span data-stu-id="106e5-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="106e5-111">Komunikat jest poziom śledzenia 3.</span><span class="sxs-lookup"><span data-stu-id="106e5-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="106e5-112">Komunikat jest poziom śledzenia 4.</span><span class="sxs-lookup"><span data-stu-id="106e5-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="106e5-113">Komunikat jest poziom stan 0.</span><span class="sxs-lookup"><span data-stu-id="106e5-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="106e5-114">Komunikat jest poziom stan 1.</span><span class="sxs-lookup"><span data-stu-id="106e5-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="106e5-115">Komunikat jest stan poziom 2.</span><span class="sxs-lookup"><span data-stu-id="106e5-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="106e5-116">Komunikat jest poziom stan 3.</span><span class="sxs-lookup"><span data-stu-id="106e5-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="106e5-117">Komunikat jest poziom stan 4.</span><span class="sxs-lookup"><span data-stu-id="106e5-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="106e5-118">Komunikat jest poziom ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="106e5-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="106e5-119">Komunikat jest błąd poziomu.</span><span class="sxs-lookup"><span data-stu-id="106e5-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="106e5-120">Komunikat jest alarm poziomu.</span><span class="sxs-lookup"><span data-stu-id="106e5-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="106e5-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="106e5-121">Remarks</span></span>  
 <span data-ttu-id="106e5-122">Środowisko uruchomieniowe języka wspólnego (CLR) wywołuje [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) metodę, aby powiadomić debuger zalogował zarządzanego wątku zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="106e5-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="106e5-123">Środowisko CLR przekazuje wartość `LoggingLevelEnum` wyliczeniu, aby wskazać poziom ważności wiadomości, która zarejestrowała zarządzanych wątków do dziennika zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="106e5-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="106e5-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="106e5-124">Requirements</span></span>  
 <span data-ttu-id="106e5-125">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="106e5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="106e5-126">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="106e5-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="106e5-127">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="106e5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="106e5-128">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="106e5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106e5-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="106e5-129">See Also</span></span>  
 <xref:System.Diagnostics.EventLog>  
 [<span data-ttu-id="106e5-130">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="106e5-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)