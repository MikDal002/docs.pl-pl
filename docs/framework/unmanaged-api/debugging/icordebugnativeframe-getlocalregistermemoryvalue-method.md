---
title: "ICorDebugNativeFrame::GetLocalRegisterMemoryValue — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 58d48b8d3b45afe4018d80ce30066708085c517a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="96d75-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="96d75-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="96d75-103">Pobiera wartość argumentu lub zmiennej lokalnej, z których word niski i wysoki word są przechowywane w lokalizacji pamięci i określić rejestru, odpowiednio dla tego natywną.</span><span class="sxs-lookup"><span data-stu-id="96d75-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d75-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="96d75-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96d75-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="96d75-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="96d75-106">[in] Wartość określająca rejestru zawierającego słowo wysokiej wartości wyliczenia "CorDebugRegister".</span><span class="sxs-lookup"><span data-stu-id="96d75-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="96d75-107">[in] A `CORDB_ADDRESS` wartość, która określa lokalizację pamięci zawierające słowo niskiej wartości.</span><span class="sxs-lookup"><span data-stu-id="96d75-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="96d75-108">[in] Liczba całkowita określająca rozmiar podpisu metadanych binarny, który odwołuje się do niego `pvSigBlob` parametru.</span><span class="sxs-lookup"><span data-stu-id="96d75-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="96d75-109">[in] A `PCCOR_SIGNATURE` wartość, która wskazuje podpisu metadanych binarnego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="96d75-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="96d75-110">[out] Wskaźnik do adresu "ICorDebugValue" obiekt reprezentujący pobranej wartości przechowywane w określonej lokalizacji rejestru i pamięci.</span><span class="sxs-lookup"><span data-stu-id="96d75-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d75-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="96d75-111">Requirements</span></span>  
 <span data-ttu-id="96d75-112">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96d75-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d75-113">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96d75-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96d75-114">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96d75-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96d75-115">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d75-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d75-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96d75-116">See Also</span></span>  
 