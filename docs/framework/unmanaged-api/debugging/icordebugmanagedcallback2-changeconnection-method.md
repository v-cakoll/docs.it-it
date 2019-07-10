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
ms.openlocfilehash: f8a8f84d3dfd8f1e64197078d7e20d2aebef2323
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761216"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>Metodo ICorDebugManagedCallback2::ChangeConnection
Notifica al debugger che è stato modificato il set di attività associate alla connessione specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
- Quando un debugger viene collegato a un processo che contiene le connessioni. In questo caso, il runtime verrà generare e inviare un [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) eventi e un `ChangeConnection` evento per ogni connessione del processo. Oggetto `ChangeConnection` evento viene generato per ogni connessione esistente, indipendentemente dal fatto che set della connessione di attività è stato modificato dopo la creazione.  
  
- Quando un host chiama [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) nel [API Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
 Il debugger deve eseguire l'analisi di tutti i thread del processo per rendere effettive le nuove modifiche.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
