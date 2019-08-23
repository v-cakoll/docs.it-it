---
title: Metodo IHostTask::SetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533e3d715b46b4ef6d473795a010fa3ad297ded2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913757"
---
# <a name="ihosttasksetpriority-method"></a>Metodo IHostTask::SetPriority
Richiede che l'host modifichi il livello di priorità del thread per l'attività rappresentata dall'istanza corrente di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `newPriority`  
 in Integer che rappresenta il valore di priorità del thread richiesto per l'attività rappresentata dall' `IHostTask` istanza corrente.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|DESCRIZIONE|  
|-------------|-----------------|  
|S_OK|`SetPriority`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Ai thread viene concesso il tempo di elaborazione utilizzando un sistema Round Robin che è parzialmente basato sul livello di priorità di un thread. `SetPriority`consente a CLR di impostare il livello di priorità del thread per l'attività corrente. Sono supportati `newPriority` i valori seguenti.  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_IDLE  
  
- THREAD_PRIORITY_LOWEST  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
 CLR chiama `SetPriority` quando il valore <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> di viene modificato dal codice utente. Un host può definire i propri algoritmi per l'assegnazione della priorità del thread ed è libero di ignorare questa richiesta.  
  
> [!NOTE]
> `SetPriority`non indica se il livello di priorità del thread è stato modificato. Chiamare [IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) per determinare il valore del livello di priorità del thread dell'attività.  
  
 I valori del livello di priorità dei thread sono `SetThreadPriority` definiti dalla funzione Win32. Per ulteriori informazioni sulla priorità dei thread, vedere la documentazione della piattaforma Windows.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread>
- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Metodo GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
