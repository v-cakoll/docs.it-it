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
ms.openlocfilehash: 0b8e7dfbe377e60b548003af10fb11392b514030
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703447"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a>Metodo ICLRPolicyManager::SetActionOnTimeout
Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica il timeout dell'operazione specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `operation`  
 in Uno dei valori di [EClrOperation](eclroperation-enumeration.md) , che indica l'operazione per la quale specificare l'azione di timeout. Sono supportati i valori seguenti:  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `action`  
 in Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) , che indica l'azione del criterio da intraprendere quando si verifica il timeout dell'operazione.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`SetActionOnTimeout`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Non è possibile impostare un timeout per l'oggetto specificato `operation` oppure è stato fornito un valore non valido per `operation` .|  
  
## <a name="remarks"></a>Osservazioni  
 Il valore di timeout può essere il timeout predefinito impostato da CLR o un valore specificato dall'host in una chiamata al metodo [ICLRPolicyManager::](iclrpolicymanager-settimeout-method.md) SetValue.  
  
 Non tutti i valori dell'azione del criterio possono essere specificati come comportamento di timeout per le operazioni CLR. `SetActionOnTimeout`viene in genere utilizzato solo per l'escalation del comportamento. Un host può, ad esempio, specificare che le interruzioni dei thread vengano trasformate in interruzioni di thread rude, ma non è possibile specificare l'opposto. Nella tabella seguente vengono descritti i `action` valori validi per i `operation` valori validi.  
  
|Valore per`operation`|Valori validi per`action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|- eRudeAbortThread<br />-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ProcessExit|- eExitProcess<br />- eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrOperation](eclroperation-enumeration.md)
- [Enumerazione EPolicyAction](epolicyaction-enumeration.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
