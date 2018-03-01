---
title: Metodo ICorProfilerCallback2::RootReferences2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 29a5a3051b75df18a08498369aa5707a53caf75f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2rootreferences2-method"></a>Metodo ICorProfilerCallback2::RootReferences2
Notifica al profiler sui riferimenti principali dopo un'operazione di garbage collection. Questo metodo è un'estensione del [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cRootRefs`  
 [in] Il numero di elementi di `rootRefIds`, `rootKinds`, `rootFlags`, e `rootIds` matrici.  
  
 `rootRefIds`  
 [in] Matrice di ID oggetto, ognuno dei quali fa riferimento a un oggetto statico o un oggetto di nello stack. Gli elementi di `rootKinds` matrice forniscono informazioni per classificare gli elementi corrispondenti nel `rootRefIds` matrice.  
  
 `rootKinds`  
 [in] Matrice di [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) valori che indicano il tipo di radice di garbage collection.  
  
 `rootFlags`  
 [in] Matrice di [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) valori che descrivono le proprietà di una radice di garbage collection.  
  
 `rootIds`  
 [in] Una matrice di UINT_PTR valori che puntano a un intero che contiene informazioni aggiuntive sulla radice di garbage collection, in base al valore di `rootKinds` parametro.  
  
 Se il tipo di radice è uno stack, l'ID di radice è per la funzione che contiene la variabile. Se l'ID della radice è 0, la funzione è una funzione senza nome all'interna di CLR. Se il tipo di radice è un handle, l'ID di radice è per l'handle di garbage collection. Per altri tipi di primo livello, l'ID è un valore opaco e deve essere ignorato.  
  
## <a name="remarks"></a>Note  
 Il `rootRefIds`, `rootKinds`, `rootFlags`, e `rootIds` sono matrici parallele. Vale a dire `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, e `rootIds[i]` riguardano la stessa radice.  
  
 Entrambi `RootReferences` e `RootReferences2` vengono chiamati per notificare al profiler. I profiler in genere implementano un metodo o l'altro, ma non ad entrambi, in quanto le informazioni passate in `RootReferences2` è un superset di passati `RootReferences`.  
  
 È possibile che le voci in `rootRefIds` pari a zero, il che implica che il riferimento alla radice corrispondente è null e non fa riferimento a un oggetto nell'heap gestito.  
  
 L'ID di oggetto restituito da `RootReferences2` non validi durante il callback vero e proprio, perché l'operazione di garbage collection potrebbe essere ancora spostando gli oggetti provenienti da indirizzi precedenti a nuovi indirizzi. I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `RootReferences2`. Quando [ICorProfilerCallback2::](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) viene chiamato, tutti gli oggetti sono stati spostati nelle nuove posizioni e possono essere controllati in modo sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
