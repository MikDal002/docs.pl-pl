---
title: "ICorDebugEval::CallFunction — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CallFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72713d81931b53e8d61fb39cee146fd30a59bfcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="07138-102">ICorDebugEval::CallFunction — Metoda</span><span class="sxs-lookup"><span data-stu-id="07138-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="07138-103">Konfiguruje wywołanie określonych funkcji.</span><span class="sxs-lookup"><span data-stu-id="07138-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="07138-104">Ta metoda jest przestarzała w programie .NET Framework w wersji 2.0.</span><span class="sxs-lookup"><span data-stu-id="07138-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="07138-105">Użyj [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="07138-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07138-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="07138-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07138-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="07138-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="07138-108">[in] Wskaźnik do obiektu ICorDebugFunction, który określa funkcję, która ma zostać wywołana.</span><span class="sxs-lookup"><span data-stu-id="07138-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="07138-109">[in] Liczba argumentów funkcji.</span><span class="sxs-lookup"><span data-stu-id="07138-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="07138-110">[in] Tablicy wskaźników, z których każdy wskazuje obiekt ICorDebugValue określający argument można przekazać do funkcji.</span><span class="sxs-lookup"><span data-stu-id="07138-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07138-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="07138-111">Remarks</span></span>  
 <span data-ttu-id="07138-112">Jeśli funkcja jest wirtualny, `CallFunction` wykona wirtualnego wysyłania.</span><span class="sxs-lookup"><span data-stu-id="07138-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="07138-113">Jeśli funkcja znajduje się w domenie innej aplikacji, przejście zostanie przeprowadzona tak długo, jak wszystkie argumenty mają również w tej domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="07138-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07138-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="07138-114">Requirements</span></span>  
 <span data-ttu-id="07138-115">**Platformy:** WindowSee [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07138-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07138-116">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07138-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07138-117">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07138-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07138-118">**Wersje programu .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="07138-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07138-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="07138-119">See Also</span></span>  
 [<span data-ttu-id="07138-120">CallParameterizedFunction — metoda</span><span class="sxs-lookup"><span data-stu-id="07138-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)