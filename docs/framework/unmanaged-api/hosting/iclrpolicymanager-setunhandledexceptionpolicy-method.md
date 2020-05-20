---
title: Metodo ICLRPolicyManager::SetUnhandledExceptionPolicy
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 7fa02c4c79da118543117aada7d1b9cca09c4cae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703395"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a>Metodo ICLRPolicyManager::SetUnhandledExceptionPolicy
Specifica il comportamento del Common Language Runtime (CLR) quando si verifica un'eccezione non gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `policy`  
 in Uno dei valori di [EClrUnhandledException](eclrunhandledexception-enumeration.md) , che indica se il comportamento è impostato da CLR o dall'host.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`SetUnhandledExceptionPolicy`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 Per impostazione predefinita, CLR è il gestore finale per tutte le eccezioni non gestite e il comportamento predefinito prevede la rimozione del processo. L'host può modificare questo comportamento impostando il `policy` valore su eHostDeterminedPolicy. Questo valore consente all'host di implementare il proprio comportamento predefinito, come con le versioni precedenti di CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrUnhandledException](eclrunhandledexception-enumeration.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfaccia ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Interfaccia IHostPolicyManager](ihostpolicymanager-interface.md)
