---
title: "CorCallingConvention — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallingConvention
helpviewer_keywords: CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c0fbbb5f2c8f73cb6c76137263fa457840cdddc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="34b56-102">CorCallingConvention — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="34b56-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="34b56-103">Zawiera wartości, które opisują typy konwencji wywoływania, które zostały wprowadzone w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="34b56-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34b56-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="34b56-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="34b56-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="34b56-105">Members</span></span>  
  
|<span data-ttu-id="34b56-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="34b56-106">Member</span></span>|<span data-ttu-id="34b56-107">Opis</span><span class="sxs-lookup"><span data-stu-id="34b56-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="34b56-108">Wskazuje domyślną konwencję wywoływania.</span><span class="sxs-lookup"><span data-stu-id="34b56-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="34b56-109">Wskazuje, że metoda korzysta z różną liczbą parametrów.</span><span class="sxs-lookup"><span data-stu-id="34b56-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="34b56-110">Wskazuje, że wywołanie jest do pola.</span><span class="sxs-lookup"><span data-stu-id="34b56-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="34b56-111">Oznacza wywołania do metody lokalnego.</span><span class="sxs-lookup"><span data-stu-id="34b56-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="34b56-112">Wskazuje, że wywołanie jest właściwością.</span><span class="sxs-lookup"><span data-stu-id="34b56-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="34b56-113">Wskazuje, że wywołanie jest niezarządzany.</span><span class="sxs-lookup"><span data-stu-id="34b56-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="34b56-114">Wskazuje wystąpienia metody ogólnej.</span><span class="sxs-lookup"><span data-stu-id="34b56-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="34b56-115">Wskazuje 64-bitowych wywołanie funkcji PInvoke do metody, która przyjmuje zmienną liczbę parametrów.</span><span class="sxs-lookup"><span data-stu-id="34b56-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="34b56-116">W tym artykule opisano nieprawidłową wartość 4-bitowy.</span><span class="sxs-lookup"><span data-stu-id="34b56-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="34b56-117">Wskazuje, czy za pomocą liczby bitów dolnej czterech opisano konwencji wywołania.</span><span class="sxs-lookup"><span data-stu-id="34b56-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="34b56-118">Wskazuje opisujący top bitu `this` parametru.</span><span class="sxs-lookup"><span data-stu-id="34b56-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="34b56-119">Oznacza to, że `this` parametru jest opisana jawnie w podpisie.</span><span class="sxs-lookup"><span data-stu-id="34b56-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="34b56-120">Określa podpis metody ogólnej z jawnym liczby argumentów typu.</span><span class="sxs-lookup"><span data-stu-id="34b56-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="34b56-121">Liczba parametrów zwykłej to poprzedza.</span><span class="sxs-lookup"><span data-stu-id="34b56-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34b56-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="34b56-122">Requirements</span></span>  
 <span data-ttu-id="34b56-123">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34b56-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b56-124">**Nagłówek:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="34b56-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="34b56-125">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34b56-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34b56-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="34b56-126">See Also</span></span>  
 [<span data-ttu-id="34b56-127">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="34b56-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)