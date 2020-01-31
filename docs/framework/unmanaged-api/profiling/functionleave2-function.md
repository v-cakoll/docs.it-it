---
title: Funzione FunctionLeave2
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: 0b1ecd1266528f8a08ef114de2f111dd0f71ca8b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866931"
---
# <a name="functionleave2-function"></a>Funzione FunctionLeave2
Notifica al profiler che una funzione sta per tornare al chiamante e fornisce informazioni sull'stack frame e sul valore restituito della funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcId`

  \[in] identificatore della funzione che restituisce.

- `clientData`

  \[in] identificatore della funzione di cui è stato eseguito il mapping, specificato in precedenza dal profiler tramite la funzione [FunctionIDMapper](functionidmapper-function.md) .

- `func`

  \[in] valore `COR_PRF_FRAME_INFO` che punta alle informazioni relative al stack frame.

  Il profiler deve considerarlo come un handle opaco che può essere passato di nuovo al motore di esecuzione nel metodo [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .  
  
- `retvalRange`

  \[in] puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) che specifica la posizione di memoria del valore restituito della funzione.

  Per accedere alle informazioni sul valore restituito, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_RETVAL`. Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento.

## <a name="remarks"></a>Note  
 I valori dei parametri `func` e `retvalRange` non sono validi dopo che la funzione `FunctionLeave2` restituisce il risultato perché i valori possono essere modificati o eliminati.  
  
 La funzione `FunctionLeave2` è un callback. è necessario implementarla. L'implementazione deve usare l'attributo della classe di archiviazione `__declspec`(`naked`).  
  
 Il motore di esecuzione non salva i registri prima di chiamare questa funzione.  
  
- In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).  
  
- All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.  
  
 L'implementazione di `FunctionLeave2` non deve bloccarsi perché ritarda Garbage Collection. L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection. Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionLeave2` non restituisce.  
  
 Inoltre, la funzione `FunctionLeave2` non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di managed memory.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione FunctionEnter2](functionenter2-function.md)
- [Funzione FunctionTailcall2](functiontailcall2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
