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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8491f80c1b4340756c00b5540520bd76f0f583a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486997"
---
# <a name="functiontailcall2-function"></a>Funzione FunctionTailcall2
Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail ad un'altra funzione e fornisce informazioni sullo stack frame.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `funcId`  
 [in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.  
  
 `clientData`  
 [in] Identificatore della funzione modificato, quali il profiler specificato in precedenza tramite [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.  
  
 `func`  
 [in] Oggetto `COR_PRF_FRAME_INFO` valore che punta alle informazioni sullo stack frame.  
  
 Il profiler deve trattarlo come un handle opaco che può essere passato al motore di esecuzione la [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) (metodo).  
  
## <a name="remarks"></a>Note  
 La funzione di destinazione della chiamata tail verrà utilizzato lo stack frame corrente e restituirà direttamente al chiamante della funzione che ha effettuato la parte finale di chiamata. Ciò significa che un [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback non verrà generato per una funzione che rappresenta la destinazione di una chiamata tail.  
  
 Il valore dei `func` parametro non valido dopo il `FunctionTailcall2` funzione perché il valore potrebbe cambiare o essere distrutto.  
  
 Il `FunctionTailcall2` funzione è un callback, è necessario implementarla. L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.  
  
 Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.  
  
-   In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).  
  
-   In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.  
  
 L'implementazione di `FunctionTailcall2` non devono bloccare perché ritarderà l'operazione di garbage collection. L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di garbage collection adatto. Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionTailcall2` restituisce.  
  
 Inoltre, il `FunctionTailcall2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzione FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [Funzione FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
