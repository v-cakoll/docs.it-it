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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89c7b0fe0f3ade3f57aa50b100bc9b4ecc904a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451997"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>Metodo ICorProfilerCallback::JITCachedFunctionSearchFinished
Notifica al profiler che una ricerca è stato completato per una funzione che è stata compilata in precedenza utilizzando il generatore di immagini Native (NGen.exe).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione per cui è stata eseguita la ricerca.  
  
 `result`  
 [in] Il valore di [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumerazione che indica il risultato della ricerca.  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 2.0, il [ICorProfilerCallback:: JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) e `JITCachedFunctionSearchFinished` i callback non verranno effettuati per tutte le funzioni nelle immagini NGen normali. Solo le immagini NGen ottimizzate per un profiler genererà i callback per tutte le funzioni nell'immagine. Tuttavia, a causa del sovraccarico aggiuntivo, un profiler deve richiedere immagini NGen ottimizzate profiler solo se intende utilizzare questi callback per forzare una funzione compilati just-in-time (JIT). In caso contrario, il profiler deve utilizzare una strategia lenta per raccogliere le informazioni di funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
