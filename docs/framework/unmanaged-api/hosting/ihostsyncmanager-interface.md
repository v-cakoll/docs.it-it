---
title: Interfaccia IHostSyncManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 951f7808e238f514ffcf19a8dda0033b7b07172c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanager-interface"></a>Interfaccia IHostSyncManager
Fornisce metodi che consentono a common language runtime (CLR) per creare le primitive di sincronizzazione tramite la chiamata dell'host anziché utilizzare le funzioni di sincronizzazione di Win32.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CreateAutoEvent (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|Crea un oggetto evento di reimpostazione automatica.|  
|[CreateCrst (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|Crea un oggetto sezione critica per la sincronizzazione.|  
|[CreateCrstWithSpinCount (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|Crea un oggetto sezione critica con conteggio di selezione per la sincronizzazione.|  
|[CreateManualEvent (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|Crea un oggetto evento di reimpostazione manuale.|  
|[CreateMonitorEvent (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|Crea un oggetto evento di reimpostazione automatica monitorato.|  
|[CreateRWLockReaderEvent (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.|  
|[CreateRWLockWriterEvent (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|Crea un oggetto evento di reimpostazione automatica per l'implementazione di un blocco del writer.|  
|[CreateSemaphore (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) oggetto per Common Language Runtime da utilizzare come un semaforo per gli eventi di attesa.|  
|[SetCLRSyncManager (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Imposta il [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) istanza da associare all'oggetto corrente `IHostSyncManager` istanza.|  
  
## <a name="remarks"></a>Note  
 Implementazione dell'host di `IHostSyncManager` chiamando il [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) metodo con un `IID` di IID_IHostSyncManager.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRSyncManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
