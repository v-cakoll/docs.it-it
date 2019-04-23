---
title: Metodo ICLRTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8833daa9cd385a1a76c5b706f15a76bb15139b84
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079682"
---
# <a name="iclrtaskmanagercreatetask-method"></a>Metodo ICLRTaskManager::CreateTask
Le richieste in modo esplicito che common language runtime (CLR) creare una nuova attività.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pTask`  
 [out] Un puntatore all'indirizzo di un oggetto appena creato [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), oppure null se non è stato possibile creare l'attività.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il metodo è stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente è disponibile per allocare la risorsa richiesta.|  
  
## <a name="remarks"></a>Note  
 CLR crea una nuova attività automaticamente al momento dell'inizializzazione, quando il codice utente crea un thread usando i tipi nel <xref:System.Threading> dello spazio dei nomi, oppure quando sono aumentata le dimensioni del pool di thread. Crea anche le attività quando il codice non gestito effettua una chiamata di una funzione gestita.  
  
 `CreateTask` consente all'host eseguire una richiesta esplicita che Common Language Runtime crea una nuova attività. Ad esempio, l'host può richiamare questo metodo per preinizializzare strutture di dati.  
  
> [!IMPORTANT]
>  La nuova attività viene restituita in uno stato sospeso e rimane sospesa fino a quando l'host chiama in modo esplicito [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
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
