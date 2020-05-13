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
ms.openlocfilehash: 51d34e68851bc6a60d25f643f63d112396abdc4e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209071"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a>Metodo ICorDebugManagedCallback2::CreateConnection
Notifica al debugger che è stata creata una nuova connessione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui è stata creata la connessione  
  
 `dwConnectionId`  
 in ID della nuova connessione.  
  
 `pConnName`  
 in Puntatore al nome della nuova connessione.  
  
## <a name="remarks"></a>Osservazioni  
 Un `CreateConnection` callback verrà attivato in uno dei seguenti casi:  
  
- Quando un debugger si connette a un processo che contiene connessioni. In questo caso, il runtime genererà e invierà un `CreateConnection` evento e un evento [ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) per ogni connessione nel processo.  
  
- Quando un host chiama [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nell' [API di hosting](../hosting/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
