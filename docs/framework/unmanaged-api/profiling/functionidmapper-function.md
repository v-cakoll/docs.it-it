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
ms.openlocfilehash: d5bf6626e2c6ba15fa9a5da08bcf2d9052866750
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866944"
---
# <a name="functionidmapper-function"></a>Funzione FunctionIDMapper
Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da usare nei callback [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)e [FunctionTailcall2](functiontailcall2-function.md) per tale funzione. `FunctionIDMapper` consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcId`

  \[in] identificatore di funzione di cui eseguire il mapping.

- `pbHookFunction`

  \[out] puntatore a un valore che il profiler imposta `true` se desidera ricevere callback `FunctionEnter2`, `FunctionLeave2`e `FunctionTailcall2`; in caso contrario, imposta questo valore su `false`.

## <a name="return-value"></a>Valore restituito  
 Il profiler restituisce un valore che il motore di esecuzione usa come identificatore alternativo della funzione. Il valore restituito non può essere null a meno che non sia restituito `false` in `pbHookFunction`. In caso contrario, un valore restituito null produrrà risultati imprevedibili, inclusa la possibilità di arrestare il processo.  
  
## <a name="remarks"></a>Note  
 La funzione `FunctionIDMapper` è un callback. Viene implementato dal profiler per eseguire il mapping di un ID funzione a un altro identificatore più utile per il profiler. Il `FunctionIDMapper` restituisce l'ID alternativo da usare per una determinata funzione. Il motore di esecuzione rispetta quindi la richiesta del profiler passando questo ID alternativo, oltre all'ID funzione tradizionale, al profiler nel parametro `clientData` degli hook `FunctionEnter2`, `FunctionLeave2`e `FunctionTailcall2` per identificare la funzione per la quale viene chiamato l'hook.  
  
 È possibile usare il metodo [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) per specificare l'implementazione della funzione `FunctionIDMapper`. È possibile chiamare il metodo `ICorProfilerInfo::SetFunctionIDMapper` solo una volta e si consiglia di eseguire questa operazione nel callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .  
  
 Per impostazione predefinita, si presuppone che un profiler che imposta il flag di COR_PRF_MONITOR_ENTERLEAVE tramite [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)e che imposta hook tramite [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debba ricevere i callback `FunctionEnter2`, `FunctionLeave2`e `FunctionTailcall2` per ogni funzione. Tuttavia, i profiler possono implementare `FunctionIDMapper` per evitare selettivamente la ricezione di questi callback per determinate funzioni impostando `pbHookFunction` su `false`.  
  
 I profiler devono essere tolleranti nei casi in cui più thread di un'applicazione profilata chiamano simultaneamente lo stesso metodo o funzione. In questi casi, il profiler può ricevere più callback `FunctionIDMapper` per lo stesso `FunctionID`. Il profiler deve essere determinato per restituire gli stessi valori da questo callback quando viene chiamato più volte con lo stesso `FunctionID`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [Funzione FunctionIDMapper2](functionidmapper2-function.md)
- [Funzione FunctionEnter2](functionenter2-function.md)
- [Funzione FunctionLeave2](functionleave2-function.md)
- [Funzione FunctionTailcall2](functiontailcall2-function.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
