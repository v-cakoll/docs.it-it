---
title: Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb7c8fa40d260e45ae536f1b58c6ab360f35448e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550643"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
Specifica funzioni implementate dal profiler verrà chiamato sulle versioni aggiornate del "Immettere", "Continua" e "tailcall" hook di funzioni gestite.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pFuncEnter`  
 [in] Un puntatore all'implementazione da usare come le [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.  
  
 `pFuncLeave`  
 [in] Un puntatore all'implementazione da usare come le [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.  
  
 `pFuncTailcall`  
 [in] Un puntatore all'implementazione da usare come le [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.  
  
## <a name="remarks"></a>Note  
 Il `SetEnterLeaveFunctionHooks2` metodo è simile al [SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) (metodo). Utilizzare la precedente per specificare le funzioni da utilizzare come le versioni più recenti di callback invio/leave/tailcall e quest'ultimo per specificare le funzioni da utilizzare come le versioni precedenti dei callback di invio/leave/tailcall.  
  
 Un solo set di callback può essere attivo contemporaneamente. Di conseguenza, se un profiler chiama entrambe `ICorProfilerInfo::SetEnterLeaveFunctionHooks` e `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` viene usato.  
  
 Il `SetEnterLeaveFunctionHooks2` metodo può essere chiamato solo da del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
