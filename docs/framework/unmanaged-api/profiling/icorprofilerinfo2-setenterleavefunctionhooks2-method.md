---
title: Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bea9be4db2730a67485ef9a504bbc69c096e76c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
Specifica di funzioni implementate dal profiler venga chiamata per le versioni aggiornate del "Immettere", "lasciare" e "tailcall" hook delle funzioni gestite.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pFuncEnter`  
 [in] Un puntatore all'implementazione da usare come il [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.  
  
 `pFuncLeave`  
 [in] Un puntatore all'implementazione da usare come il [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.  
  
 `pFuncTailcall`  
 [in] Un puntatore all'implementazione da usare come il [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.  
  
## <a name="remarks"></a>Note  
 Il `SetEnterLeaveFunctionHooks2` è simile al metodo di [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) metodo. Utilizzare il primo per specificare le funzioni da utilizzare come le versioni più recenti di invio lasciare/tali callback e quest'ultimo per specificare le funzioni da utilizzare come le versioni precedenti dell'invio lasciare/tali callback.  
  
 Un solo set di callback può essere attivo contemporaneamente. Pertanto, se un profiler chiama sia `ICorProfilerInfo::SetEnterLeaveFunctionHooks` e `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` viene utilizzato.  
  
 Il `SetEnterLeaveFunctionHooks2` metodo può essere chiamato solo da del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
