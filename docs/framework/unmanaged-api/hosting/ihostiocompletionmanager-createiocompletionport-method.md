---
title: Metodo IHostIoCompletionManager::CreateIoCompletionPort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CreateIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1942c34b0807b76bbe25aedc60b7b1c6fecc87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a>Metodo IHostIoCompletionManager::CreateIoCompletionPort
Richieste all'host di creare una nuova porta di completamento i/o.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phPort`  
 [out] Puntatore a un handle per la porta di completamento i/o appena creata, oppure 0 (zero), se non è stato possibile creare la porta.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CreateIoCompletionPort`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Memoria insufficiente è disponibile per la risorsa richiesta.|  
  
## <a name="remarks"></a>Note  
 CLR chiama il `CreateIoCompletionPort` metodo per richiedere che l'host crea una nuova porta di completamento i/o. Associa a questa porta mediante una chiamata a operazioni dei / o il [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) metodo. L'host segnala lo stato nuovo a CLR chiamando [ICLRIoCompletionManager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRIoCompletionManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [IHostIoCompletionManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
