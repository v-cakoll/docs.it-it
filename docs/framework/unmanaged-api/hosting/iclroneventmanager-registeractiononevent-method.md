---
title: Metodo ICLROnEventManager::RegisterActionOnEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager.RegisterActionOnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ef99527abc7ca33e1176958a590483f34556a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a>Metodo ICLROnEventManager::RegisterActionOnEvent
Registra un puntatore di callback per l'evento specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `event`  
 [in] Uno del [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valori, che indica l'evento per il quale registrare il puntatore di callback descritto da `pAction`.  
  
 `pAction`  
 [in] Un puntatore a un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) oggetto che viene chiamato quando viene generato l'evento registrato.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`RegisterActionOnEvent`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 L'host può registrare callback per uno o entrambi i tipi di due eventi descritti dal `EClrEvent`. L'host ottiene il `ICLROnEventManager` interfaccia chiamando il [ICLRControl::](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metodo.  
  
> [!NOTE]
>  Gli eventi che `RegisterActionOnEvent` registri possono essere generati più volte da thread diversi per segnalare uno scaricamento o la disattivazione di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazione EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [IActionOnCLREvent (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [ICLRControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLROnEventManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
