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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 263c22a07f363c2752afb50779515de043976e93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775063"
---
# <a name="corprfgcrootflags-enumeration"></a>Enumerazione COR_PRF_GC_ROOT_FLAGS
Indica una proprietà di una radice di garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|La radice impedisce un'operazione di garbage collection di spostare l'oggetto.|  
|`COR_PRF_GC_ROOT_WEAKREF`|La radice non impedisce l'operazione di garbage collection.|  
|`COR_PRF_GC_ROOT_INTERIOR`|La radice fa riferimento a un campo dell'oggetto anziché l'oggetto stesso.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|Radice impedisce l'operazione di garbage collection se il conteggio dei riferimenti dell'oggetto è un determinato valore.|  
  
## <a name="remarks"></a>Note  
 `COR_PRF_GC_ROOT_FLAGS` è una maschera di bit che fornisce informazioni aggiuntive sulle radici speciali. Tuttavia, non tutte le radici sono speciali. Ad esempio, alcune directory principali non sono riferimenti deboli, i puntatori interni, bloccati o con conteggio dei riferimenti. Per questo tipo radici, non sono presenti flag per indicare. Di conseguenza, i metodi che usano questa enumerazione, ad esempio la [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) metodo send 0 per la maschera di bit di flag che indica che tutti i flag sono disattivati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
