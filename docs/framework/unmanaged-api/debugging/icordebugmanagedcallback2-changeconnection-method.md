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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68288111e3f862cf1364031eaad9c63cf347146f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>Metodo ICorDebugManagedCallback2::ChangeConnection
Notifica al debugger che il set di attività associata alla connessione specificata è stato modificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pProcess`  
 [in] Un puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo che contiene la connessione modificata.  
  
 `dwConnectionId`  
 [in] L'ID di connessione modificata.  
  
## <a name="remarks"></a>Note  
 Oggetto `ChangeConnection` callback verrà generato in uno dei seguenti casi:  
  
-   Quando un debugger si connette a un processo che contiene le connessioni. In questo caso, il runtime generare e inviare un [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) evento e un `ChangeConnection` evento per ogni connessione del processo. Oggetto `ChangeConnection` evento viene generato per ogni connessione esistente, indipendentemente dal fatto che set della connessione di attività è stato modificato rispetto alla creazione.  
  
-   Quando un host chiama [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) nel [API di Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
 Il debugger deve eseguire l'analisi di tutti i thread del processo per rendere effettive le nuove modifiche.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
