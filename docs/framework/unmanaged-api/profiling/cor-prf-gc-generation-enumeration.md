---
title: Enumerazione COR_PRF_GC_GENERATION
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69eec0c2dfccacee4c54c9f2493da523812259aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgeneration-enumeration"></a>Enumerazione COR_PRF_GC_GENERATION
Identifica una generazione di garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|L'oggetto viene archiviato come generazione 0.|  
|`COR_PRF_GC_GEN_1`|L'oggetto viene archiviato come generazione 1.|  
|`COR_PRF_GC_GEN_2`|L'oggetto viene archiviato come generazione 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|L'oggetto viene archiviato nell'heap degli oggetti di grandi dimensioni.|  
  
## <a name="remarks"></a>Note  
 Il garbage collector consente di migliorare le prestazioni di gestione della memoria dividendo gli oggetti in generazioni in base all'età. Il garbage collector attualmente utilizza tre generazioni, numerate 0, 1 e 2, oltre a un segmento di un heap speciale che viene utilizzato per oggetti di grandi dimensioni. Gli oggetti la cui dimensione è maggiore di un particolare valore vengono archiviati nell'heap degli oggetti di grandi dimensioni. Gli altri oggetti allocati inizialmente appartengono alla generazione 0. Tutti gli oggetti esistenti dopo la garbage collection nella generazione 0 vengono promossi alla generazione 1. Gli oggetti che esistono dopo la garbage collection nella generazione 1 promossi alla generazione 2.  
  
 L'utilizzo di generazioni significa che il garbage collector deve utilizzare solo un subset degli oggetti allocati in qualsiasi momento.  
  
 Il `COR_PRF_GC_GENERATION` enumerazione viene utilizzata per la [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) struttura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
