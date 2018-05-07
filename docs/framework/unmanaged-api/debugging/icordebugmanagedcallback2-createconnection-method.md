---
title: Metodo ICorDebugManagedCallback2::CreateConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7024b8c0682b3351d185e518dd149737beb04bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2createconnection-method"></a>Metodo ICorDebugManagedCallback2::CreateConnection
Notifica al debugger che è stata creata una nuova connessione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pProcess`  
 [in] Un puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui è stata creata la connessione  
  
 `dwConnectionId`  
 [in] L'ID della nuova connessione.  
  
 `pConnName`  
 [in] Un puntatore al nome della nuova connessione.  
  
## <a name="remarks"></a>Note  
 Oggetto `CreateConnection` callback verrà generato in uno dei seguenti casi:  
  
-   Quando un debugger si connette a un processo che contiene le connessioni. In questo caso, il runtime generare e inviare un `CreateConnection` evento e un [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) evento per ogni connessione del processo.  
  
-   Quando un host chiama [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nel [API di Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
