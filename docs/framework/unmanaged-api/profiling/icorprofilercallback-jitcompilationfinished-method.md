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
ms.openlocfilehash: f1cfef464569b577923fbb16624c99358998d29c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866247"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>Metodo ICorProfilerCallback::JITCompilationFinished
Notifica al profiler che il compilatore just-in-time (JIT) ha terminato la compilazione di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parametri

- `functionId`

  \[in] ID della funzione compilata.

- `hrStatus`

  \[in] valore che indica se la compilazione è stata eseguita correttamente.

- `fIsSafeToBlock`

  \[in] valore che indica al profiler se il blocco influirà sul funzionamento del runtime. Il valore è `true` se il blocco può causare la restituzione del thread chiamante da parte del runtime. in caso contrario, `false`.

  Sebbene il valore `true` non danneggi il runtime, può alterare i risultati della profilatura.

## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
