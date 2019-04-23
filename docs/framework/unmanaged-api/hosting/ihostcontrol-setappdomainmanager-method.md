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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118e75cb28a4e474427f35f4516ec41850ebe99f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150865"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a>Metodo IHostControl::SetAppDomainManager
Notifica all'host che è stato creato un dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwAppDomainID`  
 [in] L'identificatore numerico dell'oggetto selezionato <xref:System.AppDomain>.  
  
 `pUnkAppDomainManager`  
 [in] Un puntatore per il <xref:System.AppDomainManager> oggetto che implementa l'host come `IUnknown`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 Il <xref:System.AppDomainManager> fornisce un meccanismo per eseguire il bootstrap in codice gestito e per controllare la creazione e configurazione di ciascun host <xref:System.AppDomain>. Il <xref:System.AppDomainManager> viene caricato in ognuno <xref:System.AppDomain> quando che <xref:System.AppDomain> viene creato. Se sceglie, CLR notifica all'host che creato il dominio dell'applicazione impostando il valore della `pUnkAppDomainManager` parametro.  
  
 Nella sua implementazione del `SetAppDomainManager` metodo, l'host può impostare il nome dell'assembly e il tipo per il gestore del dominio applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [Interfaccia IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
