---
title: Metodo ICorProfilerCallback4::ReJITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177085"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Metodo ICorProfilerCallback4::ReJITCompilationStarted
Notifica al profiler che il compilatore JIT (Just-In-Time) ha iniziato a ricompilare una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] ID della funzione che il compilatore JIT ha iniziato a ricompilare.  
  
 `rejitId`  
 [in] ID di ricompilazione della nuova versione della funzione.  
  
 `fIsSafeToBlock`  
 [in] `true` per indicare che il blocco può causare il runtime di attendere che il thread chiamante venga restituito da questo callback; `false` per indicare che il blocco non influirà sul funzionamento del runtime. Un valore `true` di non danneggia il runtime, ma può influire sui risultati della profilatura.  
  
## <a name="remarks"></a>Osservazioni  
 È possibile ricevere più di `ReJITCompilationStarted` una coppia di chiamate al metodo [EJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) per ogni funzione a causa del modo in cui il runtime gestisce i costruttori di classe. Ad esempio, il runtime inizia a ricompilare il metodo A, ma è necessario eseguire il costruttore della classe per la classe B. Pertanto, il runtime ricompila il costruttore per la classe B e lo esegue. Mentre il costruttore è in esecuzione, effettua una chiamata al metodo A, che fa sì che il metodo A venga ricompilato nuovamente. In questo scenario, la prima ricompilazione del metodo A viene interrotta. Tuttavia, entrambi i tentativi di ricompilare il metodo A vengono segnalati con gli eventi di ricompilazione JIT.  
  
 I profiler devono supportare la sequenza dei callback di ricompilazione JIT nei casi in cui due thread eseguono contemporaneamente callback. Ad esempio, il `ReJITCompilationStarted`thread A chiama ; tuttavia, prima che il thread A [chiami ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), il thread B `ReJITCompilationStarted` chiama [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID funzione dal callback per il thread A. Potrebbe sembrare che l'ID funzione non deve essere ancora valido perché una chiamata a [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) non era ancora stata ricevuta dal profiler. Tuttavia, in questo caso, l'ID funzione è valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Metodo JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
- [Metodo ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
