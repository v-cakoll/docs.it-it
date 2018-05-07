---
title: Metodo ICorProfilerCallback::ObjectsAllocatedByClass
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78dde5c50666333c02c8c1a9a167e17af3f40341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>Metodo ICorProfilerCallback::ObjectsAllocatedByClass
Notifica al profiler il numero di istanze di ogni classe specificata che sono stati creati dall'operazione di garbage collection più recente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a>Parametri  
 `cClassCount`  
 [in] Le dimensioni del `classIds` e `cObjects` matrici.  
  
 `classIds`  
 [in] Matrice di ID, in cui ogni ID specifica una classe con una o più istanze di classe.  
  
 `cObjects`  
 [in] Una matrice di interi, in cui ogni integer che specifica il numero di istanze per la classe corrispondente nel `classIds` matrice.  
  
## <a name="remarks"></a>Note  
 Il `classIds` e `cObjects` sono matrici parallele. Ad esempio, `classIds[i]` e `cObjects[i]` riferimento alla stessa classe. Se nessuna istanza di una classe è stata creata dall'operazione di garbage collection precedente, la classe viene omesso. Il `ObjectsAllocatedByClass` callback non segnalerà gli oggetti allocati nell'heap degli oggetti di grandi dimensioni.  
  
 I numeri segnalati da `ObjectsAllocatedByClass` sono solo stime. Per i conteggi esatti, utilizzare [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 Il `classIds` matrice può contenere uno o più voci null se il corrispondente `cObjects` matrice dispone di tipi in fase di scaricamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
