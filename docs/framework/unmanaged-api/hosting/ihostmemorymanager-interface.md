---
title: Interfaccia IHostMemoryManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 415539be0dbed8e0cf3f9d6e5c79bf4cfac09fe2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanager-interface"></a>Interfaccia IHostMemoryManager
Fornisce metodi che consentono a common language runtime (CLR) per effettuare richieste di memoria virtuale tramite l'host, invece di usare le funzioni di memoria virtuale Win32 standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Notifica all'host che common language runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.|  
|[Metodo CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Ottiene un puntatore a interfaccia a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) istanza che viene usato per richiedere le allocazioni di memoria da un heap creato dall'host.|  
|[GetMemoryLoad (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Ottiene la quantità di memoria fisica che è attualmente in uso, come riportato dall'host.|  
|[NeedsVirtualAddressSpace (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Notifica all'host che CLR tenterà di utilizzare la memoria specificata.|  
|[RegisterMemoryNotificationCallback (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registra un puntatore a una funzione di callback che l'host richiama per notificare a CLR il carico di memoria corrente nel computer.|  
|[ReleasedVirtualAddressSpace (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Notifica all'host che CLR ha terminato di utilizzare la memoria specificata.|  
|[VirtualAlloc (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che si riserva o esegue il commit di una regione di pagine nello spazio degli indirizzi virtuali del processo chiamante.|  
|[VirtualFree (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che rilascia, libera o rilascia e libera un'area di pagine all'interno di spazio degli indirizzi virtuali del processo chiamante.|  
|[VirtualProtect (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che modifica la protezione in un'area di pagine salvate nello spazio degli indirizzi virtuali del processo chiamante.|  
|[VirtualQuery (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che recupera informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.|  
  
## <a name="remarks"></a>Note  
 `IHostMemoryManager`fornisce inoltre metodi per ottenere un puntatore attraverso il quale per effettuare richieste di memoria nell'heap e di ottenere il livello di utilizzo della memoria del processo, come riportato dall'host CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IHostMalloc (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
