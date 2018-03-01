---
title: Metodo ICLRTask::Reset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8dc37f47fc01d73ff499ef974a2e11345a95286a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskreset-method"></a>Metodo ICLRTask::Reset
Informa common language runtime (CLR), l'host ha completato un'attività che consente di Riutilizzare corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza per rappresentare un'altra attività.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fFull`  
 [in] `true`, se il runtime deve reimpostare tutti i valori statici relativi ai thread oltre alle informazioni di sicurezza e le impostazioni locali relative all'oggetto corrente `ICLRTask` dell'istanza; in caso contrario, `false`.  
  
 Se il valore è `true`, il runtime Reimposta i dati archiviati utilizzando <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Reset`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare la chiamata. correttamente|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 CLR possono essere riciclati creato in precedenza `ICLRTask` istanze per evitare il sovraccarico di più volte la creazione di nuove istanze ogni volta che è necessaria una nuova attività. L'host abilita questa funzionalità chiamando `ICLRTask::Reset` anziché [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) quando un'attività è stata completata. L'elenco seguente riepiloga il normale ciclo di vita di un `ICLRTask` istanza:  
  
1.  Il runtime crea un nuovo `ICLRTask` istanza.  
  
2.  Il runtime chiama [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) per ottenere un riferimento all'attività corrente di host.  
  
3.  Il runtime chiama [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) per associare la nuova istanza di attività dell'host.  
  
4.  L'attività viene eseguita e completata.  
  
5.  L'host elimina l'attività mediante una chiamata `ICLRTask::ExitTask`.  
  
 `Reset`modifica di questo scenario in due modi. Nel passaggio 5, l'host chiama `Reset` per reimpostare l'attività lo stato originario, quindi separa il `ICLRTask` istanza da associato [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza. Se si desidera, l'host può inoltre memorizzare nella cache il `IHostTask` istanza per il riutilizzo. Nel passaggio 1, il ricicla `ICLRTask` dalla cache anziché creare una nuova istanza.  
  
 Questo approccio funziona bene quando l'host dispone anche di un pool di attività di lavoro riutilizzabile. Quando l'host elimina uno dei relativi `IHostTask` istanze, vengono eliminati definitivamente corrispondente `ICLRTask` chiamando `ExitTask`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
