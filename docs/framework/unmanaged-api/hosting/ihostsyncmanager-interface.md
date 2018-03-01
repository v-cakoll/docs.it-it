---
title: Interfaccia IHostSyncManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b51e1dd9219c30eb4918bf1e331c96585f7c03ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanager-interface"></a>Interfaccia IHostSyncManager
Fornisce metodi che consentono a common language runtime (CLR) per creare le primitive di sincronizzazione tramite la chiamata dell'host anziché utilizzare le funzioni di sincronizzazione di Win32.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|Crea un oggetto evento di reimpostazione automatica.|  
|[Metodo CreateCrst](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|Crea un oggetto sezione critica per la sincronizzazione.|  
|[Metodo CreateCrstWithSpinCount](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|Crea un oggetto sezione critica con conteggio di selezione per la sincronizzazione.|  
|[Metodo CreateManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|Crea un oggetto evento di reimpostazione manuale.|  
|[Metodo CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|Crea un oggetto evento di reimpostazione automatica monitorato.|  
|[Metodo CreateRWLockReaderEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.|  
|[Metodo CreateRWLockWriterEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|Crea un oggetto evento di reimpostazione automatica per l'implementazione di un blocco del writer.|  
|[Metodo CreateSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) oggetto per Common Language Runtime da utilizzare come un semaforo per gli eventi di attesa.|  
|[Metodo SetCLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Imposta il [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) istanza da associare all'oggetto corrente `IHostSyncManager` istanza.|  
  
## <a name="remarks"></a>Note  
 Implementazione dell'host di `IHostSyncManager` chiamando il [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) metodo con un `IID` di IID_IHostSyncManager.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
