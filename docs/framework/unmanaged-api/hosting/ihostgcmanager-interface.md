---
title: Interfaccia IHostGCManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager
helpviewer_keywords: IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0927b236af094b964261a9b2a49a33d1ea2b9391
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanager-interface"></a>Interfaccia IHostGCManager
Fornisce metodi per notificare all'host gli eventi nel meccanismo di garbage collection implementato da common language runtime (CLR).  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|[SuspensionEnding (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|Notifica all'host che Common Language Runtime viene ripresa l'esecuzione di attività nel thread che era stato sospeso per una garbage collection.|  
|[SuspensionStarting (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|Notifica all'host che Common Language Runtime sta sospendendo l'esecuzione delle attività, per eseguire un'operazione di garbage collection.|  
|[ThreadIsBlockingForSuspension (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|Notifica all'host che il thread da cui è stata effettuata la chiamata al metodo per essere bloccato per una garbage collection.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
