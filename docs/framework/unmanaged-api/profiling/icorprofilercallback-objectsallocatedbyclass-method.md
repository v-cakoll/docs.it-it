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
ms.openlocfilehash: 9ba021ec223d00e57081567b76f70f59768e6b9a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445865"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>Metodo ICorProfilerCallback::ObjectsAllocatedByClass
Notifica al profiler il numero di istanze di ogni classe specificata create dopo la Garbage Collection più recente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a>Parametri  
 `cClassCount`  
 in Dimensioni delle matrici `classIds` e `cObjects`.  
  
 `classIds`  
 in Matrice di ID di classe, in cui ogni ID specifica una classe con una o più istanze.  
  
 `cObjects`  
 in Matrice di numeri interi, dove ogni numero intero specifica il numero di istanze per la classe corrispondente nella matrice `classIds`.  
  
## <a name="remarks"></a>Note  
 Le matrici `classIds` e `cObjects` sono matrici parallele. Ad esempio, `classIds[i]` e `cObjects[i]` fanno riferimento alla stessa classe. Se non è stata creata alcuna istanza di una classe dalla Garbage Collection precedente, la classe viene omessa. Il callback `ObjectsAllocatedByClass` non segnalerà gli oggetti allocati nell'heap degli oggetti grandi.  
  
 I numeri segnalati da `ObjectsAllocatedByClass` sono solo stime. Per i conteggi esatti, utilizzare [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 La matrice di `classIds` può contenere una o più voci null se la matrice `cObjects` corrispondente contiene tipi che stanno scaricando.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
