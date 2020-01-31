---
title: Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: f7bc1954d11134a4515d2e29e9e0eb1626ae5d26
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863428"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks
Specifica le funzioni implementate dal profiler da chiamare sugli hook "Enter", "Leave" e "tailcall" delle funzioni gestite.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFuncEnter`  
 in Puntatore all'implementazione da utilizzare come callback [FunctionEnter](functionenter-function.md) .  
  
 `pFuncLeave`  
 in Puntatore all'implementazione da utilizzare come callback [FunctionLeave](functionleave-function.md) .  
  
 `pFuncTailcall`  
 in Puntatore all'implementazione da utilizzare come callback [FunctionTailcall](functiontailcall-function.md) .  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 1,0 ogni puntatore a funzione può essere null per disabilitare il callback corrispondente.  
  
 Può essere attivo un solo set di callback alla volta. Se quindi un profiler chiama sia `SetEnterLeaveFunctionHooks` che [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), `SetEnterLeaveFunctionHooks2` avrà la precedenza.  
  
 Il metodo `SetEnterLeaveFunctionHooks` può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
