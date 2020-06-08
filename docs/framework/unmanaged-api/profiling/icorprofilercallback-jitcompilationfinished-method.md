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
ms.openlocfilehash: 0da67f0d4be779cc21481d03a21209620289888e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500059"
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

  \[in] valore che indica al profiler se il blocco influirà sul funzionamento del runtime. Il valore è `true` se il blocco può far sì che il runtime attenda che il thread chiamante restituisca da questo callback; in caso contrario, `false` .

  Sebbene il valore di `true` non danneggi il runtime, può alterare i risultati della profilatura.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
