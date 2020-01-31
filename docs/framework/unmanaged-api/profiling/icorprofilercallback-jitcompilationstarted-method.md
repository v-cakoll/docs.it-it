---
title: Metodo ICorProfilerCallback::JITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: e05cb944ea4f3a9ca718dc22c6cd726b6a516ea9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866234"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>Metodo ICorProfilerCallback::JITCompilationStarted
Notifica al profiler che il compilatore just-in-time (JIT) ha iniziato a compilare una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 in ID della funzione per la quale viene avviata la compilazione.  
  
 `fIsSafeToBlock`  
 in Valore che indica al profiler se il blocco influirà sul funzionamento del runtime. Il valore è `true` se il blocco può causare la restituzione del thread chiamante da parte del runtime. in caso contrario, `false`.  
  
 Sebbene il valore `true` non danneggi il runtime, può alterare i risultati della profilatura.  
  
## <a name="remarks"></a>Note  
 È possibile ricevere più di una coppia di `JITCompilationStarted` e [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) chiama per ogni funzione a causa del modo in cui il runtime gestisce i costruttori della classe. Ad esempio, il runtime avvia il metodo di compilazione JIT A, ma è necessario eseguire il costruttore della classe B. Pertanto, il runtime compila in modalità JIT il costruttore per la classe B e lo esegue. Mentre il costruttore è in esecuzione, effettua una chiamata al metodo a, che fa in modo che il metodo a venga nuovamente compilato tramite JIT. In questo scenario, la prima compilazione JIT del metodo A è stata interrotta. Tuttavia, entrambi i tentativi di compilare tramite JIT il metodo A vengono segnalati con gli eventi di compilazione JIT. Se il profiler sostituisce il codice MSIL (Microsoft Intermediate Language) per il metodo A chiamando il metodo [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) , questa operazione deve essere eseguita per entrambi gli eventi `JITCompilationStarted`, ma può usare lo stesso blocco MSIL per entrambi.  
  
 I profiler devono supportare la sequenza di callback JIT nei casi in cui due thread eseguono contemporaneamente i callback. Ad esempio, il thread A chiama `JITCompilationStarted`. Tuttavia, prima che il thread A chiami `JITCompilationFinished`, il thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID funzione dal callback `JITCompilationStarted` del thread a. Potrebbe sembrare che l'ID funzione non sia ancora valido perché una chiamata a `JITCompilationFinished` non è ancora stata ricevuta dal profiler. Tuttavia, in un caso come questo, l'ID funzione è valido.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
