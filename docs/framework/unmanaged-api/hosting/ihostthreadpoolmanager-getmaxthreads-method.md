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
ms.openlocfilehash: efbfa310c90f48c99219cb185f090a1b854949a2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842283"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>Metodo IHostThreadPoolManager::GetMaxThreads
Ottiene il numero massimo di thread che l'host gestisce simultaneamente nel pool di thread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwMaxWorkerThreads`  
 out Puntatore al numero massimo di thread gestiti dall'host nel pool di thread.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads`la restituzione è riuscita.|  
|HOST_E_CLRNOTAVAILABLE|Il Common Language Runtime (CLR (non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.|  
|HOST_E_TIMEOUT|Timeout della chiamata.|  
|HOST_E_NOT_OWNER|Il chiamante non è il proprietario del blocco.|  
|HOST_E_ABANDONED|Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo. Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|L'host non fornisce un'implementazione di `GetMaxThreads` .|  
  
## <a name="remarks"></a>Osservazioni  
 CLR chiama `GetMaxThreads` per determinare il numero totale di thread nel pool di thread. Il metodo [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) ottiene il numero di thread che attualmente non elaborano elementi di lavoro. Tutte le richieste sopra il valore restituito del `pdwMaxWorkerThreads` parametro rimangono accodate fino a quando i thread diventano disponibili.  
  
 Se l'host non fornisce un'implementazione di `GetMaxThreads` , deve restituire un valore HRESULT pari a E_NOTIMPL.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [Metodo GetMinThreads](ihostthreadpoolmanager-getminthreads-method.md)
- [Metodo SetMaxThreads](ihostthreadpoolmanager-setmaxthreads-method.md)
- [Interfaccia IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)
