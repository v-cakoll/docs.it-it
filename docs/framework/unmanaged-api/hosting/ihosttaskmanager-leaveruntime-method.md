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
ms.openlocfilehash: 959cb541013ca0a26557e849874dbb329489d855
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749539"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>Metodo IHostTaskManager::LeaveRuntime
Notifica all'host che l'attività attualmente in esecuzione sta per lasciare common language runtime (CLR) e immettere il codice non gestito.  
  
> [!IMPORTANT]
>  Una chiamata corrispondente al [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione è reinserimento codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `target`  
 [in] L'indirizzo all'interno del file eseguibile portabile con mapping di funzione non gestita da chiamare.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente è disponibile per completare l'allocazione di richiesta.|  
  
## <a name="remarks"></a>Note  
 Le sequenze di chiamate da e verso il codice non gestito possono essere annidate. Ad esempio, l'elenco seguente descrive una situazione ipotetica in cui la sequenza di chiamate a `LeaveRuntime`, [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.  
  
|Operazione|Chiamata di metodo corrispondente|  
|------------|-------------------------------|  
|Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C usando platform invoke.|`IHostTaskManager::LeaveRuntime`|  
|La funzione non gestita C chiama un metodo in una DLL gestita scritta in C#.|`IHostTaskManager::ReverseEnterRuntime`|  
|Gestito C# funzione chiama un'altra funzione non gestita scritta in C, anche usando il platform invoke.|`IHostTaskManager::LeaveRuntime`|  
|La seconda funzione non gestita restituisce l'esecuzione di C# (funzione).|`IHostTaskManager::EnterRuntime`|  
|Il C# funzione restituisce l'esecuzione per la prima funzione non gestita.|`IHostTaskManager::ReverseLeaveRuntime`|  
|La funzione non gestita prima restituisce l'esecuzione del programma Visual Basic.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
