---
title: Interfaccia IHostMemoryManager
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: 09b4a06892cdc450eed9dead503a990b6f19804e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501508"
---
# <a name="ihostmemorymanager-interface"></a>Interfaccia IHostMemoryManager
Fornisce metodi che consentono all'Common Language Runtime (CLR) di effettuare richieste di memoria virtuale attraverso l'host, anziché utilizzare le funzioni di memoria virtuale Win32 standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AcquiredVirtualAddressSpace](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Notifica all'host che la Common Language Runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.|  
|[Metodo CreateMAlloc](ihostmemorymanager-createmalloc-method.md)|Ottiene un puntatore a interfaccia a un'istanza di [IHostMalloc](ihostmalloc-interface.md) utilizzata per richiedere allocazioni di memoria da un heap creato dall'host.|  
|[Metodo GetMemoryLoad](ihostmemorymanager-getmemoryload-method.md)|Ottiene la quantità di memoria fisica attualmente in uso, come segnalato dall'host.|  
|[Metodo NeedsVirtualAddressSpace](ihostmemorymanager-needsvirtualaddressspace-method.md)|Notifica all'host che CLR tenterà di utilizzare la memoria specificata.|  
|[Metodo RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md)|Registra un puntatore a una funzione di callback richiamata dall'host per notificare a CLR il carico di memoria corrente nel computer.|  
|[Metodo ReleasedVirtualAddressSpace](ihostmemorymanager-releasedvirtualaddressspace-method.md)|Notifica all'host che CLR ha terminato di utilizzare la memoria specificata.|  
|[Metodo VirtualAlloc](ihostmemorymanager-virtualalloc-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che consente di riservare o eseguire il commit di un'area di pagine nello spazio degli indirizzi virtuali del processo chiamante.|  
|[Metodo VirtualFree](ihostmemorymanager-virtualfree-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che rilascia, decommit o rilascia un'area di pagine all'interno dello spazio degli indirizzi virtuali del processo chiamante.|  
|[Metodo VirtualProtect](ihostmemorymanager-virtualprotect-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che modifica la protezione in un'area di pagine di cui è stato eseguito il commit nello spazio degli indirizzi virtuali del processo chiamante.|  
|[Metodo VirtualQuery](ihostmemorymanager-virtualquery-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che recupera informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.|  
  
## <a name="remarks"></a>Osservazioni  
 `IHostMemoryManager`fornisce inoltre metodi che consentono a CLR di ottenere un puntatore tramite il quale eseguire richieste di memoria nell'heap e ottenere il livello di utilizzo di memoria nel processo, come riportato dall'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMalloc](ihostmalloc-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
