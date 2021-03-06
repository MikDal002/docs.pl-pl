---
title: ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d83270d0e7f5dabff8402f5f81dae20d4457d147
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604261"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs
Pozwala zdefiniować informacje dotyczące metody async opcjonalne dla każdej metody symbolu. Zawsze używaj metodą otwarte; oznacza to między wywołaniami [openmethod — metoda](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) i [closemethod — metoda](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Składnia  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Metody  
 Ten interfejs zawiera następujące metody:  
  
|Metoda|Opis|  
|------------|-----------------|  
|[DefineAsyncStepInfo, metoda](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Zdefiniuj grupę async operator await operacji w bieżącej metodzie.<br /><br /> Przesunięcie każdego yield pasuje do zwrotu instrukcji await, identyfikowanie potencjalnej wydajności. Każdy `breakpointMethod` / `breakpointOffset` pary identyfikuje, gdy operacja asynchroniczna zostanie wznowiona; może być w innej metody.|  
|[DefineCatchHandlerILOffset, metoda](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Ustawia IL przesunięcie obsługi catch generowanych przez kompilator, który otacza metody asynchronicznej.<br /><br /> Przesunięcie IL wygenerowanego catch jest używany przez debuger do obsługi catch, tak jakby kod niezwiązany z użytkownikiem, mimo że może występować w metodzie kodu użytkownika. W szczególności jest używany w odpowiedzi na **CatchHandlerFound** zdarzenie wyjątku.|  
|[DefineKickoffMethod, metoda](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Ustawia metodę początkową, która inicjuje operacji asynchronicznej.|  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Zobacz także
- [Interfejsy magazynu symboli diagnostycznych](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
