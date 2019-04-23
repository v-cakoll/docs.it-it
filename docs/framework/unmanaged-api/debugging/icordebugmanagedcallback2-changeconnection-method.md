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
ms.openlocfilehash: b4eeecc22db5786f66b3d484b521989e71817d8e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185042"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>Metodo ICorDebugManagedCallback2::ChangeConnection
Notifica al debugger che è stato modificato il set di attività associate alla connessione specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 [in] Un puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo che contiene la connessione modificata.  
  
 `dwConnectionId`  
 [in] L'ID della connessione in cui è stato modificato.  
  
## <a name="remarks"></a>Note  
 Oggetto `ChangeConnection` callback verrà generato in entrambi i casi seguenti:  
  
-   Quando un debugger viene collegato a un processo che contiene le connessioni. In questo caso, il runtime verrà generare e inviare un [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) eventi e un `ChangeConnection` evento per ogni connessione del processo. Oggetto `ChangeConnection` evento viene generato per ogni connessione esistente, indipendentemente dal fatto che set della connessione di attività è stato modificato dopo la creazione.  
  
-   Quando un host chiama [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) nel [API Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
 Il debugger deve eseguire l'analisi di tutti i thread del processo per rendere effettive le nuove modifiche.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
