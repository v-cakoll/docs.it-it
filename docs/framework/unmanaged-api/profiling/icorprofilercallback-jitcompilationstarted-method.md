---
title: Metodo ICorProfilerCallback::JITCompilationStarted
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 12a25f452ccb121ef7ebcae05048eb7116b4ac48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>Metodo ICorProfilerCallback::JITCompilationStarted
Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato per la compilazione di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione per cui viene avviata la compilazione.  
  
 `fIsSafeToBlock`  
 [in] Un valore che indica al profiler se il blocco verrà influiscono sul funzionamento di runtime. Il valore è `true` se il blocco può provocare il runtime di attesa per il thread chiamante da questo callback; in caso contrario, `false`.  
  
 Anche se il valore `true` non danneggerà la fase di esecuzione, possono distorcere i risultati della profilatura.  
  
## <a name="remarks"></a>Note  
 È possibile ricevere più di una coppia di `JITCompilationStarted` e [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) chiama per ogni funzione a causa del modo il runtime gestisce i costruttori di classe. Ad esempio, all'avvio di runtime per il metodo di compilazione JIT, ma il costruttore della classe per classe B deve essere eseguito. Pertanto, il runtime compila tramite JIT il costruttore di classe B e lo esegue. Durante l'esecuzione, il costruttore che effettua una chiamata al metodo a, che determina il metodo A per essere compilato tramite JIT. In questo scenario, viene interrotta la compilazione JIT prima del metodo. Tuttavia, sono inclusi entrambi i tentativi di metodo a compilazione JIT con eventi di compilazione JIT. Se il profiler per la sostituzione chiamata di codice di Microsoft intermediate language (MSIL) per il metodo di [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) metodo, deve essere eseguita sia per `JITCompilationStarted` eventi, ma può utilizzare lo stesso blocco MSIL per entrambi.  
  
 I profiler devono supportare la sequenza di callback JIT nei casi in cui due thread effettuano callback simultaneamente. Ad esempio, il thread chiama `JITCompilationStarted`. Tuttavia, prima di un thread chiama `JITCompilationFinished`, thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID della funzione del thread `JITCompilationStarted` callback. Potrebbe sembrare che l'ID della funzione non deve ancora essere valido perché una chiamata a `JITCompilationFinished` non ha ancora ricevuto dal profiler. In caso come questo, tuttavia, l'ID della funzione è valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
