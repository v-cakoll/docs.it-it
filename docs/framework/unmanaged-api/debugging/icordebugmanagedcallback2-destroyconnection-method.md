---
title: Metodo ICorDebugManagedCallback2::DestroyConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: c5527f3bd0b04857a1ebc520016b81ddbe3c23f8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208889"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a>Metodo ICorDebugManagedCallback2::DestroyConnection
Notifica al debugger che la connessione specificata è stata terminata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo contenente la connessione distrutta.  
  
 `dwConnectionId`  
 in ID della connessione distrutta.  
  
## <a name="remarks"></a>Osservazioni  
 Un `DestroyConnection` callback verrà generato quando un host chiama [ICLRDebugManager:: ENDCONNECTION](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) nell'API di [hosting](../hosting/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
