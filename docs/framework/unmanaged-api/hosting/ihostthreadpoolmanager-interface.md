---
title: Interfaccia IHostThreadPoolManager
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122077"
---
# <a name="ihostthreadpoolmanager-interface"></a>Interfaccia IHostThreadPoolManager
Fornisce metodi che consentono al Common Language Runtime (CLR) di configurare il pool di thread e di accodare gli elementi di lavoro al pool di thread.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Ottiene il numero di thread nel pool di thread che non stanno attualmente elaborando elementi di lavoro.|  
|[Metodo GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Ottiene il numero massimo di thread che l'host gestisce simultaneamente nel pool di thread.|  
|[Metodo GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Ottiene il numero minimo di thread inattivi gestiti dall'host in previsione di richieste.|  
|[Metodo QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Accoda una funzione per l'esecuzione e fornisce un oggetto contenente i dati che devono essere utilizzati dalla funzione.|  
|[Metodo SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Imposta il numero massimo di thread che l'host è in grado di gestire nel pool di thread.|  
|[Metodo SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Imposta il numero minimo di thread inattivi che l'host deve gestire in previsione di richieste.|  
  
## <a name="remarks"></a>Note  
 L'host non è necessario per configurare il pool di thread utilizzando i valori specificati nelle chiamate ai metodi `SetMaxThreads` e `SetMinThreads`. In questo caso, l'host deve restituire un valore HRESULT di E_NOTIMPL da questi metodi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
