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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7673d6fac2626bc0059204ea77a23686b11638cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452735"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>Metodo ICorProfilerCallback::RuntimeThreadSuspended
Notifica al profiler che il thread specificato è stato sospeso o sta per essere sospesa.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `threadId`  
 [in] L'ID del thread che è stata sospesa.  
  
## <a name="remarks"></a>Note  
 Il `RuntimeThreadSuspended` notifica può verificarsi in qualsiasi momento compreso tra il [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) associati [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback. Le notifiche che si verificano tra [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) e `RuntimeResumeStarted` per i thread che erano in esecuzione nel codice non gestito e sono stati sospesi al momento dell'accesso al runtime.  
  
 In genere, questo callback si verifica subito dopo un thread è sospeso. Tuttavia, se il thread attualmente in esecuzione (il thread che ha chiamato il callback) è quello che viene sospeso, questo callback si verifica prima che il thread è sospeso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
