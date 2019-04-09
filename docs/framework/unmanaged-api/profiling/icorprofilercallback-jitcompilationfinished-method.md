---
title: Metodo ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1abc4dd209581c9f7c8e950ea1addc74c611d248
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226058"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>Metodo ICorProfilerCallback::JITCompilationFinished
Notifica al profiler che il compilatore JIT just-in-time ha terminato la compilazione di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che è stata compilata.  
  
 `hrStatus`  
 [in] Un valore che indica se la compilazione ha avuto esito positivo.  
  
 `fIsSafeToBlock`  
 [in] Un valore che indica al profiler, se il blocco avrà effetto sul funzionamento del runtime. Il valore è `true` se il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; in caso contrario, `false`.  
  
 Anche se un valore di `true` non danneggerà la fase di esecuzione, possono distorcere i risultati della profilatura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
