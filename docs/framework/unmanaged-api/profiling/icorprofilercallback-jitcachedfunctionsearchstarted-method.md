---
title: Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09fcdc67dc730b59b76a2da9f6ccea04800e20c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted
Notifica al profiler che si è iniziata una ricerca per una funzione che è stata compilata in precedenza utilizzando il generatore di immagini Native (NGen.exe).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione per cui viene eseguita la ricerca.  
  
 `pbUseCachedFunction`  
 [out] `true` se il motore di esecuzione deve usare la versione memorizzata nella cache di una funzione (se disponibile); in caso contrario `false`. Se il valore è `false`, il motore di esecuzione JIT compila la funzione anziché una versione che non è compilato tramite JIT.  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 2.0, il `JITCachedFunctionSearchStarted` e [metodo ICorProfilerCallback:: JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callback non verranno effettuati per tutte le funzioni nelle immagini NGen normali. Solo le immagini NGen ottimizzate per un profilo genererà i callback per tutte le funzioni nell'immagine. Tuttavia, a causa del sovraccarico aggiuntivo, un profiler deve richiedere immagini NGen ottimizzate profiler solo se intende utilizzare questi callback per forzare una funzione compilati just-in-time (JIT). In caso contrario, il profiler deve utilizzare una strategia lenta per raccogliere le informazioni di funzione.  
  
 I profiler devono supportare i casi in cui più thread di un'applicazione profilata chiamano il metodo stesso contemporaneamente. Ad esempio, il thread chiama `JITCachedFunctionSearchStarted` e il profiler risponde impostando *pbUseCachedFunction*su FALSE per forzare la compilazione JIT. Thread chiama quindi i metodi [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) e [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Ora il thread B chiama `JITCachedFunctionSearchStarted` per la stessa funzione. Anche se il profiler ha dichiarato la propria intenzione di compilazione JIT la funzione, il profiler avrà ricevuto il callback secondo perché il thread B invia il callback prima che il profiler ha risposto alla chiamata del thread per `JITCachedFunctionSearchStarted`. L'ordine in cui i thread chiamate dipende dalla modalità di programmazione i thread.  
  
 Quando il profiler riceve callback duplicati, è necessario impostare il valore a cui fa riferimento `pbUseCachedFunction` sullo stesso valore per tutti i callback duplicati. Ovvero, quando `JITCachedFunctionSearchStarted` viene chiamato più volte con lo stesso `functionId` valore, il profiler deve rispondere lo stesso ogni volta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
