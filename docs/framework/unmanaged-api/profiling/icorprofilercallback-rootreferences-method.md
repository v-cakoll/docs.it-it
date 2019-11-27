---
title: Metodo ICorProfilerCallback::RootReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: 9c96cacf508ef5c056a1ff4469247393fdfb9e9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444468"
---
# <a name="icorprofilercallbackrootreferences-method"></a>Metodo ICorProfilerCallback::RootReferences
Notifica al profiler informazioni sui riferimenti radice dopo Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Parametri  
 `cRootRefs`  
 in Numero di riferimenti nella matrice `rootRefIds`.  
  
 `rootRefIds`  
 in Matrice di ID oggetto che fanno riferimento a un oggetto statico o a un oggetto nello stack.  
  
## <a name="remarks"></a>Note  
 Per notificare al profiler vengono chiamati sia `RootReferences` che [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) . I profiler in genere implementano uno o l'altro, ma non entrambi, perché le informazioni passate in `RootReferences2` sono un superset di quello passato in `RootReferences`.  
  
 È possibile che la matrice di `rootRefIds` contenga un oggetto null. Ad esempio, tutti i riferimenti a oggetti dichiarati nello stack vengono considerati come radici dal Garbage Collector e verranno sempre segnalati.  
  
 Gli ID oggetto restituiti da `RootReferences` non sono validi durante il callback stesso, perché è possibile che il Garbage Collection stia spostando gli oggetti dagli indirizzi precedenti ai nuovi indirizzi. Pertanto, i profiler non devono tentare di ispezionare gli oggetti durante una chiamata `RootReferences`. Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) , tutti gli oggetti sono stati spostati nelle nuove posizioni e possono essere controllati in modo sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
