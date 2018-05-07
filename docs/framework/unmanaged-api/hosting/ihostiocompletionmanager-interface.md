---
title: Interfaccia IHostIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 194dcec6ea484e9cd2d3a17093c1eceb16c8f6c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanager-interface"></a>Interfaccia IHostIoCompletionManager
Fornisce metodi che consentono a common language runtime (CLR) per interagire con le porte di completamento i/o fornite dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Associa un handle a una porta di completamento i/o.|  
|[Metodo CloseIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Chiude una porta creata tramite una chiamata precedente a `CreateIoCompletionPort`.|  
|[Metodo CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Richieste all'host di creare una nuova porta di completamento i/o.|  
|[Metodo GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Ottiene il numero di thread di completamento i/o che non stanno elaborando le richieste.|  
|[Metodo GetHostOverlappedSize](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Ottiene le dimensioni dei dati personalizzati, che l'host dovrà accodare alle richieste dei / o.|  
|[Metodo GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Ottiene il numero massimo di thread che l'host è possibile allocare per rispondere alle richieste dei / o.|  
|[Metodo GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Ottiene il numero minimo di thread che l'host fornisce per rispondere alle richieste dei / o.|  
|[Metodo InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Fornisce all'host la possibilità di inizializzare qualsiasi dato personalizzato su una richiesta dei / o.|  
|[Metodo SetCLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Fornisce all'host con un puntatore a interfaccia a un [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) istanza implementata da CLR.|  
|[Metodo SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Imposta il numero massimo di thread che l'host assegnati per rispondere alle richieste dei / o.|  
|[Metodo SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Imposta il numero minimo di thread che l'host deve assegnare fino al completamento dei / o.|  
  
## <a name="remarks"></a>Note  
 `IHostIoCompletionManager` corrisponde alla `ICLRIoCompletionManager` interfaccia implementata da CLR. CLR chiama i metodi di `IHostIoCompletionManager` per associare gli handle per le porte che fornisce l'host e l'host chiama i metodi di `ICLRIoCompletionManager` per segnalare il completamento delle richieste dei / o.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
