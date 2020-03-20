---
title: Funzione FunctionIDMapper
ms.date: 03/30/2017
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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175174"
---
# <a name="functionidmapper-function"></a>Funzione FunctionIDMapper
Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da utilizzare nei callback [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)e [FunctionTailcall2](functiontailcall2-function.md) per tale funzione. `FunctionIDMapper` consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcId`

  \[in] L'identificatore di funzione da rimappare.

- `pbHookFunction`

  \[out] Un puntatore a un `true` valore che il `FunctionEnter2` `FunctionLeave2`profiler `FunctionTailcall2` imposta su se desidera ricevere , e callback; in caso contrario, `false`imposta questo valore su .

## <a name="return-value"></a>Valore restituito  
 Il profiler restituisce un valore che il motore di esecuzione usa come identificatore alternativo della funzione. Il valore restituito non può essere null a meno che non sia restituito `false` in `pbHookFunction`. In caso contrario, un valore restituito null produrrà risultati imprevisti, inclusa la possibile interruzione del processo.  
  
## <a name="remarks"></a>Osservazioni  
 La `FunctionIDMapper` funzione è un callback. Viene implementato dal profiler per rimappare un ID funzione a un altro identificatore più utile per il profiler. Restituisce `FunctionIDMapper` l'ID alternativo da utilizzare per qualsiasi funzione specificata. Il motore di esecuzione rispetta quindi la richiesta del profiler passando questo ID alternativo, oltre `clientData` all'ID `FunctionEnter2` `FunctionLeave2`funzione `FunctionTailcall2` tradizionale, al profiler nel parametro di , e hook, per identificare la funzione per la quale viene chiamato l'hook.  
  
 È possibile utilizzare il metodo [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) `FunctionIDMapper` per specificare l'implementazione della funzione. È possibile `ICorProfilerInfo::SetFunctionIDMapper` chiamare il metodo una sola volta e si consiglia di eseguire questa operazione nel callback di [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) .  
  
 Per impostazione predefinita, si presuppone che un profiler che imposta il flag di COR_PRF_MONITOR_ENTERLEAVE utilizzando [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md)e che imposta gli hook tramite [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), riceva i callback `FunctionEnter2`, `FunctionLeave2`e `FunctionTailcall2` per ogni funzione. Tuttavia, i `FunctionIDMapper` profiler possono implementare per evitare in `pbHookFunction` `false`modo selettivo la ricezione di questi callback per determinate funzioni impostando su .  
  
 I profiler devono essere tolleranti nei casi in cui più thread di un'applicazione profilata chiamano contemporaneamente lo stesso metodo/funzione. In questi casi, il `FunctionIDMapper` profiler può ricevere `FunctionID`più callback per lo stesso oggetto . Il profiler deve essere certo di restituire gli stessi valori da `FunctionID`questo callback quando viene chiamato più volte con lo stesso oggetto .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [Funzione FunctionIDMapper2](functionidmapper2-function.md)
- [Funzione FunctionEnter2](functionenter2-function.md)
- [Funzione FunctionLeave2](functionleave2-function.md)
- [Funzione FunctionTailcall2](functiontailcall2-function.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
