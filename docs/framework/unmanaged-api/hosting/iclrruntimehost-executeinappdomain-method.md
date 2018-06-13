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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96352ec5eaba67489dbef999925c56475611746c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435968"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>Metodo ICLRRuntimeHost::ExecuteInAppDomain
Specifica il <xref:System.AppDomain> in cui eseguire il codice gestito specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `AppDomainId`  
 [in] ID numerico del <xref:System.AppDomain> in cui eseguire il metodo specificato.  
  
 `pCallback`  
 [in] Un puntatore alla funzione da eseguire all'interno specificato <xref:System.AppDomain>.  
  
 `cookie`  
 [in] Puntatore alla memoria allocata dal chiamante opaco. Questo parametro viene passato da common language runtime (CLR) per il callback di dominio. Non è la memoria heap gestito di runtime. sia l'allocazione e la durata della memoria sono controllate dal chiamante.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Note  
 `ExecuteInAppDomain` consente all'host esercitare un controllo su cui gestiti <xref:System.AppDomain> il metodo gestito specificato deve essere eseguito nel. È possibile ottenere il valore dell'identificatore di un dominio dell'applicazione, che corrisponde al valore del <xref:System.AppDomain.Id%2A> proprietà chiamando [GetCurrentAppDomainId (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
