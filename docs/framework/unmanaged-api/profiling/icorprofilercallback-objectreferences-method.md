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
ms.openlocfilehash: 6e6cc44c2f9028c0e26c4f933242cad93e3a98c3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866091"
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
 in Numero di oggetti a cui fa riferimento l'oggetto specificato (ovvero il numero di elementi nella matrice di `objectRefIds`).  
  
 `objectRefIds`  
 in Matrice di ID di oggetti a cui fa riferimento `objectId`.  
  
## <a name="remarks"></a>Note  
 Il metodo `ObjectReferences` viene chiamato per ogni oggetto rimanente nell'heap dopo il completamento di un Garbage Collection. Se il profiler restituisce un errore da questo callback, i servizi di profilatura non richiameranno questo callback fino al Garbage Collection successivo.  
  
 Il callback di `ObjectReferences` può essere usato insieme al callback [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) per creare un grafico completo di riferimento all'oggetto per il Runtime. Il Common Language Runtime (CLR) garantisce che ogni riferimento a un oggetto venga segnalato solo una volta dal metodo `ObjectReferences`.  
  
 Gli ID oggetto restituiti da `ObjectReferences` non sono validi durante il callback stesso, perché il Garbage Collection potrebbe trovarsi durante lo spostamento di oggetti. Pertanto, i profiler non devono tentare di ispezionare gli oggetti durante una chiamata `ObjectReferences`. Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) , il Garbage Collection è completo e l'ispezione può essere eseguita in modo sicuro.  
  
 Un `ClassId` null indica che `objectId` dispone di un tipo che sta scaricando.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
