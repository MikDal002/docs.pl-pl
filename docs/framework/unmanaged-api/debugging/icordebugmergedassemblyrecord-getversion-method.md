---
title: "ICorDebugMergedAssemblyRecord::GetVersion — metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68fa2b1b7502f13876c6e613f012a0c78ab7c5d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="c0ce5-102">ICorDebugMergedAssemblyRecord::GetVersion — metoda</span><span class="sxs-lookup"><span data-stu-id="c0ce5-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="c0ce5-103">Pobiera informacje o wersji zestawu.</span><span class="sxs-lookup"><span data-stu-id="c0ce5-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ce5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c0ce5-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0ce5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c0ce5-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="c0ce5-106">[out] Wskaźnik do głównego numeru wersji.</span><span class="sxs-lookup"><span data-stu-id="c0ce5-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="c0ce5-107">[out] Wskaźnik do podrzędny numer wersji.</span><span class="sxs-lookup"><span data-stu-id="c0ce5-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="c0ce5-108">[out] Wskaźnik do numeru kompilacji.</span><span class="sxs-lookup"><span data-stu-id="c0ce5-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="c0ce5-109">[out] Wskaźnik do numer wersji.</span><span class="sxs-lookup"><span data-stu-id="c0ce5-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0ce5-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c0ce5-110">Remarks</span></span>  
 <span data-ttu-id="c0ce5-111">Aby uzyskać informacje na numery wersji zestawu, zobacz <xref:System.Version> klasy tematu.</span><span class="sxs-lookup"><span data-stu-id="c0ce5-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0ce5-112">Ta metoda jest tylko dostępne z platformą .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c0ce5-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ce5-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c0ce5-113">Requirements</span></span>  
 <span data-ttu-id="c0ce5-114">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ce5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ce5-115">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0ce5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0ce5-116">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ce5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0ce5-117">**Wersje programu .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ce5-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ce5-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c0ce5-118">See Also</span></span>  
 [<span data-ttu-id="c0ce5-119">Interfejs ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="c0ce5-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="c0ce5-120">Interfejsy debugowania</span><span class="sxs-lookup"><span data-stu-id="c0ce5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)