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
ms.openlocfilehash: 682aac9729519e0861ae6e6f60df78a30063c278
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867209"
---
# <a name="cor_prf_gc_generation_range-structure"></a>Struttura COR_PRF_GC_GENERATION_RANGE
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
|`generation`|Valore dell'enumerazione [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) che specifica la generazione a cui appartiene il blocco di memoria.|  
|`rangeStart`|ID di un oggetto che specifica la posizione iniziale del blocco di memoria.|  
|`rangeLength`|Puntatore a un intero che specifica la dimensione della parte utilizzata del blocco di memoria, ovvero la quantità di memoria utilizzata nel blocco.|  
|`rangeLengthReserved`|Puntatore a un intero che specifica la dimensione del blocco di memoria, ovvero la quantità di memoria riservata per il blocco.|  
  
## <a name="remarks"></a>Note  
 Il valore `rangeLength` garantisce la precisione solo se [ICorProfilerInfo2:: GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) o [Icorprofilerinfo2:: GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), che usano entrambi la struttura `COR_PRF_GC_GENERATION_RANGE`, viene chiamato dal metodo [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) o [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di profilatura](profiling-structures.md)
