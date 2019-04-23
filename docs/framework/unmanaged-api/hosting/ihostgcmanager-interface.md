---
title: Interfaccia IHostGCManager
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 238b054d240437df64a83a9c4daad34d4bd5d36a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228881"
---
# <a name="ihostgcmanager-interface"></a>Interfaccia IHostGCManager
Fornisce metodi per notificare all'host gli eventi nel meccanismo di garbage collection implementato da common language runtime (CLR).  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|[Metodo SuspensionEnding](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|Notifica all'host che CLR viene ripresa l'esecuzione delle attività nei thread che erano stati sospesi per una garbage collection.|  
|[Metodo SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|Notifica all'host che Common Language Runtime sta per sospendere l'esecuzione di attività, per eseguire un'operazione di garbage collection.|  
|[Metodo ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|Notifica all'host che è il thread da cui è stata effettuata la chiamata al metodo per essere bloccato per una garbage collection.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
