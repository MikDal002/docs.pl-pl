---
title: "ICorDebugModule::GetBaseAddress — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetBaseAddress
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3e6a613fc272dc20089856b479b62afd5bf2487
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="3308d-102">ICorDebugModule::GetBaseAddress — Metoda</span><span class="sxs-lookup"><span data-stu-id="3308d-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="3308d-103">Pobiera adres podstawowy modułu.</span><span class="sxs-lookup"><span data-stu-id="3308d-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3308d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3308d-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3308d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3308d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="3308d-106">[out] A `CORDB_ADDRESS` , który określa adres bazowy modułu.</span><span class="sxs-lookup"><span data-stu-id="3308d-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3308d-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3308d-107">Remarks</span></span>  
 <span data-ttu-id="3308d-108">Jeśli moduł jest natywny obrazu (to znaczy, jeśli moduł został utworzony przez generator obrazu natywnego, NGen.exe), jej adres podstawowy będą miały wartość zero.</span><span class="sxs-lookup"><span data-stu-id="3308d-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3308d-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3308d-109">Requirements</span></span>  
 <span data-ttu-id="3308d-110">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3308d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3308d-111">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3308d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3308d-112">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3308d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3308d-113">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3308d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3308d-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3308d-114">See Also</span></span>  
    
 