---
title: Metodo ICorProfilerCallback2::FinalizeableObjectQueued
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: e2e01c396a67614464e3d4ca50de992388961463
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499823"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a>Metodo ICorProfilerCallback2::FinalizeableObjectQueued
Notifica all'Code Profiler che un oggetto con un finalizzatore è stato accodato al thread del finalizzatore per l'esecuzione del relativo `Finalize` metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a>Parametri  
 `finalizerFlags`  
 in Valore dell'enumerazione [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) che descrive gli aspetti del finalizzatore.  
  
 `objectID`  
 in ID dell'oggetto che è stato accodato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
