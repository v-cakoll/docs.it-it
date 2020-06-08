---
title: Metodo ICorProfilerCallback::JITCachedFunctionSearchFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: 6efc9d407bb95f75a79252b2dfad85b396d2164a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500078"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>Metodo ICorProfilerCallback::JITCachedFunctionSearchFinished
Notifica al profiler che una ricerca è stata completata per una funzione compilata in precedenza utilizzando il generatore di immagini native (NGen. exe).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a>Parametri

- `functionId`

  \[in] ID della funzione per la quale è stata eseguita la ricerca.

- `result`

  \[in] valore dell'enumerazione [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) che indica il risultato della ricerca.

## <a name="remarks"></a>Osservazioni  
 Nella versione .NET Framework 2,0, il metodo [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) e i `JITCachedFunctionSearchFinished` callback non verranno eseguiti per tutte le funzioni nelle immagini NGen normali. Solo le immagini NGen ottimizzate per un profiler genereranno callback per tutte le funzioni nell'immagine. Tuttavia, a causa dell'overhead aggiuntivo, un profiler deve richiedere immagini NGen ottimizzate per il profiler solo se intende usare questi callback per forzare la compilazione di una funzione JIT (just-in-Time). In caso contrario, il profiler deve usare una strategia Lazy per raccogliere informazioni sulle funzioni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
