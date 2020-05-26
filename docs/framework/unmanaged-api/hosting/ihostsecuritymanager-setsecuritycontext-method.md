---
title: Metodo IHostSecurityManager::SetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: 79ef08ef70ad1132ceacc3e2b997651e57032b9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803815"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a>Metodo IHostSecurityManager::SetSecurityContext
Imposta il contesto di sicurezza del thread attualmente in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `eContextType`  
 in Uno dei valori di [EContextType](econtexttype-enumeration.md) , che indica il tipo di contesto che il Common Language Runtime (CLR) sta inserendo nell'host.  
  
 `ppSecurityContext`  
 out Puntatore all'indirizzo di un nuovo oggetto [IHostSecurityContext](ihostsecuritycontext-interface.md) .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`SetSecurityContext`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR chiama `SetSecurityContext` in diversi scenari. Prima di eseguire i costruttori e i finalizzatori della classe e del modulo, CLR chiama `SetSecurityContext` per proteggere l'host dagli errori di esecuzione. Reimposta quindi il contesto di sicurezza sullo stato originale dopo l'esecuzione del costruttore o del finalizzatore, usando un'altra chiamata a `SetSecurityContext` . Un modello simile si verifica con il completamento di I/O. Se l'host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), il CLR chiama `SetSecurityContext` [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)quando l'host chiama.  
  
 Nei punti asincroni nei thread di lavoro, CLR chiama `SetSecurityContext` all'interno <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o all'interno di [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), a seconda che l'host o CLR implementi il pool di thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [Enumerazione EContextType](econtexttype-enumeration.md)
- [Interfaccia ICLRIoCompletionManager](iclriocompletionmanager-interface.md)
- [Interfaccia IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
- [Interfaccia IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Interfaccia IHostSecurityManager](ihostsecuritymanager-interface.md)
- [Interfaccia IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)
