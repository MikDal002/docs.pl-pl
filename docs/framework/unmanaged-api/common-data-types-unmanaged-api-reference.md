---
title: "Standardowe typy danych (niezarządzana dokumentacja interfejsu API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03350825b3de4515a0d30e8644f34df71efa25db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="common-data-types-unmanaged-api-reference"></a><span data-ttu-id="aa34d-102">Standardowe typy danych (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="aa34d-102">Common Data Types (Unmanaged API Reference)</span></span>
<span data-ttu-id="aa34d-103">Ten temat zawiera listę typów proste danych używany przez niezarządzane interfejsy API programu .NET Framework, które są definiowane przez C/C++ `typedef` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="aa34d-103">This topic lists simple data types used by the unmanaged APIs for the .NET Framework that are defined by C/C++ `typedef` statements.</span></span> <span data-ttu-id="aa34d-104">Te typy danych są zazwyczaj aliasów dla typów pierwotnych danych C/C++.</span><span class="sxs-lookup"><span data-stu-id="aa34d-104">These data types are typically aliases for C/C++ primitive data types.</span></span> <span data-ttu-id="aa34d-105">Zazwyczaj wartości te typy danych są nieprzezroczyste; oznacza to, że są zwracane przez określonej funkcji lub metody, dzięki czemu mogą być przekazywane do innych funkcji lub metody bez żadnych modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="aa34d-105">Typically, the values of these data types are opaque; that is, they are returned by a particular function or method so that they can be passed to other functions or methods without modification.</span></span>  
  
