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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5ba90ce4523fcc55fca3f84a78fa4cfeb6a93f0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782824"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>Metodo ICorProfilerCallback::JITCompilationStarted
Notifica al profiler che il compilatore JIT just-in-time è iniziata la compilazione di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione per il quale viene avviata la compilazione.  
  
 `fIsSafeToBlock`  
 [in] Un valore che indica al profiler, se il blocco avrà effetto sul funzionamento del runtime. Il valore è `true` se il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; in caso contrario, `false`.  
  
 Anche se un valore di `true` non danneggerà la fase di esecuzione, possono distorcere i risultati della profilatura.  
  
## <a name="remarks"></a>Note  
 È possibile ricevere più di una coppia di `JITCompilationStarted` e [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) chiama per ogni funzione del modo in cui il runtime gestisce i costruttori di classe. Ad esempio, il runtime inizi metodo a compilazione JIT, ma deve essere eseguito il costruttore della classe per classe B. Pertanto, il runtime compila tramite JIT il costruttore per la classe B e lo esegue. Mentre il costruttore è in esecuzione, che effettua una chiamata al metodo A, che fa sì che il metodo a essere compilato tramite JIT. In questo scenario, viene interrotta la compilazione JIT prima del metodo. Tuttavia, entrambi i tentativi di metodo a compilazione JIT vengono segnalati con gli eventi di compilazione JIT. Se il profiler per sostituire il codice Microsoft intermediate language (MSIL) per il metodo chiamando il [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) metodo, l'operazione deve essere eseguita per entrambi `JITCompilationStarted` gli eventi, ma è possibile usare lo stesso blocco di codice MSIL per entrambi.  
  
 I profiler devono supportare la sequenza di callback JIT in casi in cui due thread contemporaneamente dei callback. Ad esempio, il thread chiama `JITCompilationStarted`. Tuttavia, prima che il thread chiami `JITCompilationFinished`, il thread B chiamate [ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID di funzione del thread `JITCompilationStarted` callback. Può sembrare che l'ID di funzione non deve ancora essere valido perché una chiamata a `JITCompilationFinished` non ha ancora ricevuto dal profiler. In un caso come questo, tuttavia, l'ID di funzione è valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
