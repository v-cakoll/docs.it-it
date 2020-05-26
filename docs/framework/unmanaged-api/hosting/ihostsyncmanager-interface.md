---
title: Interfaccia IHostSyncManager
ms.date: 03/30/2017
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
ms.openlocfilehash: e96492270c403f93687245cee8b680dc16b3c787
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803130"
---
# <a name="ihostsyncmanager-interface"></a>Interfaccia IHostSyncManager
Fornisce metodi che consentono all'Common Language Runtime (CLR) di creare primitive di sincronizzazione chiamando l'host invece di usare le funzioni di sincronizzazione Win32.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateAutoEvent](ihostsyncmanager-createautoevent-method.md)|Crea un oggetto evento di reimpostazione automatica.|  
|[Metodo CreateCrst](ihostsyncmanager-createcrst-method.md)|Crea un oggetto sezione critica per la sincronizzazione.|  
|[Metodo CreateCrstWithSpinCount](ihostsyncmanager-createcrstwithspincount-method.md)|Crea un oggetto sezione critico con il numero di spin per la sincronizzazione.|  
|[Metodo CreateManualEvent](ihostsyncmanager-createmanualevent-method.md)|Crea un oggetto evento di reimpostazione manuale.|  
|[Metodo CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md)|Crea un oggetto evento di reimpostazione automatica monitorato.|  
|[Metodo CreateRWLockReaderEvent](ihostsyncmanager-createrwlockreaderevent-method.md)|Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.|  
|[Metodo CreateRWLockWriterEvent](ihostsyncmanager-createrwlockwriterevent-method.md)|Crea un oggetto evento di reimpostazione automatica per l'implementazione di un blocco del writer.|  
|[Metodo CreateSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Crea un oggetto [IHostSemaphore](ihostsemaphore-interface.md) per CLR da usare come semaforo per gli eventi di attesa.|  
|[Metodo SetCLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Imposta l'istanza di [ICLRSyncManager](iclrsyncmanager-interface.md) da associare all' `IHostSyncManager` istanza corrente.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR individua l'implementazione dell'host di chiamando `IHostSyncManager` il metodo [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) con un oggetto `IID` di IID_IHostSyncManager.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
