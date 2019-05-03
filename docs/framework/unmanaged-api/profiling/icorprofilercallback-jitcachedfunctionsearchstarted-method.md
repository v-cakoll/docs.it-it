---
title: Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3550f4da497574ea5076766ad201e9431af52e4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598033"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted
Notifica al profiler che ha avviato una ricerca per una funzione che è stata compilata in precedenza usando il generatore di immagini Native (NGen.exe).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione per cui la ricerca viene eseguita.  
  
 `pbUseCachedFunction`  
 [out] `true` se il motore di esecuzione deve usare la versione memorizzata nella cache di una funzione (se disponibile); in caso contrario `false`. Se il valore è `false`, l'esecuzione motore JIT compila la funzione invece di usare una versione che non è compilato tramite JIT.  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 2.0, il `JITCachedFunctionSearchStarted` e [JITCachedFunctionSearchFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callback non verranno effettuati per tutte le funzioni nelle immagini NGen normali. Solo le immagini NGen ottimizzate per un profilo genererà i callback per tutte le funzioni nell'immagine. Tuttavia, a causa del sovraccarico aggiuntivo, un profiler deve richiedere immagini NGen ottimizzata su profiler solo se intende usare questi callback per forzare una funzione di essere compilati just-in-time (JIT). In caso contrario, il profiler deve usare una strategia lazy per raccogliere informazioni sulle funzioni.  
  
 I profiler devono supportare i casi in cui più thread di un'applicazione profilata chiamano il metodo di stesso contemporaneamente. Ad esempio, il thread chiama `JITCachedFunctionSearchStarted` e il profiler risponde impostando *pbUseCachedFunction*su FALSE per forzare la compilazione JIT. Thread chiama quindi i metodi [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) e [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Ora il thread B chiama `JITCachedFunctionSearchStarted` per la stessa funzione. Anche se il profiler ha indicato la propria intenzione di compilazione JIT la funzione, il profiler riceve il callback secondo perché il thread B invia la richiamata prima che il profiler ha risposto alla chiamata del thread a `JITCachedFunctionSearchStarted`. L'ordine in cui i thread di effettuano chiamate dipende dal modo in cui il thread viene pianificata.  
  
 Quando il profiler riceve i callback duplicati, è necessario impostare il valore a cui fanno riferimento `pbUseCachedFunction` sullo stesso valore per tutte le richiamate duplicate. Ovvero, quando `JITCachedFunctionSearchStarted` viene chiamato più volte con lo stesso `functionId` valore, il profiler deve rispondere lo stesso ogni volta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
