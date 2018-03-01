---
title: Metodo ICorProfilerFunctionControl::SetCodegenFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9264e717da62c88b6f2f6eca262b5635fc928741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>Metodo ICorProfilerFunctionControl::SetCodegenFlags
Imposta uno o più flag dal [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumerazione per controllare la generazione di codice per un just-in-time (JIT) ricompilate (funzione).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a>Parametri  
 `flags`  
 [in] Uno o più flag dal [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumerazione.  
  
## <a name="remarks"></a>Note  
 Il profiler ottiene un'istanza di questa interfaccia con il [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback. `SetCodegenFlags`consente al profiler di controllare la generazione di codice per la funzione ricompilata. Come con tutti gli altri parametri di ricompilazione JIT, i flag di generazione di codice si applicano a tutte le istanze della funzione.  
  
 Il compilatore JIT considera questi flag di compilazione, con altri flag specificati da altre origini, durante la compilazione di una funzione.  Le altre origini includono il debugger, impostata dal profiler all'avvio dal flag globali utilizzando il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) (metodo) (con i valori `COR_PRF_DISABLE_INLINING` e `COR_PRF_DISABLE_OPTIMIZATIONS`) e il profiler [ ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.  Il compilatore JIT assegna la precedenza a un'origine che richiede la quantità minima di ottimizzazione.  Ad esempio, se il profiler specifica `COR_PRF_DISABLE_INLINING` all'avvio, ma non specifica `COR_PRF_CODEGEN_DISABLE_INLINING` nel [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, l'incorporamento è ancora disabilitata.  Analogamente, se il profiler specificato non è `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, ma disabilita quindi inline utilizzando il [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, l'incorporamento è disabilitato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
