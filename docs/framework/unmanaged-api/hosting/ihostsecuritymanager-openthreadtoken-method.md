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
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176266"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>Metodo IHostSecurityManager::OpenThreadToken
Apre il token di accesso discrezionale associato al thread attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwDesiredAccess`  
 [in] Maschera di valori di accesso che specificano i tipi di accesso richiesti al token del thread. Questi valori sono definiti nella `OpenThreadToken` funzione Win32.These values are defined in the Win32 function. I tipi di accesso richiesti vengono riconciliati con l'elenco di controllo di accesso discrezionale (DACL) del token per determinare quali tipi di accesso concedere o negare.  
  
 `bOpenAsSelf`  
 [in] `true` per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza del processo per il thread chiamante; `false` per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza per il thread chiamante stesso. Se il thread rappresenta un client, il contesto di sicurezza può essere quello di un processo client.  
  
 `phThreadToken`  
 [fuori] Puntatore al token di accesso appena aperto.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`restituito con successo.|  
|HOST_E_CLRNOTAVAILABLE|Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `IHostSecurityManager::OpenThreadToken`si comporta in modo simile alla funzione Win32 corrispondente con lo stesso nome, ad eccezione del fatto che `IHostSecurityManager::OpenThreadToken` la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, mentre apre solo il token associato al thread chiamante.  
  
 Il `HANDLE` tipo non è conforme a COM, ovvero la sua dimensione è specifica del sistema operativo e richiede il marshalling personalizzato. Pertanto, questo token è per l'utilizzo solo all'interno del processo, tra CLR e l'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
