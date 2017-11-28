---
title: Metodo ICorProfilerCallback2::GarbageCollectionStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e79eea059fab4810ece12dbc264f3d3b08b7ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>Metodo ICorProfilerCallback2::GarbageCollectionStarted
Notifica al profiler di codice che ha avviato l'operazione di garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cGenerations`  
 [in] Il numero totale di voci di `generationCollected` matrice.  
  
 `generationCollected`  
 [in] Una matrice di valori booleani, che sono `true` se la generazione che corrisponde all'indice della matrice viene raccolto da garbage collection; in caso contrario, `false`.  
  
 La matrice viene indicizzata da un valore di [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumerazione che indica la generazione.  
  
 `reason`  
 [in] Il valore di [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumerazione che indica il motivo per l'operazione di garbage collection è stata attivata.  
  
## <a name="remarks"></a>Note  
 Tutti i callback relativi a questa operazione di garbage collection si verificheranno tra il `GarbageCollectionStarted` callback e i corrispondenti [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback. Questi callback non devono verificarsi sullo stesso thread.  
  
 È consigliabile per il profiler controllare gli oggetti nei rispettivi percorsi originali durante il `GarbageCollectionStarted` callback. Il garbage collector verrà avviato lo spostamento di oggetti dopo l'uscita da `GarbageCollectionStarted`. Dopo che il profiler ha restituito da questo callback, il profiler deve considerare tutti gli ID oggetto risulta valido finché riceve un `ICorProfilerCallback2::GarbageCollectionFinished` callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2 (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
