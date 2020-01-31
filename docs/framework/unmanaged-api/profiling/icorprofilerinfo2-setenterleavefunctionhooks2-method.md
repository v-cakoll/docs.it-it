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
ms.openlocfilehash: 7eac42e1d8132ca9e6d6c6b43efd43b88c1e5d3d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868577"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>Metodo ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
Specifica le funzioni implementate dal profiler da chiamare sulle versioni aggiornate degli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFuncEnter`  
 in Puntatore all'implementazione da utilizzare come callback [FunctionEnter2](functionenter2-function.md) .  
  
 `pFuncLeave`  
 in Puntatore all'implementazione da utilizzare come callback [FunctionLeave2](functionleave2-function.md) .  
  
 `pFuncTailcall`  
 in Puntatore all'implementazione da utilizzare come callback [FunctionTailcall2](functiontailcall2-function.md) .  
  
## <a name="remarks"></a>Note  
 Il metodo `SetEnterLeaveFunctionHooks2` è simile al metodo [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) . Usare la prima per specificare le funzioni da usare come le versioni più recenti dei callback enter/leave/tailcall e la seconda per specificare le funzioni da usare come versioni precedenti dei callback enter/leave/tailcall.  
  
 È possibile che sia attivo un solo set di callback alla volta. Se quindi un profiler chiama sia `ICorProfilerInfo::SetEnterLeaveFunctionHooks` che `SetEnterLeaveFunctionHooks2`, viene usato `SetEnterLeaveFunctionHooks2`.  
  
 Il metodo `SetEnterLeaveFunctionHooks2` può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
