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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92097cdf735630f3537296f188bd83ea8162add2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ihostthreadpoolmanager-interface"></a>Interfaccia IHostThreadPoolManager
Fornisce metodi che consentono di common language runtime (CLR) per configurare il pool di thread e per accodare gli elementi di lavoro al pool di thread.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Ottiene il numero di thread nel pool di thread che non stanno elaborando gli elementi di lavoro.|  
|[Metodo GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Ottiene il numero massimo di thread gestiti dall'host contemporaneamente nel pool di thread.|  
|[Metodo GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Ottiene il numero minimo di thread inattivi gestiti dall'host prima di richieste.|  
|[Metodo QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Accoda una funzione per l'esecuzione e fornisce un oggetto contenente dati da utilizzare per la funzione.|  
|[Metodo SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Imposta il numero massimo di thread che l'host può mantenere nel pool di thread.|  
|[Metodo SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Imposta il numero minimo di thread inattivi che l'host devono essere conservati in previsione delle richieste.|  
  
## <a name="remarks"></a>Note  
 L'host non è necessario configurare il pool di thread utilizzando i valori specificati in chiamate al `SetMaxThreads` e `SetMinThreads` metodi. In questo caso, l'host deve restituire un valore HRESULT di E_NOTIMPL da questi metodi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
