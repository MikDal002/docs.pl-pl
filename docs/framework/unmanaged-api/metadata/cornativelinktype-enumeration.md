---
title: CorNativeLinkType — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f946179fc31adebc8e8fc67c394e0b55a876f49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641333"
---
# <a name="cornativelinktype-enumeration"></a>CorNativeLinkType — Wyliczenie
Zawiera wartości wskazujące typ połączone w kodzie natywnym.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`nltNone`|Wskazuje brak słów kluczowych określony.|  
|`nltAnsi`|Wskazuje, że zostanie określone słowo kluczowe ANSI.|  
|`nltUnicode`|Wskazuje, że określono Unicode — słowo kluczowe|  
|`nltAuto`|Wskazuje, że określono auto — słowo kluczowe.|  
|`nltOle`|Wskazuje, że zostanie określone słowo kluczowe OLE.|  
|`nltMaxValue`|Nie używany.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** COR.h  
  
 **Biblioteka:** Dołączony jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Wyliczenia metadanych](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
