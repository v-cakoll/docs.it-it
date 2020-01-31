---
title: Metodo ICorProfilerCallback2::RootReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: a9ce9a7a56847efcadf09924ffc56c41f20a1c58
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865727"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>Metodo ICorProfilerCallback2::RootReferences2
Notifica al profiler i riferimenti radice dopo che si è verificato un Garbage Collection. Questo metodo è un'estensione del metodo [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `cRootRefs`  
 in Il numero di elementi nelle matrici `rootRefIds`, `rootKinds`, `rootFlags`e `rootIds`.  
  
 `rootRefIds`  
 in Matrice di ID oggetto, ognuno dei quali fa riferimento a un oggetto statico o a un oggetto nello stack. Gli elementi nella matrice di `rootKinds` forniscono informazioni per classificare gli elementi corrispondenti nella matrice di `rootRefIds`.  
  
 `rootKinds`  
 in Matrice di valori di [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) che indicano il tipo di Garbage Collection radice.  
  
 `rootFlags`  
 in Matrice di valori [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) che descrivono le proprietà di un Garbage Collection radice.  
  
 `rootIds`  
 in Matrice di valori di UINT_PTR che punta a un Integer che contiene informazioni aggiuntive sulla radice Garbage Collection, a seconda del valore del parametro `rootKinds`.  
  
 Se il tipo della radice è uno stack, l'ID radice è per la funzione che contiene la variabile. Se l'ID radice è 0, la funzione è una funzione senza nome che è interna a CLR. Se il tipo della radice è un handle, l'ID radice è per il Garbage Collection handle. Per gli altri tipi radice, l'ID è un valore opaco e deve essere ignorato.  
  
## <a name="remarks"></a>Note  
 Le matrici `rootRefIds`, `rootKinds`, `rootFlags`e `rootIds` sono matrici parallele. Ovvero `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`e `rootIds[i]` tutti riguardano la stessa radice.  
  
 Per notificare al profiler vengono chiamati sia `RootReferences` che `RootReferences2`. I profiler in genere implementano un metodo o l'altro, ma non entrambi, perché le informazioni passate in `RootReferences2` sono un superset di passato in `RootReferences`.  
  
 È possibile che le voci in `rootRefIds` siano pari a zero, il che significa che il riferimento radice corrispondente è null e non fa riferimento a un oggetto nell'heap gestito.  
  
 Gli ID oggetto restituiti da `RootReferences2` non sono validi durante il callback stesso, perché è possibile che il Garbage Collection stia spostando gli oggetti dagli indirizzi precedenti ai nuovi indirizzi. I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `RootReferences2`. Quando viene chiamato [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) , tutti gli oggetti sono stati spostati nelle nuove posizioni e possono essere controllati in modo sicuro.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
