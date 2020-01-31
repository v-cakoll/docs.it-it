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
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865779"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>Metodo ICorProfilerCallback2::GarbageCollectionStarted
Notifica all'Code Profiler che Garbage Collection è stata avviata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Parametri  
 `cGenerations`  
 in Il numero totale di voci nella matrice di `generationCollected`.  
  
 `generationCollected`  
 in Matrice di valori booleani, che vengono `true` se la generazione che corrisponde all'indice della matrice viene raccolta da questa Garbage Collection; in caso contrario, `false`.  
  
 La matrice viene indicizzata in base a un valore dell'enumerazione [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , che indica la generazione.  
  
 `reason`  
 in Valore dell'enumerazione [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) che indica il motivo per cui è stato indotto l'Garbage Collection.  
  
## <a name="remarks"></a>Note  
 Tutti i callback relativi a questo Garbage Collection si verificheranno tra il callback `GarbageCollectionStarted` e il callback [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) corrispondente. Questi callback non devono essere eseguiti nello stesso thread.  
  
 Il profiler può ispezionare gli oggetti nei percorsi originali durante il callback `GarbageCollectionStarted`. Il Garbage Collector inizierà a trasferire gli oggetti dopo il ritorno da `GarbageCollectionStarted`. Dopo che il profiler ha restituito questo callback, il profiler deve considerare tutti gli ID oggetto come non validi fino a quando non riceve un callback `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
