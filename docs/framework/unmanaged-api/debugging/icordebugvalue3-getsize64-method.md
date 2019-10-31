---
title: Metodo ICorDebugValue3::GetSize64
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 72a1b6fdc40f3169500d8cf3b3028315106ecc69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140236"
---
# <a name="icordebugvalue3getsize64-method"></a>Metodo ICorDebugValue3::GetSize64
Ottiene la dimensione in byte di questo oggetto [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 pSize  
 out Puntatore alla dimensione, in byte, dell'oggetto.  
  
## <a name="remarks"></a>Note  
 Se il tipo di questo valore è un tipo di riferimento, questo metodo restituisce le dimensioni del puntatore anziché le dimensioni dell'oggetto.  
  
 Il metodo `ICorDebugValue3::GetSize` differisce dal metodo [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) nel tipo del parametro di output. In [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), il parametro di output è un `ULONG32`; in `ICorDebugValue3::GetSize`, si tratta di un `ULONG64`. Ciò consente all'interfaccia [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) di segnalare le dimensioni delle matrici che superano 2 GB.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
