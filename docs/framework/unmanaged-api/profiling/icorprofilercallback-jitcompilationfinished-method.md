---
title: Metodo ICorProfilerCallback::JITCompilationFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9719ce1474c2111692c6176655b75bd2d7edf923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>Metodo ICorProfilerCallback::JITCompilationFinished
Notifica al profiler che il compilatore di just-in-time (JIT) ha terminato la compilazione di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che è stata compilata.  
  
 `hrStatus`  
 [in] Un valore che indica se la compilazione è stata completata.  
  
 `fIsSafeToBlock`  
 [in] Un valore che indica al profiler se il blocco verrà influiscono sul funzionamento di runtime. Il valore è `true` se il blocco può provocare il runtime di attesa per il thread chiamante da questo callback; in caso contrario, `false`.  
  
 Anche se il valore `true` non danneggerà la fase di esecuzione, possono distorcere i risultati della profilatura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [JITCompilationStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
