---
title: Metodo ICorProfilerFunctionControl::SetCodegenFlags
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 75414ec3d2b30fe8afc5db1e97c81f34b29a3115
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864674"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>Metodo ICorProfilerFunctionControl::SetCodegenFlags
Imposta uno o più flag dall'enumerazione [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) per controllare la generazione di codice per una funzione JIT (just-in-Time) ricompilata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>Parametri  
 `flags`  
 in Uno o più flag dall'enumerazione [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) .  
  
## <a name="remarks"></a>Note  
 Il profiler ottiene un'istanza di questa interfaccia tramite il callback [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) . `SetCodegenFlags` consente al profiler di controllare la generazione del codice per la funzione ricompilata. Come per tutti gli altri parametri di ricompilazione JIT, i flag di generazione del codice si applicano a tutte le istanze della funzione.  
  
 Il compilatore JIT considera questi flag di compilazione, insieme ad altri flag specificati da altre origini, durante la compilazione di una funzione.  Le altre origini includono il debugger, i flag globali impostati dal profiler all'avvio tramite il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) (con i valori `COR_PRF_DISABLE_INLINING` e `COR_PRF_DISABLE_OPTIMIZATIONS`) e il callback [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) del profiler.  Il compilatore JIT fornisce la precedenza a un'origine che richiede la quantità minima di ottimizzazione.  Se, ad esempio, il profiler specifica `COR_PRF_DISABLE_INLINING` all'avvio, ma non specifica `COR_PRF_CODEGEN_DISABLE_INLINING` nel callback [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) , l'inlining è ancora disabilitato.  Analogamente, se il profiler non specifica `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, ma quindi Disabilita l'incorporamento tramite il callback [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) , l'incorporamento è disabilitato.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md)
