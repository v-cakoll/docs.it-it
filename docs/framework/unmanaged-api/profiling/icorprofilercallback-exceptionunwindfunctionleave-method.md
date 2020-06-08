---
title: Metodo ICorProfilerCallback::ExceptionUnwindFunctionLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
ms.openlocfilehash: 8694a2d19c3b98487b86da4273eb0c68fb9d9ace
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500117"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a>Metodo ICorProfilerCallback::ExceptionUnwindFunctionLeave
Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha terminato la rimozione di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a>Osservazioni  
 Quando `ExceptionUnwindFunctionLeave` viene chiamato il metodo, l'istanza della funzione e i relativi dati dello stack vengono rimossi dallo stack.  
  
 Il profiler non deve bloccarsi durante questa chiamata perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive. Se il profiler si blocca ed è stato eseguito un tentativo di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.  
  
 Inoltre, durante questa chiamata, il profiler non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)
