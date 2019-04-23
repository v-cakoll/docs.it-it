---
title: Struttura COR_GC_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d335a62545f06a66d4044b59aa9499d3f7ede515
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208475"
---
# <a name="corgcstats-structure"></a>Struttura COR_GC_STATS
Fornisce statistiche sul meccanismo di garbage collection di common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`Flags`|Indica i valori dei campi devono essere calcolati e restituiti.|  
|`ExplicitGCCount`|Indica il numero di operazioni di garbage collection che sono stati obbligati da una richiesta esterna.|  
|`GenCollectionsTaken`|Indica il numero di operazioni di garbage collection eseguite per ogni generazione.|  
|`CommittedKBytes`|Il numero totale di kilobyte eseguito il commit in tutti gli heap.|  
|`ReservedKBytes`|Il numero totale di kilobyte riservato in tutti gli heap.|  
|`Gen0HeapSizeKBytes`|Dimensione, espressa in kilobyte, dell'heap di generazione 0.|  
|`Gen1HeapSizeKBytes`|Dimensione, espressa in kilobyte, dell'heap di generazione 1.|  
|`Gen2HeapSizeKBytes`|Dimensione, espressa in kilobyte, dell'heap di generazione 2.|  
|`LargeObjectHeapSizeKBytes`|Dimensione, espressa in kilobyte, dell'heap oggetti grandi.|  
|`KBytesPromotedFromGen0`|Dimensione, espressa in kilobyte, gli oggetti promossi dalla generazione 0 alla generazione 1.|  
|`KBytesPromotedFromGen1`|Dimensione, espressa in kilobyte, gli oggetti promossi dalla generazione 1 alla generazione 2.|  
  
## <a name="remarks"></a>Note  
 Il [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) metodo richiede il `Flags` campo il `COR_GC_STATS` struttura viene impostata su uno o più valori del [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumerazione per specificare quali le statistiche devono essere impostate.  
  
 Nella tabella seguente viene eseguito il mapping le statistiche fornite da questa struttura per i due [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) valori di enumerazione `COR_GC_COUNTS` e `COR_GC_MEMORYUSAGE`.  
  
|Specificato dal COR_GC_COUNTS|Specificato dal COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Un esempio dell'utilizzo è come segue:  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** GCHost.idl  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Gestione automatica della memoria](../../../../docs/standard/automatic-memory-management.md)
- [Garbage Collection](../../../../docs/standard/garbage-collection/index.md)
