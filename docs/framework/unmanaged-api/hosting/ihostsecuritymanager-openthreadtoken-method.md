---
title: Metodo IHostSecurityManager::OpenThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68ebfdcd0ef34edec724a044791d05dd48580b12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697485"
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
  
## <a name="parameters"></a>Parametri  
 `dwDesiredAccess`  
 [in] Maschera di valori di accesso che specificano i tipi di richiesti di accesso ai token del thread. Questi valori sono definiti in Win32 `OpenThreadToken` (funzione). I tipi di richiesta di accesso vengono riconciliati con elenco di controllo di accesso discrezionale (DACL) per determinare i tipi di accesso per concedere o negare del token.  
  
 `bOpenAsSelf`  
 [in] `true` per specificare che il controllo di accesso deve essere effettuato utilizzando il contesto di sicurezza del processo per il thread chiamante; `false` per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza per il thread chiamante se stesso. Se il thread è una rappresentazione di un client, il contesto di sicurezza può essere quello di un processo client.  
  
 `phThreadToken`  
 [out] Puntatore al token di accesso appena aperta.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `IHostSecurityManager::OpenThreadToken` si comporta in modo analogo alla funzione Win32 corrispondente con lo stesso nome, ad eccezione del fatto che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, anche se `IHostSecurityManager::OpenThreadToken` apre solo il token associato al thread chiama.  
  
 Il `HANDLE` tipo non è compatibile con COM, vale a dire, la dimensione è specifica per il sistema operativo e richiede il marshalling personalizzato. Di conseguenza, questo token è destinata solo all'interno del processo, tra CLR e l'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
