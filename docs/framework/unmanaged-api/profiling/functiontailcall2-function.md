---
title: Funzione FunctionTailcall2
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 2d99c6d8bd2af02456c6a90143b524c337483868
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866895"
---
# <a name="functiontailcall2-function"></a>Funzione FunctionTailcall2
Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sul stack frame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcId`

  \[in] identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.

- `clientData`

  \[in] identificatore della funzione di cui è stato eseguito il mapping, che il profiler ha specificato in precedenza tramite [FunctionIDMapper](functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.
  
- `func`

  \[in] valore `COR_PRF_FRAME_INFO` che punta alle informazioni relative al stack frame.

  Il profiler deve considerarlo come un handle opaco che può essere passato di nuovo al motore di esecuzione nel metodo [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .

## <a name="remarks"></a>Note  
 La funzione di destinazione della chiamata tail utilizzerà l'stack frame corrente e tornerà direttamente al chiamante della funzione che ha eseguito la chiamata tail. Ciò significa che non verrà emesso un callback [FunctionLeave2](functionleave2-function.md) per una funzione che è la destinazione di una chiamata tail.  
  
 Il valore del parametro `func` non è valido dopo la restituzione della funzione `FunctionTailcall2` perché il valore può cambiare o essere eliminato definitivamente.  
  
 La funzione `FunctionTailcall2` è un callback. è necessario implementarla. L'implementazione deve usare l'attributo della classe di archiviazione `__declspec`(`naked`).  
  
 Il motore di esecuzione non salva i registri prima di chiamare questa funzione.  
  
- In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).  
  
- All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.  
  
 L'implementazione di `FunctionTailcall2` non deve bloccarsi perché ritarda Garbage Collection. L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection. Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionTailcall2` non restituisce.  
  
 Inoltre, la funzione `FunctionTailcall2` non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di managed memory.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione FunctionEnter2](functionenter2-function.md)
- [Funzione FunctionLeave2](functionleave2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
