---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f77871c8547f250d4b46c11c1a0be25b6ef68a88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581954"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a>ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method
Pobiera klucz publiczny zestawu token.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cbPublicKeyToken`  
 [in] Maksymalna liczba bajtów w `pbPublicKeyToken` tablicy.  
  
 `pcbPublicKeyToken`  
 [out] Wskaźnik do rzeczywista liczba bajtów zapisanych na `pbPublicKeyToken` tablicy.  
  
 `pbPublicKeyToken`  
 [out] Wskaźnik do tablicy typu byte, który zawiera token klucza publicznego zestawu.  
  
## <a name="remarks"></a>Uwagi  
 Token klucza publicznego zestawu jest ostatnich ośmiu bajtów skrótu SHA1 swojego klucza publicznego.  
  
> [!NOTE]
>  Ta metoda jest tylko dostępne z architekturą .NET Native.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebugMergedAssemblyRecord, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
