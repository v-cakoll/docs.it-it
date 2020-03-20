---
title: Metodo ICLRRuntimeHost::ExecuteInAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176422"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>Metodo ICLRRuntimeHost::ExecuteInAppDomain
Specifica l'oggetto <xref:System.AppDomain> in cui eseguire il codice gestito specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `AppDomainId`  
 [in] ID numerico <xref:System.AppDomain> dell'oggetto in cui eseguire il metodo specificato.  
  
 `pCallback`  
 [in] Puntatore alla funzione da eseguire <xref:System.AppDomain>all'interno dell'oggetto specificato.  
  
 `cookie`  
 [in] Puntatore alla memoria opaca allocata dal chiamante. Questo parametro viene passato da Common Language Runtime (CLR) al callback di dominio. Non è memoria heap gestita dal runtime; sia l'allocazione che la durata di questa memoria sono controllate dal chiamante.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain`restituito con successo.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 `ExecuteInAppDomain`consente all'host di esercitare il controllo su cui gestito <xref:System.AppDomain> il metodo gestito specificato deve essere eseguito in. È possibile ottenere il valore dell'identificatore di un dominio <xref:System.AppDomain.Id%2A> applicazione, che corrisponde al valore della proprietà, chiamando [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
