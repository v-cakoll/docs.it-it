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
ms.openlocfilehash: b587f30a01623c6e9806bcd9d01058a0880be239
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499909"
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
 in Numero di riferimenti nella `rootRefIds` matrice.  
  
 `rootRefIds`  
 in Matrice di ID oggetto che fanno riferimento a un oggetto statico o a un oggetto nello stack.  
  
## <a name="remarks"></a>Osservazioni  
 `RootReferences`E [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) vengono chiamati per inviare una notifica al profiler. I profiler in genere implementano uno o l'altro, ma non entrambi, perché le informazioni passate `RootReferences2` sono un superset di quello passato `RootReferences` .  
  
 È possibile che la `rootRefIds` matrice contenga un oggetto null. Ad esempio, tutti i riferimenti a oggetti dichiarati nello stack vengono considerati come radici dal Garbage Collector e verranno sempre segnalati.  
  
 Gli ID oggetto restituiti da `RootReferences` non sono validi durante il callback stesso, perché è possibile che il Garbage Collection stia spostando gli oggetti dagli indirizzi precedenti ai nuovi indirizzi. Pertanto, i profiler non devono tentare di ispezionare gli oggetti durante una `RootReferences` chiamata. Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) , tutti gli oggetti sono stati spostati nelle nuove posizioni e possono essere controllati in modo sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