|<span data-ttu-id="aa34d-106">Typ danych</span><span class="sxs-lookup"><span data-stu-id="aa34d-106">Data type</span></span>|<span data-ttu-id="aa34d-107">Definicja</span><span class="sxs-lookup"><span data-stu-id="aa34d-107">Definition</span></span>|<span data-ttu-id="aa34d-108">Zdefiniowany w</span><span class="sxs-lookup"><span data-stu-id="aa34d-108">Defined in</span></span>|<span data-ttu-id="aa34d-109">Opis</span><span class="sxs-lookup"><span data-stu-id="aa34d-109">Description</span></span>|  
|---------------|----------------|----------------|-----------------|  
|<span data-ttu-id="aa34d-110">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="aa34d-110">AppDomainID</span></span>|`typedef UINT_PTR AppDomainID;`|<span data-ttu-id="aa34d-111">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-111">corprof.h</span></span>|<span data-ttu-id="aa34d-112">Identyfikator domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="aa34d-112">The identifier of an application domain.</span></span>|  
|<span data-ttu-id="aa34d-113">Właściwość AssemblyID</span><span class="sxs-lookup"><span data-stu-id="aa34d-113">AssemblyID</span></span>|`typedef UINT_PTR AssemblyID;`|<span data-ttu-id="aa34d-114">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-114">corprof.h</span></span>|<span data-ttu-id="aa34d-115">Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="aa34d-115">The identifier of an assembly.</span></span>|  
|<span data-ttu-id="aa34d-116">Identyfikator klasy</span><span class="sxs-lookup"><span data-stu-id="aa34d-116">ClassID</span></span>|`typedef UINT_PTR ClassID;`|<span data-ttu-id="aa34d-117">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-117">corprof.h</span></span>|<span data-ttu-id="aa34d-118">Identyfikator klasy zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="aa34d-118">The identifier of a managed class.</span></span>|  
|<span data-ttu-id="aa34d-119">CONNID</span><span class="sxs-lookup"><span data-stu-id="aa34d-119">CONNID</span></span>|`typedef DWORD CONNID;`|<span data-ttu-id="aa34d-120">cordebug.h, mscoree.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-120">cordebug.h, mscoree.h</span></span>|<span data-ttu-id="aa34d-121">Identyfikator połączenia dla wątku, który jest podłączony do wystąpienia programu Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aa34d-121">The connection identifier for a thread that is connected to an instance of Microsoft SQL Server.</span></span>|  
|<span data-ttu-id="aa34d-122">Identyfikator kontekstu</span><span class="sxs-lookup"><span data-stu-id="aa34d-122">ContextID</span></span>|`typedef UINT_PTR ContextID;`|<span data-ttu-id="aa34d-123">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-123">corprof.h</span></span>|<span data-ttu-id="aa34d-124">Identyfikator kontekstu skojarzonego z konkretnym wątkiem zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="aa34d-124">The identifier of the context associated with a particular managed thread.</span></span>|  
|<span data-ttu-id="aa34d-125">COR_PRF_ELT_INFO</span><span class="sxs-lookup"><span data-stu-id="aa34d-125">COR_PRF_ELT_INFO</span></span>|`typedef UINT_PTR COR_PRF_ELT_INFO;`|<span data-ttu-id="aa34d-126">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-126">corprof.h</span></span>|<span data-ttu-id="aa34d-127">Nieprzezroczystego uchwyt reprezentujący informacji na temat ramka stosu określonego.</span><span class="sxs-lookup"><span data-stu-id="aa34d-127">An opaque handle that represents information about a particular stack frame.</span></span>|  
|<span data-ttu-id="aa34d-128">COR_PRF_FRAME_INFO</span><span class="sxs-lookup"><span data-stu-id="aa34d-128">COR_PRF_FRAME_INFO</span></span>|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|<span data-ttu-id="aa34d-129">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-129">corprof.h</span></span>|<span data-ttu-id="aa34d-130">Nieprzezroczyste obsługi się do ramki stosu.</span><span class="sxs-lookup"><span data-stu-id="aa34d-130">An opaque handle that points to a stack frame.</span></span> <span data-ttu-id="aa34d-131">Jest on prawidłowy tylko w trakcie wywołania zwrotnego, do którego jest przekazywany.</span><span class="sxs-lookup"><span data-stu-id="aa34d-131">It is valid only during the callback to which it is passed.</span></span>|  
|<span data-ttu-id="aa34d-132">CORDB_ADDRESS</span><span class="sxs-lookup"><span data-stu-id="aa34d-132">CORDB_ADDRESS</span></span>|`typedef ULONG64 CORDB_ADDRESS;`|<span data-ttu-id="aa34d-133">cordebug.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-133">cordebug.h</span></span>|<span data-ttu-id="aa34d-134">Adres w pamięci.</span><span class="sxs-lookup"><span data-stu-id="aa34d-134">An address in memory.</span></span>|  
|<span data-ttu-id="aa34d-135">CORDB_CONTINUE_STATUS</span><span class="sxs-lookup"><span data-stu-id="aa34d-135">CORDB_CONTINUE_STATUS</span></span>|`typedef DWORD CORDB_CONTINUE_STATUS;`|<span data-ttu-id="aa34d-136">cordebug.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-136">cordebug.h</span></span>|<span data-ttu-id="aa34d-137">Stan kontynuacji.</span><span class="sxs-lookup"><span data-stu-id="aa34d-137">The continuation status.</span></span>|  
|<span data-ttu-id="aa34d-138">CORDB_REGISTER</span><span class="sxs-lookup"><span data-stu-id="aa34d-138">CORDB_REGISTER</span></span>|`typedef ULONG64 CORDB_REGISTER;`|<span data-ttu-id="aa34d-139">cordebug.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-139">cordebug.h</span></span>|<span data-ttu-id="aa34d-140">Wartość rejestru procesora CPU.</span><span class="sxs-lookup"><span data-stu-id="aa34d-140">The value of a CPU register.</span></span>|  
|<span data-ttu-id="aa34d-141">FunctionID</span><span class="sxs-lookup"><span data-stu-id="aa34d-141">FunctionID</span></span>|`typedef UINT_PTR FunctionID;`|<span data-ttu-id="aa34d-142">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-142">corprof.h</span></span>|<span data-ttu-id="aa34d-143">Identyfikator metody lub funkcji.</span><span class="sxs-lookup"><span data-stu-id="aa34d-143">The identifier of a function or method.</span></span>|  
|<span data-ttu-id="aa34d-144">GCHandleID</span><span class="sxs-lookup"><span data-stu-id="aa34d-144">GCHandleID</span></span>|`typedef UINT_PTR GCHandleID;`|<span data-ttu-id="aa34d-145">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-145">corprof.h</span></span>|<span data-ttu-id="aa34d-146">Uchwyt kolekcji pamięci.</span><span class="sxs-lookup"><span data-stu-id="aa34d-146">A garbage collection handle.</span></span>|  
|<span data-ttu-id="aa34d-147">mdToken</span><span class="sxs-lookup"><span data-stu-id="aa34d-147">mdToken</span></span>|`typedef UINT32 mdToken;`|<span data-ttu-id="aa34d-148">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-148">corprof.h</span></span>|<span data-ttu-id="aa34d-149">Token metadanych (wiersz w tabeli metadanych).</span><span class="sxs-lookup"><span data-stu-id="aa34d-149">A   metadata token (a row in a metadata table).</span></span>|  
|<span data-ttu-id="aa34d-150">ModuleID</span><span class="sxs-lookup"><span data-stu-id="aa34d-150">ModuleID</span></span>|`typedef UINT_PTR ModuleID;`|<span data-ttu-id="aa34d-151">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-151">corprof.h</span></span>|<span data-ttu-id="aa34d-152">Identyfikator modułu zestawu.</span><span class="sxs-lookup"><span data-stu-id="aa34d-152">The identifier of an assembly module.</span></span>|  
|<span data-ttu-id="aa34d-153">Identyfikator obiektu</span><span class="sxs-lookup"><span data-stu-id="aa34d-153">ObjectID</span></span>|`typedef UINT_PTR ObjectID;`|<span data-ttu-id="aa34d-154">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-154">corprof.h</span></span>|<span data-ttu-id="aa34d-155">Identyfikator obiektu.</span><span class="sxs-lookup"><span data-stu-id="aa34d-155">The identifier of an object.</span></span>|  
|<span data-ttu-id="aa34d-156">Identyfikator procesu</span><span class="sxs-lookup"><span data-stu-id="aa34d-156">ProcessID</span></span>|`typedef UINT_PTR ProcessID;`|<span data-ttu-id="aa34d-157">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-157">corprof.h</span></span>|<span data-ttu-id="aa34d-158">Identyfikator procesu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="aa34d-158">The identifier of a managed process.</span></span>|  
|<span data-ttu-id="aa34d-159">ReJITID</span><span class="sxs-lookup"><span data-stu-id="aa34d-159">ReJITID</span></span>|`typedef UINT_PTR ReJITID;`|<span data-ttu-id="aa34d-160">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-160">corprof.h</span></span>|<span data-ttu-id="aa34d-161">Identyfikator funkcji skompilowanych w trybie JIT.</span><span class="sxs-lookup"><span data-stu-id="aa34d-161">The identifier of a jitted function.</span></span>|  
|<span data-ttu-id="aa34d-162">TASKID</span><span class="sxs-lookup"><span data-stu-id="aa34d-162">TASKID</span></span>|`typedef UINT64 TASKID;`|<span data-ttu-id="aa34d-163">cordebug.h, mscoree.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-163">cordebug.h, mscoree.h</span></span>|<span data-ttu-id="aa34d-164">Identyfikator [ICLRTask](../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="aa34d-164">The identifier of an [ICLRTask](../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|<span data-ttu-id="aa34d-165">Identyfikator wątku</span><span class="sxs-lookup"><span data-stu-id="aa34d-165">ThreadID</span></span>|`typedef UINT_PTR ThreadID;`|<span data-ttu-id="aa34d-166">corprof.h</span><span class="sxs-lookup"><span data-stu-id="aa34d-166">corprof.h</span></span>|<span data-ttu-id="aa34d-167">Identyfikator zarządzanego wątku.</span><span class="sxs-lookup"><span data-stu-id="aa34d-167">The identifier of a managed thread.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa34d-168">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aa34d-168">See Also</span></span>  
 [<span data-ttu-id="aa34d-169">Niezarządzany wykaz interfejsów API</span><span class="sxs-lookup"><span data-stu-id="aa34d-169">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)