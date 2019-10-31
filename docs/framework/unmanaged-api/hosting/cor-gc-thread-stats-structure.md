---
title: Struttura COR_GC_THREAD_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 37da471aaa8e9f802a8430d7b3289b375ff1b40a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136979"
---
# <a name="cor_gc_thread_stats-structure"></a>Struttura COR_GC_THREAD_STATS
Contiene statistiche per thread che riguardano Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`PerThreadAllocation`|Numero di byte di memoria allocata nel thread associato all'istanza di `COR_GC_THREAD_STATS` corrente. Questo numero viene cancellato a zero ogni volta che viene generato un Garbage Collection di generazione zero.|  
|`Flags`|Numero di byte promossi a una generazione più elevata nel Garbage Collection più recente.|  
  
## <a name="remarks"></a>Note  
 [ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) accetta un parametro di output di tipo `COR_GC_THREAD_STATS`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
