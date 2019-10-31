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
ms.openlocfilehash: 17fca3e5a2d763277d3a5f9f72e2d35be6fc350c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124646"
---
# <a name="iclrtaskreset-method"></a>Metodo ICLRTask::Reset
Informa il Common Language Runtime (CLR) che l'host ha completato un'attività e consente a CLR di riutilizzare l'istanza di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) corrente per rappresentare un'altra attività.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fFull`  
 [in] `true`, se il runtime deve reimpostare tutti i valori statici correlati ai thread oltre alle informazioni sulla sicurezza e sulle impostazioni locali correlate all'istanza del `ICLRTask` corrente. in caso contrario, `false`.  
  
 Se il valore è `true`, il Runtime reimposta i dati archiviati utilizzando <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`Reset` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata. correttamente|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 CLR può riciclare le istanze di `ICLRTask` create in precedenza per evitare il sovraccarico dovuto alla creazione ripetuta di nuove istanze ogni volta che è necessaria una nuova attività. L'host abilita questa funzionalità chiamando `ICLRTask::Reset` anziché [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) al termine di un'attività. Nell'elenco seguente viene riepilogato il normale ciclo di vita di un'istanza di `ICLRTask`:  
  
1. Il runtime crea una nuova istanza di `ICLRTask`.  
  
2. Il runtime chiama [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) per ottenere un riferimento all'attività host corrente.  
  
3. Il runtime chiama [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) per associare la nuova istanza all'attività host.  
  
4. L'attività viene eseguita e completata.  
  
5. L'host elimina l'attività chiamando `ICLRTask::ExitTask`.  
  
 `Reset` modifica questo scenario in due modi. Nel passaggio 5 precedente, l'host chiama `Reset` per reimpostare l'attività su uno stato pulito, quindi separa l'istanza di `ICLRTask` dalla relativa istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) associata. Se lo si desidera, l'host può memorizzare nella cache anche l'istanza di `IHostTask` per il riutilizzo. Nel passaggio 1, il runtime estrae una `ICLRTask` riciclata dalla cache anziché creare una nuova istanza.  
  
 Questo approccio funziona bene quando l'host dispone anche di un pool di attività di lavoro riutilizzabili. Quando l'host elimina una delle istanze di `IHostTask`, Elimina la `ICLRTask` corrispondente chiamando `ExitTask`.  
  
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
