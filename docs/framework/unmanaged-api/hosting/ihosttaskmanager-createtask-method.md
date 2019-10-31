---
title: Metodo IHostTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: 16916d62a528222db952a1d29dc7c69de2352191
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133118"
---
# <a name="ihosttaskmanagercreatetask-method"></a>Metodo IHostTaskManager::CreateTask
Richiede che l'host crei una nuova attività.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `stacksize`  
 in Dimensioni richieste, in byte, dello stack richiesto o 0 (zero) per le dimensioni predefinite.  
  
 `pStartAddress`  
 in Puntatore alla funzione che deve essere eseguita dall'attività.  
  
 `pParameter`  
 in Puntatore ai dati utente da passare alla funzione oppure null se la funzione non accetta parametri.  
  
 `ppTask`  
 out Puntatore all'indirizzo di un'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) creato dall'host oppure null se non è possibile creare l'attività. L'attività rimane in stato sospeso fino a quando non viene avviata in modo esplicito da una chiamata a [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CreateTask` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente per creare l'attività richiesta.|  
  
## <a name="remarks"></a>Note  
 CLR chiama `CreateTask` per richiedere che l'host crei una nuova attività. L'host restituisce un puntatore a interfaccia a un'istanza di `IHostTask`. L'attività restituita deve rimanere sospesa fino a quando non viene avviata in modo esplicito da una chiamata a `IHostTask::Start`.  
  
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
