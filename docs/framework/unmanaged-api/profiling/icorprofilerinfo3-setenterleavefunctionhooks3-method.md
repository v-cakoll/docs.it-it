---
title: Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: eb658d682ce589b7dfdcfc0228d0c657310e6f7a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496233"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a>Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
Specifica le funzioni implementate dal profiler che verranno chiamate nelle funzioni [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFuncEnter3`  
 in Puntatore all'implementazione da utilizzare come `FunctionEnter3` callback.  
  
 `pFuncLeave3`  
 in Puntatore all'implementazione da utilizzare come `FunctionLeave3` callback.  
  
 `pFuncTailcall3`  
 in Puntatore all'implementazione da utilizzare come `FunctionTailcall3` callback.  
  
## <a name="remarks"></a>Osservazioni  
 Gli hook [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md) non forniscono stack frame e l'ispezione degli argomenti. Per accedere a tali informazioni, `COR_PRF_ENABLE_FUNCTION_ARGS` `COR_PRF_ENABLE_FUNCTION_RETVAL` è necessario impostare i flag, e/o `COR_PRF_ENABLE_FRAME_INFO` . Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il metodo [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.  
  
 Solo un set di callback può essere attivo alla volta e la versione più recente ha la precedenza. Se pertanto un profiler chiama sia il [metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) che il `SetEnterLeaveFunctionHooks3` metodo, `SetEnterLeaveFunctionHooks3` viene utilizzato.  
  
 Il `SetEnterLeaveFunctionHooks3` metodo può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
- [ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
