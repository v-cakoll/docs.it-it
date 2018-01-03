---
title: Enumerazione ETaskType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ETaskType
api_location: mscoree.dll
api_type: COM
f1_keywords: ETaskType
helpviewer_keywords: ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7973b8cbd49858daaf6f08d55c7d9f60f687a72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="etasktype-enumeration"></a>Enumerazione ETaskType
Contiene valori che indicano il tipo di attività che è rappresentato da un [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`TT_ADUNLOAD`|L'interfaccia rappresenta un'attività di scaricamento del dominio applicazione.|  
|`TT_DEBUGGERHELPER`|L'interfaccia rappresenta un'attività di supporto del debugger.|  
|`TT_FINALIZER`|L'interfaccia rappresenta un'attività del finalizzatore.|  
|`TT_GC`|L'interfaccia rappresenta un'attività di garbage collection.|  
|`TT_THREADPOOL_GATE`|L'interfaccia rappresenta un'attività di thread di controllo.|  
|`TT_THREADPOOL_IOCOMPLETION`|L'interfaccia rappresenta un'attività di thread dei / o o di un'attività di thread di porta di completamento.|  
|`TT_THREADPOOL_TIMER`|L'interfaccia rappresenta un'attività di thread di timer.|  
|`TT_THREADPOOL_WAIT`|L'interfaccia rappresenta un'attività di thread di attesa.|  
|`TT_THREADPOOL_WORKER`|L'interfaccia rappresenta un'attività di thread di lavoro.|  
|`TT_UNKNOWN`|L'attività è sconosciuto.|  
|`TT_USER`|L'interfaccia rappresenta un'attività definita dall'utente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
