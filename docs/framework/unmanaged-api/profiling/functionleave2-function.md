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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 124921f2f99ca4d8da88cc3713624383e225a26f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781263"
---
# <a name="functionleave2-function"></a>Funzione FunctionLeave2
Notifica al profiler che una funzione sta per restituire al chiamante e vengono fornite informazioni relative al valore restituito dello stack frame e la funzione.  
  
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
 `funcId`  
 [in] L'identificatore della funzione che restituisce.  
  
 `clientData`  
 [in] Identificatore della funzione modificato, quali il profiler specificato in precedenza tramite il [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) (funzione).  
  
 `func`  
 [in] Oggetto `COR_PRF_FRAME_INFO` valore che punta alle informazioni sullo stack frame.  
  
 Il profiler deve trattarlo come un handle opaco che può essere passato al motore di esecuzione la [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) (metodo).  
  
 `retvalRange`  
 [in] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) struttura che specifica la posizione di memoria del valore restituito della funzione.  
  
 Per poter accedere a informazioni sul valore restituito, il `COR_PRF_ENABLE_FUNCTION_RETVAL` flag deve essere impostato. Il profiler può usare la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodo per impostare i flag dell'evento.  
  
## <a name="remarks"></a>Note  
 I valori del `func` e `retvalRange` parametri non sono validi dopo il `FunctionLeave2` funzione perché i valori potrebbero cambiare o essere distrutti.  
  
 Il `FunctionLeave2` funzione è un callback, è necessario implementarla. L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.  
  
 Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.  
  
- In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).  
  
- In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.  
  
 L'implementazione di `FunctionLeave2` non devono bloccare perché ritarderà l'operazione di garbage collection. L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di garbage collection adatto. Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionLeave2` restituisce.  
  
 Inoltre, il `FunctionLeave2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [Funzione FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
