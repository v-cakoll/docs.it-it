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
ms.openlocfilehash: 74ffc5c92402808ae566d7cb014d9d920c384ae8
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804943"
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
 in Identificatore numerico dell'oggetto selezionato <xref:System.AppDomain> .  
  
 `pUnkAppDomainManager`  
 in Puntatore all' <xref:System.AppDomainManager> oggetto implementato dall'host come `IUnknown` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 <xref:System.AppDomainManager>Fornisce all'host un meccanismo per eseguire il bootstrap nel codice gestito e per controllare la creazione e le impostazioni di ciascuna di esse <xref:System.AppDomain> . Il <xref:System.AppDomainManager> viene caricato in ogni <xref:System.AppDomain> quando <xref:System.AppDomain> viene creato. Se si sceglie, CLR notifica all'host che il dominio applicazione è stato creato impostando il valore del `pUnkAppDomainManager` parametro.  
  
 Nell'implementazione del `SetAppDomainManager` metodo, l'host può impostare il nome e il tipo dell'assembly per il gestore del dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [Interfaccia IHostControl](ihostcontrol-interface.md)
