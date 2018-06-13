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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3edae4cb112f46643734c5f1612d9df36ad47e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441330"
---
# <a name="ihostmemorymanager-interface"></a>Interfaccia IHostMemoryManager
Fornisce metodi che consentono a common language runtime (CLR) per effettuare richieste di memoria virtuale tramite l'host, invece di usare le funzioni di memoria virtuale Win32 standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AcquiredVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Notifica all'host che common language runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.|  
|[Metodo CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Ottiene un puntatore a interfaccia a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) istanza che viene usato per richiedere le allocazioni di memoria da un heap creato dall'host.|  
|[Metodo GetMemoryLoad](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Ottiene la quantità di memoria fisica che è attualmente in uso, come riportato dall'host.|  
|[Metodo NeedsVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Notifica all'host che CLR tenterà di utilizzare la memoria specificata.|  
|[Metodo RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registra un puntatore a una funzione di callback che l'host richiama per notificare a CLR il carico di memoria corrente nel computer.|  
|[Metodo ReleasedVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Notifica all'host che CLR ha terminato di utilizzare la memoria specificata.|  
|[Metodo VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che si riserva o esegue il commit di una regione di pagine nello spazio degli indirizzi virtuali del processo chiamante.|  
|[Metodo VirtualFree](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che rilascia, libera o rilascia e libera un'area di pagine all'interno di spazio degli indirizzi virtuali del processo chiamante.|  
|[Metodo VirtualProtect](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che modifica la protezione in un'area di pagine salvate nello spazio degli indirizzi virtuali del processo chiamante.|  
|[Metodo VirtualQuery](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Funge da wrapper logico per la funzione Win32 corrispondente, che recupera informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.|  
  
## <a name="remarks"></a>Note  
 `IHostMemoryManager` fornisce inoltre metodi per il CLR ottenere un puntatore attraverso il quale per effettuare richieste di memoria nell'heap e di ottenere il livello di utilizzo della memoria del processo, come riportato dall'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
