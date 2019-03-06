---
title: Metodo ICorProfilerCallback2::GarbageCollectionStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3c95bbf946cd208a1cc01463aaae76e3842c8fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471264"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>Metodo ICorProfilerCallback2::GarbageCollectionStarted
Notifica al profiler di codice che ha avviato la garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Parametri  
 `cGenerations`  
 [in] Il numero totale di voci di `generationCollected` matrice.  
  
 `generationCollected`  
 [in] Matrice di valori booleani, ossia `true` se la generazione che corrisponde all'indice della matrice viene raccolto da questa operazione di garbage collection; in caso contrario, `false`.  
  
 La matrice viene indicizzata mediante il valore di [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumerazione che indica la generazione.  
  
 `reason`  
 [in] Valore di [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumerazione che indica il motivo per l'operazione di garbage collection è stata generata.  
  
## <a name="remarks"></a>Note  
 Verificheranno tutte le richiamate che si riferiscono a questa operazione di garbage collection tra i `GarbageCollectionStarted` callback e i corrispondenti [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback. Questi callback non devono verificarsi sullo stesso thread.  
  
 È sicuro per il profiler controllare gli oggetti nei rispettivi percorsi originali durante il `GarbageCollectionStarted` callback. Il garbage collector verrà avviato lo spostamento di oggetti dopo l'uscita da `GarbageCollectionStarted`. Dopo che il profiler ha restituito da questo callback, il profiler deve prendere in considerazione tutti gli ID di oggetto potrebbe non essere valido finché non riceve un `ICorProfilerCallback2::GarbageCollectionFinished` callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
