---
title: "IMapToken::Map — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMapToken.Map
api_location: mscoree.dll
api_type: COM
f1_keywords: IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2e3a9701bab27764803442a3cd0c24c4e412deaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="b620e-102">IMapToken::Map — Metoda</span><span class="sxs-lookup"><span data-stu-id="b620e-102">IMapToken::Map Method</span></span>
<span data-ttu-id="b620e-103">Mapuje relacji między zestawami przy użyciu podpisów metadanych.</span><span class="sxs-lookup"><span data-stu-id="b620e-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b620e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b620e-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b620e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b620e-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="b620e-106">[in] Token metadanych, który reprezentuje obiekt importowany kodu.</span><span class="sxs-lookup"><span data-stu-id="b620e-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="b620e-107">[in] Token metadanych, który reprezentuje obiekt emitowany kodu.</span><span class="sxs-lookup"><span data-stu-id="b620e-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b620e-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b620e-108">Remarks</span></span>  
 <span data-ttu-id="b620e-109">Token mapowane ponownie wystąpi podczas scalania, oryginalny token ma zakres w zakresie metadanych importowanych (źródło), a nowy token, ma zakres w zakresie metadanych emitowany (docelowy).</span><span class="sxs-lookup"><span data-stu-id="b620e-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b620e-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b620e-110">Requirements</span></span>  
 <span data-ttu-id="b620e-111">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b620e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b620e-112">**Nagłówek:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b620e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b620e-113">**Biblioteka:** używany jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b620e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b620e-114">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b620e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b620e-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b620e-115">See Also</span></span>  
 [<span data-ttu-id="b620e-116">IMapToken — interfejs</span><span class="sxs-lookup"><span data-stu-id="b620e-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)