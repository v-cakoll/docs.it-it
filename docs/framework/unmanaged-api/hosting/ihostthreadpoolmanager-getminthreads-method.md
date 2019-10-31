---
title: Metodo IHostThreadPoolManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
ms.openlocfilehash: ce1abb75c5135a9bb23f1ad2d2acbd40d9111b14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122063"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a>Metodo IHostThreadPoolManager::GetMinThreads
Ottiene il numero minimo di thread inattivi gestiti dall'host nel pool di thread in attesa di richieste.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `MinThreads`  
 out Puntatore al numero minimo di thread di lavoro inattivi attualmente gestiti dall'host.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|`GetMinThreads` ha restituito un esito positivo.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|L'host non fornisce un'implementazione di `GetMinThreads`.|  
  
## <a name="remarks"></a>Note  
 L'host non deve fornire un'implementazione di `GetMinThreads`. In questo caso, deve restituire un valore HRESULT di E_NOTIMPL.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [Metodo GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [Metodo SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [Interfaccia IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
