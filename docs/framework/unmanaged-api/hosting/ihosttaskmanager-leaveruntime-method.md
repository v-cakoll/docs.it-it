---
title: Metodo IHostTaskManager::LeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b2e8e636915b3921fcd727fc78a3fb18fc69104
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959032"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>Metodo IHostTaskManager::LeaveRuntime
Notifica all'host che l'attività attualmente in esecuzione sta per uscire dalla Common Language Runtime (CLR) e immettere codice non gestito.  
  
> [!IMPORTANT]
> Una chiamata corrispondente a [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione sta reimmettendo il codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `target`  
 in Indirizzo all'interno del file eseguibile portatile mappato della funzione non gestita da chiamare.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|La memoria disponibile non è sufficiente per completare l'allocazione richiesta.|  
  
## <a name="remarks"></a>Note  
 Le sequenze di chiamate da e verso codice non gestito possono essere nidificate. L'elenco seguente, ad esempio, descrive una situazione ipotetica in cui la sequenza di `LeaveRuntime`chiamate a, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.  
  
|Azione|Chiamata al metodo corrispondente|  
|------------|-------------------------------|  
|Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C utilizzando platform invoke.|`IHostTaskManager::LeaveRuntime`|  
|La funzione C non gestita chiama un metodo in una DLL gestita scritta in C#.|`IHostTaskManager::ReverseEnterRuntime`|  
|La funzione C# gestita chiama un'altra funzione non gestita scritta in C, usando anche Platform Invoke.|`IHostTaskManager::LeaveRuntime`|  
|La seconda funzione non gestita restituisce l' C# esecuzione alla funzione.|`IHostTaskManager::EnterRuntime`|  
|La C# funzione restituisce l'esecuzione alla prima funzione non gestita.|`IHostTaskManager::ReverseLeaveRuntime`|  
|La prima funzione non gestita restituisce l'esecuzione al programma Visual Basic.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
