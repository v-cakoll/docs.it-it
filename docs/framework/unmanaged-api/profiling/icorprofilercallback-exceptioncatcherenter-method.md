---
title: Metodo ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 9d0ef4da4ba6c8db49bcb0b40911756f7d9db66d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500318"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>Metodo ICorProfilerCallback::ExceptionCatcherEnter
Notifica al profiler che il controllo viene passato al `catch` blocco appropriato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>Parametri

- `functionId`

  \[in] identificatore della funzione che contiene il `catch` blocco.
  
- `objectId`

  \[in] identificatore dell'eccezione gestita.

## <a name="remarks"></a>Osservazioni  
 Il `ExceptionCatcherEnter` metodo viene chiamato solo se il punto di recupero è nel codice compilato con il compilatore just-in-time (JIT). Un'eccezione rilevata nel codice non gestito o nel codice interno del runtime non chiamerà questa notifica. Il `objectId` valore viene passato di nuovo perché un Garbage Collection potrebbe aver spostato l'oggetto dopo `ExceptionThrown` la notifica.  
  
 Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive. Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.  
  
 L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)
