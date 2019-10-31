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
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133856"
---
# <a name="ihostiocompletionmanager-interface"></a>Interfaccia IHostIoCompletionManager
Fornisce metodi che consentono all'Common Language Runtime (CLR) di interagire con le porte di completamento I/O fornite dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Associa un handle a una porta di completamento di I/O.|  
|[Metodo CloseIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Chiude una porta creata tramite una chiamata precedente a `CreateIoCompletionPort`.|  
|[Metodo CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Richiede che l'host crei una nuova porta di completamento di I/O.|  
|[Metodo GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Ottiene il numero di thread di completamento di I/O che non stanno attualmente elaborando richieste.|  
|[Metodo GetHostOverlappedSize](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Ottiene le dimensioni dei dati personalizzati che l'host intende accodare alle richieste di I/O.|  
|[Metodo GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Ottiene il numero massimo di thread che l'host può allocare alle richieste di I/O del servizio.|  
|[Metodo GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Ottiene il numero minimo di thread fornito dall'host alle richieste di I/O del servizio.|  
|[Metodo InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Fornisce all'host la possibilità di inizializzare tutti i dati personalizzati relativi a una richiesta di I/O.|  
|[Metodo SetCLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Fornisce all'host un puntatore di interfaccia a un'istanza di [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) implementata da CLR.|  
|[Metodo SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Imposta il numero massimo di thread allocati dall'host alle richieste di I/O del servizio.|  
|[Metodo SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Imposta il numero minimo di thread che l'host deve assegnare al completamento I/O.|  
  
## <a name="remarks"></a>Note  
 `IHostIoCompletionManager` corrisponde all'interfaccia `ICLRIoCompletionManager` implementata da CLR. CLR chiama i metodi di `IHostIoCompletionManager` per associare handle alle porte fornite dall'host e l'host chiama i metodi di `ICLRIoCompletionManager` per segnalare il completamento delle richieste di I/O.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
