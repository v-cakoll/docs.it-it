---
title: Metodo ICLRTaskManager::CreateTask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.CreateTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fa4607232eedd532456d1ffae6bc3d92e42282f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanagercreatetask-method"></a>Metodo ICLRTaskManager::CreateTask
Le richieste in modo esplicito che common language runtime (CLR) creare una nuova attività.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pTask`  
 [out] Un puntatore all'indirizzo di un oggetto appena creato [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), o null, se l'attività non è stato creato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il metodo è stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente è disponibile per l'allocazione della risorsa richiesta.|  
  
## <a name="remarks"></a>Note  
 CLR crea una nuova attività automaticamente al momento dell'inizializzazione, quando il codice utente crea un thread utilizzando tipi di <xref:System.Threading> dello spazio dei nomi, o quando le dimensioni del pool di thread sono aumentata. Crea inoltre attività quando il codice non gestito effettua una chiamata a una funzione gestita.  
  
 `CreateTask`consente all'host di richiedere esplicitamente a CLR di creare una nuova attività. Ad esempio, l'host è possibile richiamare questo metodo per pre-inizializzare le strutture di dati.  
  
> [!IMPORTANT]
>  La nuova attività, viene restituita in uno stato sospeso e rimane sospesa fino a quando l'host chiama in modo esplicito [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
