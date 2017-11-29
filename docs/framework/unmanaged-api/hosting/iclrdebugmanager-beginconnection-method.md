---
title: Metodo ICLRDebugManager::BeginConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.BeginConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 302b2abfdde7bbccbef51de21233948d042420be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a>Metodo ICLRDebugManager::BeginConnection
Stabilisce una nuova connessione tra l'host e il debugger per associare un elenco di attività con un identificatore e un nome descrittivo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwConnectionId`  
 [in] Identificatore da associare all'elenco attività di common language runtime (CLR).  
  
 `szConnectionName`  
 [in] Un nome descrittivo per associare l'elenco di attività CLR.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`BeginConnection`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|`dwConnectionId`è zero o `BeginConnection` è già stato chiamato utilizzando questo `dwConnectionId` valore, o `szConnectionName` è null.|  
|E_OUTOFMEMORY|Impossibile allocare memoria insufficiente per contenere l'elenco di attività associata alla connessione.|  
  
## <a name="remarks"></a>Note  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fornisce tre metodi, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), e [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), per l'associazione di elenchi di attività con gli identificatori e nomi descrittivi.  
  
> [!IMPORTANT]
>  Questi tre metodi devono essere chiamati in un ordine specifico per ogni set di attività. `BeginConnection`viene chiamato prima di tutto per stabilire una nuova connessione. `SetConnectionTasks`viene chiamato per fornire il set di attività da associare a tale connessione. `EndConnection`Infine viene chiamato per rimuovere l'associazione tra l'elenco di attività e l'identificatore e il nome descrittivo. Tuttavia, le chiamate alle diverse connessioni possono essere nidificate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRDebugManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [EndConnection (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [SetConnectionTasks (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [IHostControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
