---
title: Metodo IHostTaskManager::CallNeedsHostHook
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.CallNeedsHostHook
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0daa122b3576c1a6e6e192a4992549e704721bb4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>Metodo IHostTaskManager::CallNeedsHostHook
Consente all'host di specificare se common language runtime (CLR) può rendere inline la chiamata a una funzione non gestita specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `target`  
 [in] L'indirizzo all'interno del file mappato eseguibile portabile (PE) della funzione non gestita che deve essere chiamato.  
  
 `pbCallNeedsHostHook`  
 [out] Un puntatore a un valore booleano che indica se l'host richiede che la chiamata a essere associata.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Per ottimizzare l'esecuzione di codice, CLR esegue un'analisi di ogni piattaforma richiamo durante la compilazione per determinare se la chiamata può essere resa inline. `CallNeedsHostHook`consente all'host di eseguire l'override di tale decisione richiedendo l'hook una chiamata a una funzione non gestita. Se l'host richiede una funzione hook, il runtime non rende inline la chiamata.  
  
 L'host in genere richiederebbe un hook quando è necessario modificare uno stato a virgola mobile o alla ricezione di notifica che una chiamata sta entrando in uno stato in cui l'host non è possibile tenere delle richieste traccia di memoria e di eventuali blocchi acquisiti. Quando l'host richiede l'hook di chiamata, il runtime notifica all'host le transizioni da e verso codice gestito mediante chiamate al [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), e [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).  
  
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
