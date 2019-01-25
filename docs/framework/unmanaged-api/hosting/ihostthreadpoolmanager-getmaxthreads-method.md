---
title: Metodo IHostThreadPoolManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 887197af49a402df73005906e539791f6d7f7be4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623859"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>Metodo IHostThreadPoolManager::GetMaxThreads
Ottiene il numero massimo di thread che gestisce l'host contemporaneamente nel pool di thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pdwMaxWorkerThreads`  
 [out] Puntatore al numero massimo di thread che l'host mantiene il pool di thread.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads` stato restituito correttamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR (non è stato caricato in un processo, o Common Language Runtime è in uno stato in cui si non è possibile eseguire codice gestito o un processo di chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non possiede il blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|L'host non fornisce un'implementazione di `GetMaxThreads`.|  
  
## <a name="remarks"></a>Note  
 CLR chiama `GetMaxThreads` per determinare il numero totale di thread nel pool di thread. Il [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) metodo ottiene il numero di thread che non stanno elaborando gli elementi di lavoro. Tutte le richieste di oltre il valore restituito di `pdwMaxWorkerThreads` parametro rimangono in coda fino a quando non diventano disponibili thread.  
  
 Se l'host non fornisce un'implementazione di `GetMaxThreads`, deve restituire un valore HRESULT E_NOTIMPL.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [Metodo GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [Metodo SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [Interfaccia IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
