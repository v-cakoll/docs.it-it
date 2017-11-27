---
title: Interfaccia ICLRSyncManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager
helpviewer_keywords: ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1e47f02a5a84b909b03c6be4e0a43c7166a1ddc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanager-interface"></a>Interfaccia ICLRSyncManager
Definisce i metodi che consentono all'host per ottenere informazioni sulle attività richieste e di rilevare deadlock nell'implementazione della sincronizzazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)|Richiede che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.|  
|[DeleteRWLockOwnerIterator (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)|Richiede che Common Language Runtime di eliminare un iteratore che è stato creato da una chiamata a `CreateRWLockOwnerIterator`.|  
|[GetMonitorOwner (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)|Ottiene l'attività proprietaria del monitor specificato.|  
|[GetRWLockOwnerNext (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)|Ottiene l'attività successiva è in attesa sul blocco di lettura / scrittura corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 [IHostSyncManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Threading gestito e non gestito](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
