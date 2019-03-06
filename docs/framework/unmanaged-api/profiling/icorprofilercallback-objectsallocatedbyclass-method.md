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
ms.openlocfilehash: e26e7ac9b89e005d9520ad860cf3acee7d3cc6cc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479753"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>Metodo ICorProfilerCallback::ObjectsAllocatedByClass
Notifica al profiler sul numero di istanze di ogni classe specificata che sono stati creati dopo l'ultima garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a>Parametri  
 `cClassCount`  
 [in] Le dimensioni dei `classIds` e `cObjects` matrici.  
  
 `classIds`  
 [in] Matrice di ID, dove ogni ID specifica una classe con una o più istanze di classe.  
  
 `cObjects`  
 [in] Matrice di interi, in cui ogni integer che specifica il numero di istanze per la classe corrispondente nel `classIds` matrice.  
  
## <a name="remarks"></a>Note  
 Il `classIds` e `cObjects` sono matrici parallele. Ad esempio, `classIds[i]` e `cObjects[i]` fare riferimento alla classe stessa. Se non è stata creata alcuna istanza di una classe dopo la precedente di garbage collection, la classe viene omesso. Il `ObjectsAllocatedByClass` callback non segnalerà gli oggetti allocati nell'heap oggetto grande.  
  
 I numeri di segnalati da `ObjectsAllocatedByClass` sono solo una stima. Per i conteggi esatti, utilizzare [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 Il `classIds` matrice può contenere una o più voci null se il corrispondente `cObjects` matrice dispone di tipi in fase di scaricamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
