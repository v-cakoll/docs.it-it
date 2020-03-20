---
title: Funzione FunctionEnter2
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177059"
---
# <a name="functionenter2-function"></a>Funzione FunctionEnter2
Notifica al profiler che il controllo viene passato a una funzione e fornisce informazioni sugli argomenti dello stack frame e della funzione. Questa funzione sostituisce la funzione [FunctionEnter.](functionenter-function.md)  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcId`

  \[in] Identificatore della funzione a cui viene passato il controllo.

- `clientData`

  \[in] L'identificatore di funzione rimappato, che il profiler ha specificato in precedenza utilizzando la funzione [FunctionIDMapper.](functionidmapper-function.md)
  
- `func`

  \[in] `COR_PRF_FRAME_INFO` Un valore che punta alle informazioni sullo stack frame.
  
  Il profiler deve considerare questo come un handle opaco che può essere passato al motore di esecuzione nel [metodo ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- `argumentInfo`

  \[in] Un puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) che specifica le posizioni in memoria degli argomenti della funzione.

  Per accedere alle informazioni `COR_PRF_ENABLE_FUNCTION_ARGS` sugli argomenti, è necessario impostare il flag. Il profiler può utilizzare il metodo [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento.

## <a name="remarks"></a>Osservazioni  
 I valori `func` dei `argumentInfo` parametri e non `FunctionEnter2` sono validi dopo la restituzione della funzione perché i valori possono cambiare o essere eliminati.  
  
 La `FunctionEnter2` funzione è un callback; è necessario implementarlo. L'implementazione `__declspec`deve`naked`utilizzare l'attributo della classe di archiviazione ( ).  
  
 Il motore di esecuzione non salva i registri prima di chiamare questa funzione.  
  
- All'ingresso, è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).  
  
- All'uscita, è necessario ripristinare lo stack rimuovendo tutti i parametri inseriti dal chiamante.  
  
 L'implementazione di non deve bloccarsi perché ritarderà la procedura di `FunctionEnter2` Garbage Collection. L'implementazione non deve tentare un'operazione di Garbage Collection perché lo stack potrebbe non essere in uno stato compatibile con garbage collection. Se viene tentata un'operazione `FunctionEnter2` di Garbage Collection, il runtime si bloccherà fino a quando non viene restituito.  
  
 Inoltre, `FunctionEnter2` la funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione FunctionLeave2](functionleave2-function.md)
- [Funzione FunctionTailcall2](functiontailcall2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
