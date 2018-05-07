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
ms.openlocfilehash: 2d5dcb089074b52fc87a0bb83c7e062e7ef07b46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|La radice impedisce un'operazione di garbage collection di spostare l'oggetto.|  
|`COR_PRF_GC_ROOT_WEAKREF`|La radice non impedisce l'operazione di garbage collection.|  
|`COR_PRF_GC_ROOT_INTERIOR`|La radice fa riferimento a un campo dell'oggetto anziché l'oggetto stesso.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|La radice impedisce l'operazione di garbage collection se il conteggio dei riferimenti dell'oggetto è un determinato valore.|  
  
## <a name="remarks"></a>Note  
 `COR_PRF_GC_ROOT_FLAGS` è una maschera di bit che fornisce informazioni aggiuntive sulle radici speciali. Tuttavia, non tutte le radici sono speciali. Ad esempio, alcune directory principali non sono riferimenti deboli, puntatori interni, bloccati o con conteggio dei riferimenti. Per le radici non sono presenti flag per comunicare. Di conseguenza, i metodi che usano questa enumerazione, ad esempio il [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) metodo send 0 per la maschera di bit di flag che indica che tutti i flag sono disattivati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
