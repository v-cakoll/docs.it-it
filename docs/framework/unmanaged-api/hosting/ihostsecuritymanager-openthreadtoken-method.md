---
title: Metodo IHostSecurityManager::OpenThreadToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.OpenThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d3b5ec31944b58bec6268de6e54503141880e6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>Metodo IHostSecurityManager::OpenThreadToken
Apre il token di accesso discrezionale associato al thread attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwDesiredAccess`  
 [in] Una maschera di valori di accesso che specificano i tipi di richiesti di accesso per il token del thread. Questi valori sono definiti in Win32 `OpenThreadToken` (funzione). Tipi di accesso richiesti vengono riconciliati con elenco di controllo del token di accesso discrezionale (DACL) per determinare quali tipi di accesso per concedere o negare.  
  
 `bOpenAsSelf`  
 [in] `true` per specificare che il controllo di accesso deve essere effettuato utilizzando il contesto di sicurezza del processo per il thread chiamante. `false` per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza per il thread chiamante. Se il thread rappresenta un client, il contesto di sicurezza può essere di un processo client.  
  
 `phThreadToken`  
 [out] Puntatore al token di accesso appena aperto.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `IHostSecurityManager::OpenThreadToken`si comporta in modo analogo alla funzione Win32 con lo stesso nome, con la differenza che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, mentre `IHostSecurityManager::OpenThreadToken` apre solo il token associato al thread chiamante.  
  
 Il `HANDLE` tipo non è compatibile con COM, ovvero la dimensione è specifica per il sistema operativo e richiede marshalling personalizzato. Di conseguenza, questo token è utilizzato solo all'interno del processo, tra CLR e l'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IHostSecurityContext (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
