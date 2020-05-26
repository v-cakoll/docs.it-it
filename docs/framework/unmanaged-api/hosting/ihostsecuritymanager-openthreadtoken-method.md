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
ms.openlocfilehash: 85c7308f794929d753b50f58f69168f67a31cb85
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803880"
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
 in Maschera dei valori di accesso che specificano i tipi di accesso richiesti al token del thread. Questi valori sono definiti nella funzione Win32 `OpenThreadToken` . I tipi di accesso richiesti vengono riconciliati rispetto all'elenco di controllo di accesso discrezionale (DACL) del token per determinare i tipi di accesso da concedere o negare.  
  
 `bOpenAsSelf`  
 [in] `true` per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza del processo per il thread chiamante. `false`per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza per il thread chiamante stesso. Se il thread sta rappresentando un client, il contesto di sicurezza può essere quello di un processo client.  
  
 `phThreadToken`  
 out Puntatore al token di accesso appena aperto.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `IHostSecurityManager::OpenThreadToken`si comporta in modo analogo alla funzione Win32 corrispondente con lo stesso nome, ad eccezione del fatto che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, mentre `IHostSecurityManager::OpenThreadToken` apre solo il token associato al thread chiamante.  
  
 Il `HANDLE` tipo non è conforme a com, ovvero le sue dimensioni sono specifiche del sistema operativo e richiede il marshalling personalizzato. Questo token viene quindi utilizzato solo all'interno del processo, tra CLR e l'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Interfaccia IHostSecurityManager](ihostsecuritymanager-interface.md)
