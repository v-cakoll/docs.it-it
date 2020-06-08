---
title: Metodo ICorProfilerCallback::ObjectReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 12a0792e8fafc73b480de6bacc86f98470dfedf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503289"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>Metodo ICorProfilerCallback::ObjectReferences
Notifica al profiler gli oggetti in memoria a cui fa riferimento l'oggetto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 in ID dell'oggetto che fa riferimento a oggetti.  
  
 `classId`  
 in ID della classe di cui l'oggetto specificato è un'istanza di.  
  
 `cObjectRefs`  
 in Numero di oggetti a cui fa riferimento l'oggetto specificato, ovvero il numero di elementi nella `objectRefIds` matrice.  
  
 `objectRefIds`  
 in Matrice di ID di oggetti a cui fa riferimento `objectId` .  
  
## <a name="remarks"></a>Osservazioni  
 Il `ObjectReferences` metodo viene chiamato per ogni oggetto rimanente nell'heap dopo il completamento di un Garbage Collection. Se il profiler restituisce un errore da questo callback, i servizi di profilatura non richiameranno questo callback fino al Garbage Collection successivo.  
  
 Il `ObjectReferences` callback può essere usato insieme al callback [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) per creare un grafico completo di riferimento all'oggetto per il Runtime. Il Common Language Runtime (CLR) garantisce che ogni riferimento a un oggetto venga segnalato solo una volta dal `ObjectReferences` metodo.  
  
 Gli ID oggetto restituiti da `ObjectReferences` non sono validi durante il callback stesso, perché il Garbage Collection potrebbe trovarsi durante lo spostamento di oggetti. Pertanto, i profiler non devono tentare di ispezionare gli oggetti durante una `ObjectReferences` chiamata. Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) , il Garbage Collection è completo e l'ispezione può essere eseguita in modo sicuro.  
  
 Un valore null `ClassId` indica che `objectId` ha un tipo che sta scaricando.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
