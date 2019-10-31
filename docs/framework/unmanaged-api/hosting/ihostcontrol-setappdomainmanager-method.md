---
title: Metodo IHostControl::SetAppDomainManager
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: de264135450190fd028eb8cf12017d94cc65ffac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134717"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a>Metodo IHostControl::SetAppDomainManager
Notifica all'host che è stato creato un dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainID`  
 in Identificatore numerico del <xref:System.AppDomain>selezionato.  
  
 `pUnkAppDomainManager`  
 in Puntatore all'oggetto <xref:System.AppDomainManager> che l'host implementa come `IUnknown`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Il <xref:System.AppDomainManager> fornisce all'host un meccanismo per eseguire il bootstrap nel codice gestito e controllare la creazione e le impostazioni di ogni <xref:System.AppDomain>. Il <xref:System.AppDomainManager> viene caricato in ogni <xref:System.AppDomain> quando viene creato il <xref:System.AppDomain>. Se si sceglie, CLR notifica all'host che il dominio applicazione è stato creato impostando il valore del parametro `pUnkAppDomainManager`.  
  
 Nell'implementazione del metodo `SetAppDomainManager`, l'host può impostare il nome e il tipo dell'assembly per il gestore del dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [Interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
