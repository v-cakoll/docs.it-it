---
title: Funzione FunctionIDMapper
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
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 24e48ecb551a5faacc7da94b857b2e260f5aeca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="functionidmapper-function"></a>Funzione FunctionIDMapper
Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da utilizzare per il [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), e [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) i callback per tale funzione. `FunctionIDMapper` consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `funcId`  
 [in] Identificatore della funzione di cui eseguire nuovamente il mapping.  
  
 `pbHookFunction`  
 [out] Un puntatore a un valore che il profiler imposta su `true` se vuole ricevere `FunctionEnter2`, `FunctionLeave2`, e `FunctionTailcall2` callback; in caso contrario, questo valore viene impostato su `false`.  
  
## <a name="return-value"></a>Valore restituito  
 Il profiler restituisce un valore che il motore di esecuzione usa come identificatore alternativo della funzione. Il valore restituito non può essere null a meno che non sia restituito `false` in `pbHookFunction`. In caso contrario, un valore restituito null produrrà risultati imprevedibili, compresa la probabilmente un arresto del processo.  
  
## <a name="remarks"></a>Note  
 Il `FunctionIDMapper` funzione è un callback. Viene implementata dal profiler per modificare il mapping di un ID funzione a un altro identificatore che è più utile per il profiler. Il `FunctionIDMapper` restituisce l'ID alternativo da utilizzare per qualsiasi funzione specificata. Il motore di esecuzione rispetta quindi la richiesta del profiler passando tale ID alternativo, oltre all'ID funzione tradizionale, al profiler nel `clientData` parametro il `FunctionEnter2`, `FunctionLeave2`, e `FunctionTailcall2` hook, per identificare la funzione per cui viene chiamato l'hook.  
  
 È possibile utilizzare il [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) specificare l'implementazione del metodo di `FunctionIDMapper` (funzione). È possibile chiamare il `ICorProfilerInfo::SetFunctionIDMapper` metodo una sola volta e si consiglia di eseguire questa operazione nel [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.  
  
 Per impostazione predefinita, si presuppone che un profiler che imposta il flag COR_PRF_MONITOR_ENTERLEAVE tramite [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), e gli hook tramite [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), dovrebbe essere visualizzato il `FunctionEnter2`, `FunctionLeave2`, e `FunctionTailcall2` i callback per ogni funzione. Tuttavia, i profiler possono implementare `FunctionIDMapper` per evitare selettivamente di ricevere i callback per determinate funzioni impostando `pbHookFunction` a `false`.  
  
 I profiler devono poter supportare i casi in cui più thread di un'applicazione profilata chiamano il metodo/funzione stesso contemporaneamente. In questi casi, il profiler può ricevere più `FunctionIDMapper` i callback per lo stesso `FunctionID`. Il profiler deve essere determinato restituire gli stessi valori da questo callback quando viene chiamato più volte con lo stesso `FunctionID`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [Funzione FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [Funzione FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [Funzione FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [Funzione FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
