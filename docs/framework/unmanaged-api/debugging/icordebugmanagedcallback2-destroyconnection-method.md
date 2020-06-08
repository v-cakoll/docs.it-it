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
ms.openlocfilehash: a3093f33f2220b22b7b4b373f6d79a341abf8c9c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501937"
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
 Un `DestroyConnection` callback verrà generato quando un host chiama [ICLRDebugManager:: ENDCONNECTION](../hosting/iclrdebugmanager-endconnection-method.md) nell'API di [hosting](../hosting/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
