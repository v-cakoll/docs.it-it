---
title: Metodo ICorDebugManagedCallback2::ChangeConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 2c6ed14f9238d653b15d26dec9d954c05238817c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213452"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>Metodo ICorDebugManagedCallback2::ChangeConnection
Notifica al debugger che è stato modificato il set di attività associato alla connessione specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo contenente la connessione modificata.  
  
 `dwConnectionId`  
 in ID della connessione modificata.  
  
## <a name="remarks"></a>Osservazioni  
 Un `ChangeConnection` callback verrà attivato in uno dei seguenti casi:  
  
- Quando un debugger si connette a un processo che contiene connessioni. In questo caso, il runtime genererà e invierà un evento [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) e un `ChangeConnection` evento per ogni connessione nel processo. Un `ChangeConnection` evento viene generato per tutte le connessioni esistenti, indipendentemente dal fatto che il set di attività della connessione sia stato modificato dopo la creazione.  
  
- Quando un host chiama [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) nell' [API di hosting](../hosting/index.md).  
  
 Il debugger deve analizzare tutti i thread del processo per individuare le nuove modifiche.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
