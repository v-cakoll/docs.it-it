---
title: Metodo ICorProfilerCallback::RuntimeThreadSuspended
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865870"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>Metodo ICorProfilerCallback::RuntimeThreadSuspended
Notifica al profiler che il thread specificato è stato sospeso o sta per essere sospeso.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadId`  
 in ID del thread che è stato sospeso.  
  
## <a name="remarks"></a>Note  
 La notifica di `RuntimeThreadSuspended` può verificarsi in qualsiasi momento tra i callback ICorProfilerCallback [:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) e i callback [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) associati. Le notifiche che si verificano tra [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) e `RuntimeResumeStarted` sono per i thread che erano in esecuzione nel codice non gestito e sono stati sospesi al momento dell'immissione nel Runtime.  
  
 In genere, questo callback si verifica subito dopo la sospensione di un thread. Tuttavia, se il thread attualmente in esecuzione (il thread che ha chiamato questo callback) è quello che viene sospeso, questo callback si verificherà immediatamente prima della sospensione del thread.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)
