---
title: Metodo IHostSecurityManager::SetSecurityContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.SetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c25b8bb0effb4e5e1e61447c74c9729989d04702
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a>Metodo IHostSecurityManager::SetSecurityContext
Imposta il contesto di sicurezza del thread attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `eContextType`  
 [in] Uno del [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valori, che indica il tipo del contesto di common language runtime (CLR) sta fissando nell'host.  
  
 `ppSecurityContext`  
 [out] Un puntatore all'indirizzo di un nuovo [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) oggetto.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetSecurityContext`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 CLR chiama `SetSecurityContext` in diversi scenari. Prima di eseguire i finalizzatori e costruttori di modulo e classi, CLR chiama `SetSecurityContext` per proteggere l'host da errori di esecuzione. Reimposta il contesto di sicurezza allo stato originale dopo l'esecuzione del costruttore o un finalizzatore, con un'altra chiamata a `SetSecurityContext`. Un modello simile si verifica con il completamento dei / o. Se l'host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR chiama `SetSecurityContext` dopo l'host chiama [ICLRIoCompletionManager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).  
  
 In punti asincroni di thread di lavoro, CLR chiama `SetSecurityContext` all'interno di <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o interno [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), a seconda se l'host o CLR implementa il pool di thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ThreadPool?displayProperty=nameWithType>  
 [EContextType (enumerazione)](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [ICLRIoCompletionManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [IHostIoCompletionManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [IHostSecurityContext (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [IHostThreadPoolManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
