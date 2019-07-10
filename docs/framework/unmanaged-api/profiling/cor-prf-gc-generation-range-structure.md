---
title: Struttura COR_PRF_GC_GENERATION_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f82b187a099ef7decca590da361f6b1abfa22e0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753793"
---
# <a name="corprfgcgenerationrange-structure"></a>Struttura COR_PRF_GC_GENERATION_RANGE
Descrive un intervallo, ovvero un blocco, di memoria sottoposto a Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`generation`|Valore di [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumerazione che specifica la generazione in cui il blocco di memoria a cui appartiene.|  
|`rangeStart`|ID dell'oggetto che specifica la posizione iniziale del blocco di memoria.|  
|`rangeLength`|Un puntatore a un intero che specifica la dimensione alla parte usata del blocco di memoria (vale a dire, la quantità di memoria utilizzata all'interno del blocco).|  
|`rangeLengthReserved`|Un puntatore a un integer che specifica la dimensione del blocco di memoria (vale a dire, la quantità di memoria riservata per il blocco).|  
  
## <a name="remarks"></a>Note  
 Il `rangeLength` valore è sicuramente accurata solo se [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) oppure [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), entrambi delle quali usano la `COR_PRF_GC_GENERATION_RANGE` struttura, viene chiamato dal [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) o nella [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
