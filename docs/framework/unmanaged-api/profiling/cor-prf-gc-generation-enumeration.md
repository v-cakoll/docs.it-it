---
title: Enumerazione COR_PRF_GC_GENERATION
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: d01b864be231e5b0a3fd72dc2f3636a87c8cae83
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448636"
---
# <a name="cor_prf_gc_generation-enumeration"></a>Enumerazione COR_PRF_GC_GENERATION
Identifica una generazione di Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|L'oggetto viene archiviato come generazione 0.|  
|`COR_PRF_GC_GEN_1`|L'oggetto viene archiviato come generazione 1.|  
|`COR_PRF_GC_GEN_2`|L'oggetto viene archiviato come generazione 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|L'oggetto viene archiviato nell'heap degli oggetti di grandi dimensioni.|  
  
## <a name="remarks"></a>Note  
 Il Garbage Collector migliora le prestazioni di gestione della memoria dividendo gli oggetti in generazioni in base all'età. Il Garbage Collector utilizza attualmente tre generazioni, numerate 0, 1 e 2, più uno speciale segmento di heap utilizzato per oggetti di grandi dimensioni. Gli oggetti la cui dimensione è maggiore di un determinato valore vengono archiviati nell'heap degli oggetti di grandi dimensioni. Altri oggetti allocati iniziano a appartenere alla generazione 0. Tutti gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 0 vengono promossi alla generazione 1. Gli oggetti esistenti dopo Garbage Collection si verificano nella generazione 1 passano alla generazione 2.  
  
 L'uso di generazioni significa che il Garbage Collector deve lavorare solo con un subset degli oggetti allocati in un momento specifico.  
  
 L'enumerazione `COR_PRF_GC_GENERATION` viene utilizzata dalla struttura di [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
