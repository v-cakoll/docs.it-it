---
title: Metodo ICorProfilerInfo2::GetObjectGeneration
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
ms.openlocfilehash: b75de955e3b6857c9cc1b5411df4b0f262c4cb9a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862698"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a>Metodo ICorProfilerInfo2::GetObjectGeneration
Ottiene il segmento dell'heap che contiene l'oggetto specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 in ID dell'oggetto.  
  
 `range`  
 out Puntatore a una struttura di [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , che descrive un intervallo, ovvero un blocco, della memoria all'interno della generazione che è in fase di Garbage Collection. Questo intervallo contiene l'oggetto specificato.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetObjectGeneration` può essere chiamato da qualsiasi callback del profiler, purché Garbage Collection non sia in corso. Ovvero può essere chiamato da qualsiasi callback, ad eccezione di quelli che si verificano tra [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) e [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
