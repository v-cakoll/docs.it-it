---
title: Metodo ICLRTask::SwitchIn
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: fbfd44c8e20bc75638d6356fe405f02790da8ac7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124610"
---
# <a name="iclrtaskswitchin-method"></a>Metodo ICLRTask::SwitchIn
Notifica al Common Language Runtime (CLR) che l'attività rappresentata dall'istanza corrente di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) è ora in uno stato eseguibile.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadHandle`  
 in Handle per il thread fisico in cui è in esecuzione l'attività rappresentata dall'istanza di `ICLRTask` corrente.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SwitchIn` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|`SwitchIn` stata chiamata senza una chiamata precedente al [metodo di commutazione](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).|  
  
## <a name="remarks"></a>Note  
 Il parametro `threadHandle` rappresenta un handle per il thread del sistema operativo in cui è stata pianificata l'attività rappresentata dall'istanza di `ICLRTask` corrente. Se si è verificata una rappresentazione in questo thread, è necessario chiamare [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) prima di passare all'attività.  
  
> [!NOTE]
> Una chiamata a `SwitchIn` senza una precedente chiamata a `SwitchOut` ha esito negativo con un valore HRESULT di HOST_E_INVALIDOPERATION.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
