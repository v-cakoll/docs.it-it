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
ms.openlocfilehash: 81d11c87c9bc970dd5b5c9010023610cea7c0e72
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865194"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Metodo ICorProfilerCallback4::ReJITCompilationStarted
Notifica al profiler che il compilatore JIT (just-in-Time) ha iniziato a ricompilare una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 in ID della funzione che il compilatore JIT ha iniziato a ricompilare.  
  
 `rejitId`  
 in ID di ricompilazione della nuova versione della funzione.  
  
 `fIsSafeToBlock`  
 [in] `true` per indicare che il blocco può causare la restituzione del thread chiamante da parte del runtime. `false` per indicare che il blocco non influirà sul funzionamento del runtime. Il valore `true` non nuoce al runtime, ma può influire sui risultati della profilatura.  
  
## <a name="remarks"></a>Note  
 È possibile ricevere più di una coppia di `ReJITCompilationStarted` e chiamate al metodo [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) per ogni funzione a causa del modo in cui il runtime gestisce i costruttori della classe. Ad esempio, il runtime inizia a ricompilare il metodo A, ma è necessario eseguire il costruttore della classe B. Pertanto, il runtime ricompila il costruttore per la classe B e lo esegue. Mentre il costruttore è in esecuzione, effettua una chiamata al metodo a, che fa in modo che il metodo a venga ricompilato. In questo scenario, la prima ricompilazione del metodo A è stata interrotta. Tuttavia, entrambi i tentativi di ricompilare il metodo A vengono segnalati con gli eventi di ricompilazione JIT.  
  
 I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread eseguono contemporaneamente i callback. Ad esempio, il thread A chiama `ReJITCompilationStarted`; Tuttavia, prima che il thread A chiami [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), il thread B chiama [ICorProfilerCallback:: EXCEPTIONSEARCHFUNCTIONENTER](icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID funzione dal callback `ReJITCompilationStarted` per il thread a. Potrebbe sembrare che l'ID funzione non sia ancora valido perché una chiamata a [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) non è stata ancora ricevuta dal profiler. Tuttavia, in questo caso, l'ID funzione è valido.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Metodo JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
- [Metodo ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
