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
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175187"
---
# <a name="functiontailcall2-function"></a>Funzione FunctionTailcall2
Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sullo stack frame.  
  
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

  \[in] L'identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.

- `clientData`

  \[in] L'identificatore di funzione rimappato, specificato in precedenza dal profiler tramite [FunctionIDMapper](functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.
  
- `func`

  \[in] `COR_PRF_FRAME_INFO` Un valore che punta alle informazioni sullo stack frame.

  Il profiler deve considerare questo come un handle opaco che può essere passato al motore di esecuzione nel [metodo ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)

## <a name="remarks"></a>Osservazioni  
 La funzione di destinazione della chiamata tail utilizzerà lo stack frame corrente e tornerà direttamente al chiamante della funzione che ha effettuato la chiamata tail. Ciò significa che un callback [FunctionLeave2](functionleave2-function.md) non verrà generato per una funzione che è la destinazione di una chiamata tail.  
  
 Il valore `func` del parametro non `FunctionTailcall2` è valido dopo la restituzione della funzione perché il valore può cambiare o essere eliminato.  
  
 La `FunctionTailcall2` funzione è un callback; è necessario implementarlo. L'implementazione `__declspec`deve`naked`utilizzare l'attributo della classe di archiviazione ( ).  
  
 Il motore di esecuzione non salva i registri prima di chiamare questa funzione.  
  
- All'ingresso, è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).  
  
- All'uscita, è necessario ripristinare lo stack rimuovendo tutti i parametri inseriti dal chiamante.  
  
 L'implementazione di non deve bloccarsi perché ritarderà la procedura di `FunctionTailcall2` Garbage Collection. L'implementazione non deve tentare un'operazione di Garbage Collection perché lo stack potrebbe non essere in uno stato compatibile con garbage collection. Se viene tentata un'operazione `FunctionTailcall2` di Garbage Collection, il runtime si bloccherà fino a quando non viene restituito.  
  
 Inoltre, `FunctionTailcall2` la funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione FunctionEnter2](functionenter2-function.md)
- [Funzione FunctionLeave2](functionleave2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
