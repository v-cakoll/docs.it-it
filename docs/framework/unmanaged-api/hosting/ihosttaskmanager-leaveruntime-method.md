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
ms.openlocfilehash: deaebbce3b9b8a26bf9668b826a6818dba94dcc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501379"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>Metodo IHostTaskManager::LeaveRuntime
Notifica all'host che l'attività attualmente in esecuzione sta per uscire dalla Common Language Runtime (CLR) e immettere codice non gestito.  
  
> [!IMPORTANT]
> Una chiamata corrispondente a [IHostTaskManager:: EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifica all'host che l'attività attualmente in esecuzione sta reimmettendo il codice gestito.  
  
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
  
## <a name="remarks"></a>Osservazioni  
 Le sequenze di chiamate da e verso codice non gestito possono essere nidificate. L'elenco seguente, ad esempio, descrive una situazione ipotetica in cui la sequenza di chiamate a `LeaveRuntime` , [IHostTaskManager:: ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)e `IHostTaskManager::EnterRuntime` consente all'host di identificare i livelli annidati.  
  
|Azione|Chiamata al metodo corrispondente|  
|------------|-------------------------------|  
|Un eseguibile Visual Basic gestito chiama una funzione non gestita scritta in C utilizzando platform invoke.|`IHostTaskManager::LeaveRuntime`|  
|La funzione C non gestita chiama un metodo in una DLL gestita scritta in C#.|`IHostTaskManager::ReverseEnterRuntime`|  
|La funzione C# gestita chiama un'altra funzione non gestita scritta in C, usando anche platform invoke.|`IHostTaskManager::LeaveRuntime`|  
|La seconda funzione non gestita restituisce l'esecuzione alla funzione C#.|`IHostTaskManager::EnterRuntime`|  
|La funzione C# restituisce l'esecuzione alla prima funzione non gestita.|`IHostTaskManager::ReverseLeaveRuntime`|  
|La prima funzione non gestita restituisce l'esecuzione al programma Visual Basic.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](ihosttask-interface.md)
- [Interfaccia IHostTaskManager](ihosttaskmanager-interface.md)
