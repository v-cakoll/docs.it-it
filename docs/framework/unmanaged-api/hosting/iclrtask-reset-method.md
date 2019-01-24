---
title: Metodo ICLRTask::Reset
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f4e25cfabbf18a9f0733d245259d9bb8f9c7757
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715544"
---
# <a name="iclrtaskreset-method"></a>Metodo ICLRTask::Reset
Indica a common language runtime (CLR) che l'host ha completato un'attività e consente a CLR di riutilizzare l'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) per rappresentare un'altra attività.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fFull`  
 [in] `true`, se il runtime deve reimpostare tutti i valori relativi ai thread statici oltre alle informazioni di sicurezza e le impostazioni locali relative all'oggetto corrente `ICLRTask` dell'istanza; in caso contrario, `false`.  
  
 Se il valore è `true`, il runtime Reimposta i dati archiviati mediante <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Reset` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare la chiamata. successfully|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 CLR possono essere riciclati creato in precedenza `ICLRTask` istanze per evitare l'overhead di creazione più volte nuove istanze ogni volta che necessaria una nuova attività. L'host abilita questa funzionalità chiamando `ICLRTask::Reset` invece di [ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) quando è stata completata un'attività. L'elenco seguente riepiloga il normale ciclo di vita di un `ICLRTask` istanza:  
  
1.  Il runtime crea un nuovo `ICLRTask` istanza.  
  
2.  Il runtime chiama [GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) per ottenere un riferimento all'attività host corrente.  
  
3.  Il runtime chiama [SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) per associare la nuova istanza di attività dell'host.  
  
4.  L'attività viene eseguita e completata.  
  
5.  L'host elimina le attività chiamando `ICLRTask::ExitTask`.  
  
 `Reset` Modifica questo scenario in due modi. Nel passaggio 5 precedente, l'host chiama `Reset` reimpostare l'attività a uno stato originario e quindi consente di disaccoppiare il `ICLRTask` istanza da essa associati [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza. Se si desidera, può anche memorizzare nella cache dell'host di `IHostTask` istanza per il riutilizzo. Nel passaggio 1 precedente, il ricicla `ICLRTask` dalla cache invece di crearne una nuova istanza.  
  
 Questo approccio funziona bene quando l'host ha anche un pool di attività di lavoro riutilizzabile. Quando l'host elimina uno dei relativi `IHostTask` istanze, vengono eliminati definitivamente corrispondente `ICLRTask` chiamando `ExitTask`.  
  
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
