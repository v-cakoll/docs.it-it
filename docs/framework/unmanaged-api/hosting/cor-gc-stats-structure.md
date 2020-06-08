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
ms.openlocfilehash: 7a6553de31d4f9627809af7691218c39dc734c6f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501664"
---
# <a name="cor_gc_stats-structure"></a>Struttura COR_GC_STATS
Fornisce statistiche sul meccanismo di Garbage Collection del Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`Flags`|Indica i valori dei campi da calcolare e restituire.|  
|`ExplicitGCCount`|Indica il numero di operazioni di Garbage Collection forzate dalla richiesta esterna.|  
|`GenCollectionsTaken`|Indica il numero di operazioni di Garbage Collection eseguite per ogni generazione.|  
|`CommittedKBytes`|Numero totale di kilobyte di cui è stato eseguito il commit in tutti gli heap.|  
|`ReservedKBytes`|Numero totale di kilobyte riservati in tutti gli heap.|  
|`Gen0HeapSizeKBytes`|Dimensioni, in kilobyte, dell'heap di generazione zero.|  
|`Gen1HeapSizeKBytes`|Dimensioni, in kilobyte, dell'heap di generazione-uno.|  
|`Gen2HeapSizeKBytes`|Dimensioni, in kilobyte, dell'heap di generazione due.|  
|`LargeObjectHeapSizeKBytes`|Dimensioni, in kilobyte, dell'heap degli oggetti grandi.|  
|`KBytesPromotedFromGen0`|Dimensioni, in kilobyte, degli oggetti promossi dalla generazione zero alla generazione 1.|  
|`KBytesPromotedFromGen1`|Dimensioni, in kilobyte, degli oggetti promossi dalla generazione 1 alla seconda generazione.|  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo [ICLRGCManager:: GetStats](iclrgcmanager-getstats-method.md) richiede `Flags` che il campo della `COR_GC_STATS` struttura sia impostato su uno o più valori dell'enumerazione [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) per specificare le statistiche da impostare.  
  
 Nella tabella seguente viene eseguito il mapping delle statistiche fornite da questa struttura ai due [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) valori di enumerazione, `COR_GC_COUNTS` e `COR_GC_MEMORYUSAGE` .  
  
|Specificato da COR_GC_COUNTS|Specificato da COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Di seguito è riportato un esempio di utilizzo:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** GCHost. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](hosting-structures.md)
- [Gestione automatica della memoria](../../../standard/automatic-memory-management.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
