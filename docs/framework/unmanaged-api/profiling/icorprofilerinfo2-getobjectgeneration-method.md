---
title: Metodo ICorProfilerInfo2::GetObjectGeneration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetObjectGeneration
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e90139f96638dbb1a183f98e754838ff52424fc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a>Metodo ICorProfilerInfo2::GetObjectGeneration
Ottiene il segmento dell'heap che contiene l'oggetto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
#### <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID dell'oggetto.  
  
 `range`  
 [out] Un puntatore a un [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) struttura, che descrive un intervallo (blocco) di memoria all'interno della generazione viene sottoposto a garbage collection. Questo intervallo contiene l'oggetto specificato.  
  
## <a name="remarks"></a>Note  
 Il `GetObjectGeneration` metodo può essere chiamato da qualsiasi callback del profiler, purché non sia in corso la garbage collection. Ovvero, può essere chiamato da qualsiasi callback a eccezione di quelli che si verificano tra [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) e [ICorProfilerCallback2::](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
