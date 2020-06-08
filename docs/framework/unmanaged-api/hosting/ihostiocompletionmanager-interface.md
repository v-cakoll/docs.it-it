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
ms.openlocfilehash: 095872f8d4bd4f7d3351b8b3e3f8f8445b615cd8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501537"
---
# <a name="ihostiocompletionmanager-interface"></a>Interfaccia IHostIoCompletionManager
Fornisce metodi che consentono all'Common Language Runtime (CLR) di interagire con le porte di completamento I/O fornite dall'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo bind](ihostiocompletionmanager-bind-method.md)|Associa un handle a una porta di completamento di I/O.|  
|[Metodo CloseIoCompletionPort](ihostiocompletionmanager-closeiocompletionport-method.md)|Chiude una porta creata tramite una chiamata precedente a `CreateIoCompletionPort` .|  
|[Metodo CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md)|Richiede che l'host crei una nuova porta di completamento di I/O.|  
|[Metodo GetAvailableThreads](ihostiocompletionmanager-getavailablethreads-method.md)|Ottiene il numero di thread di completamento di I/O che non stanno attualmente elaborando richieste.|  
|[Metodo GetHostOverlappedSize](ihostiocompletionmanager-gethostoverlappedsize-method.md)|Ottiene le dimensioni dei dati personalizzati che l'host intende accodare alle richieste di I/O.|  
|[Metodo GetMaxThreads](ihostiocompletionmanager-getmaxthreads-method.md)|Ottiene il numero massimo di thread che l'host può allocare alle richieste di I/O del servizio.|  
|[Metodo GetMinThreads](ihostiocompletionmanager-getminthreads-method.md)|Ottiene il numero minimo di thread fornito dall'host alle richieste di I/O del servizio.|  
|[Metodo InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md)|Fornisce all'host la possibilità di inizializzare tutti i dati personalizzati relativi a una richiesta di I/O.|  
|[Metodo SetCLRIoCompletionManager](ihostiocompletionmanager-setclriocompletionmanager-method.md)|Fornisce all'host un puntatore di interfaccia a un'istanza di [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) implementata da CLR.|  
|[Metodo SetMaxThreads](ihostiocompletionmanager-setmaxthreads-method.md)|Imposta il numero massimo di thread allocati dall'host alle richieste di I/O del servizio.|  
|[Metodo SetMinThreads](ihostiocompletionmanager-setminthreads-method.md)|Imposta il numero minimo di thread che l'host deve assegnare al completamento I/O.|  
  
## <a name="remarks"></a>Osservazioni  
 `IHostIoCompletionManager`corrisponde all' `ICLRIoCompletionManager` interfaccia implementata da CLR. CLR chiama i metodi di `IHostIoCompletionManager` per associare gli handle alle porte fornite dall'host e l'host chiama i metodi di `ICLRIoCompletionManager` per segnalare il completamento delle richieste di i/O.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](hosting-interfaces.md)
