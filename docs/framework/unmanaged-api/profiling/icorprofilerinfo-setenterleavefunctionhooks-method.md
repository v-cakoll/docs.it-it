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
ms.openlocfilehash: cf0726a12b0274fd7a38e82b66c33430d26b031a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497452"
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
  
## <a name="remarks"></a>Osservazioni  
 In .NET Framework versione 1,0 ogni puntatore a funzione può essere null per disabilitare il callback corrispondente.  
  
 Può essere attivo un solo set di callback alla volta. Se quindi un profiler chiama sia `SetEnterLeaveFunctionHooks` che [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), `SetEnterLeaveFunctionHooks2` avrà la precedenza.  
  
 Il `SetEnterLeaveFunctionHooks` metodo può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
