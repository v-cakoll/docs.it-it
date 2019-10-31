---
title: Metodo IHostSecurityManager::SetThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139490"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a>Metodo IHostSecurityManager::SetThreadToken
Imposta un handle per il thread attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hToken`  
 in Handle per il token da impostare per il thread attualmente in esecuzione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetThreadToken` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `IHostSecurityManager::SetThreadToken` si comporta in modo analogo alla funzione Win32 corrispondente con lo stesso nome, ad eccezione del fatto che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, mentre `IHostSecurityManager::SetThreadToken` può associare un token solo al thread attualmente in esecuzione.  
  
 Il tipo di `HANDLE` non è conforme a COM; ovvero, le relative dimensioni sono specifiche di un sistema operativo e richiedono il marshalling personalizzato. Questo token viene quindi utilizzato solo all'interno del processo, tra CLR e l'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Interfaccia IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
