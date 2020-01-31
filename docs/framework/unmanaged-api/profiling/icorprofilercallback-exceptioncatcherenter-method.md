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
ms.openlocfilehash: 534e0672820cc2509f32765274ad970fda69ec5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866507"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>Metodo ICorProfilerCallback::ExceptionCatcherEnter
Notifica al profiler che il controllo viene passato al blocco `catch` appropriato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>Parametri

- `functionId`

  \[in] identificatore della funzione che contiene il blocco di `catch`.
  
- `objectId`

  \[in] identificatore dell'eccezione gestita.

## <a name="remarks"></a>Note  
 Il metodo `ExceptionCatcherEnter` viene chiamato solo se il punto di recupero è nel codice compilato con il compilatore JIT (just-in-Time). Un'eccezione rilevata nel codice non gestito o nel codice interno del runtime non chiamerà questa notifica. Il valore `objectId` viene nuovamente passato perché un Garbage Collection potrebbe avere spostato l'oggetto dopo la notifica di `ExceptionThrown`.  
  
 Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive. Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.  
  
 L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)
