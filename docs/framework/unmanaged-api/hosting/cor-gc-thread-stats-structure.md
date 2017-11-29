---
title: Struttura COR_GC_THREAD_STATS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS
helpviewer_keywords: COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10366d183ed7fd7386609e4c5726df0cea4e29a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corgcthreadstats-structure"></a>Struttura COR_GC_THREAD_STATS
Contiene le statistiche per ogni thread relative alla garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`PerThreadAllocation`|Il numero di byte di memoria allocata nel thread in cui è associato all'oggetto corrente `COR_GC_THREAD_STATS` istanza. Questo numero è impostato su zero ogni volta che si verifica una generazione 0 garbage collection.|  
|`Flags`|Il numero di byte promossi a una generazione superiore più recente operazione di garbage collection.|  
  
## <a name="remarks"></a>Note  
 [ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost. idl  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [IHostTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
