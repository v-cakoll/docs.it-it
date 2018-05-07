---
title: Metodo ICLRPolicyManager::SetActionOnTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc1d16a2d57fea27c1c26fc55fbbfa9b74c25495
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a>Metodo ICLRPolicyManager::SetActionOnTimeout
Specifica l'azione di criteri che Common language runtime (CLR) deve eseguire quando il timeout dell'operazione specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `operation`  
 [in] Uno del [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica l'operazione per cui si desidera specificare l'azione di timeout. Sono supportati i seguenti valori:  
  
-   OPR_AppDomainUnload  
  
-   OPR_ProcessExit  
  
-   OPR_ThreadRudeAbortInCriticalRegion  
  
-   OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `action`  
 [in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione dei criteri da eseguire quando il timeout dell'operazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetActionOnTimeout` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non dispone del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Non è possibile impostare un timeout per l'oggetto specificato `operation`, o è stato specificato un valore non valido per `operation`.|  
  
## <a name="remarks"></a>Note  
 Il valore di timeout può essere il timeout predefinito in CLR, o un valore specificato dall'host in una chiamata al [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) metodo.  
  
 Non tutti i valori di azione criteri possono essere specificati come il comportamento di timeout per le operazioni CLR. `SetActionOnTimeout` è in genere usati solo per l'escalation di comportamento. Ad esempio, un host può specificare che le interruzioni di thread deve essere trasformata nelle interruzioni di thread, ma non è possibile specificare l'opposto. La tabella seguente descrive validi `action` i valori del parametro valido `operation` valori.  
  
|Valore per `operation`|Valori validi per `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-eRudeAbortThread<br />-eUnloadAppDomain<br />-eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />-eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
|OPR_ProcessExit|-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazione EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [Enumerazione EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfaccia ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
