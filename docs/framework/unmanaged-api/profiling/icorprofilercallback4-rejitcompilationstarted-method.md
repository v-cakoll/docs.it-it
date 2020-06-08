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
ms.openlocfilehash: 6e340fa08800f31d36e6cfb280cac847a4fca548
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499350"
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
 [in] `true` per indicare che il blocco può far sì che il runtime attenda il ritorno del thread chiamante da questo callback; `false`per indicare che il blocco non influisce sul funzionamento del runtime. Il valore non `true` nuoce al runtime, ma può influire sui risultati della profilatura.  
  
## <a name="remarks"></a>Osservazioni  
 È possibile ricevere più di una coppia di chiamate al `ReJITCompilationStarted` metodo [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) per ogni funzione a causa del modo in cui il runtime gestisce i costruttori della classe. Ad esempio, il runtime inizia a ricompilare il metodo A, ma è necessario eseguire il costruttore della classe B. Pertanto, il runtime ricompila il costruttore per la classe B e lo esegue. Mentre il costruttore è in esecuzione, effettua una chiamata al metodo a, che fa in modo che il metodo a venga ricompilato. In questo scenario, la prima ricompilazione del metodo A è stata interrotta. Tuttavia, entrambi i tentativi di ricompilare il metodo A vengono segnalati con gli eventi di ricompilazione JIT.  
  
 I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread eseguono contemporaneamente i callback. Ad esempio, il thread A chiama `ReJITCompilationStarted` ; tuttavia, prima che il thread a chiami [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), il thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID funzione dal `ReJITCompilationStarted` callback per il thread a. Potrebbe sembrare che l'ID funzione non sia ancora valido perché una chiamata a [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) non è stata ancora ricevuta dal profiler. Tuttavia, in questo caso, l'ID funzione è valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Metodo JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
- [Metodo ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
