---
title: Metodo IHostSecurityManager::GetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176253"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a>Metodo IHostSecurityManager::GetSecurityContext
Ottiene [l'oggetto iHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) richiesto dall'host.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `eContextType`  
 [in] Uno dei valori [di EContextType,](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) che indica il tipo di contesto di sicurezza da restituire.  
  
 `ppSecurityContext`  
 [fuori] Indirizzo di un puntatore `IHostSecurityContext` `eContextType`a interfaccia all'oggetto di .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetSecurityContext`restituito con successo.|  
|HOST_E_CLRNOTAVAILABLE|Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Un host può controllare tutto l'accesso al codice ai token di thread da CLR e dal codice utente. Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate attraverso operazioni asincrone o punti di codice con accesso al codice limitato. `IHostSecurityContext`incapsula queste informazioni sul contesto di sicurezza, che è opaco per CLR. CLR acquisisce queste informazioni e le sposta tra l'invio di elementi di lavoro del pool di thread, l'esecuzione del finalizzatore e la costruzione di moduli e classi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [Interfaccia IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Interfaccia IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
