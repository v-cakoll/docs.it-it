---
title: Enumerazione COR_PRF_GC_ROOT_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: bbc163c71b47e6fee0db89284d6e3fd27e882768
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500887"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a>Enumerazione COR_PRF_GC_ROOT_FLAGS
Indica una proprietà di un Garbage Collection radice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|La radice impedisce a un Garbage Collection di migrare l'oggetto.|  
|`COR_PRF_GC_ROOT_WEAKREF`|La radice non impedisce Garbage Collection.|  
|`COR_PRF_GC_ROOT_INTERIOR`|La radice fa riferimento a un campo dell'oggetto anziché all'oggetto stesso.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|La radice impedisce Garbage Collection se il conteggio dei riferimenti dell'oggetto è un determinato valore.|  
  
## <a name="remarks"></a>Osservazioni  
 `COR_PRF_GC_ROOT_FLAGS`è una maschera di maschera che fornisce informazioni aggiuntive sulle radici speciali. Tuttavia, non tutte le radici sono particolari. Alcune radici, ad esempio, non sono riferimenti vulnerabili, puntatori interni, aggiunti o conteggiati come riferimenti. Per tali radici, non sono presenti flag da inserire. Pertanto, i metodi che utilizzano questa enumerazione, ad esempio il metodo [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) , inviano 0 per la maschera di maschera dei flag, che indica che tutti i flag sono disattivati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](profiling-enumerations.md)
