---
title: "ICorDebugModule::GetClassFromToken — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetClassFromToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bd483eebc66b1274c0d28c46b3ccb1b1272f74b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="22925-102">ICorDebugModule::GetClassFromToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="22925-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="22925-103">Pobiera z klasą określoną przez token metadanych.</span><span class="sxs-lookup"><span data-stu-id="22925-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22925-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="22925-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22925-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="22925-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="22925-106">[in] `mdTypeDef` Token metadanych, który odwołuje się do metadanych klasy.</span><span class="sxs-lookup"><span data-stu-id="22925-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="22925-107">[out] Wskaźnik do adresu ICorDebugClass obiektu, który reprezentuje klasę.</span><span class="sxs-lookup"><span data-stu-id="22925-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22925-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="22925-108">Requirements</span></span>  
 <span data-ttu-id="22925-109">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22925-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22925-110">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22925-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22925-111">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22925-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22925-112">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22925-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>