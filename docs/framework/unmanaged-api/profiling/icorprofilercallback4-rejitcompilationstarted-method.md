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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a65de26f3fc088b292ec9f8a96ca4e503a17edd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680900"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Metodo ICorProfilerCallback4::ReJITCompilationStarted
Notifica al profiler che il compilatore JIT just-in-time è stato avviato ricompilare una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che il compilatore JIT è stata avviata da ricompilare.  
  
 `rejitId`  
 [in] L'ID di ricompilazione della nuova versione della funzione.  
  
 `fIsSafeToBlock`  
 [in] `true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avrà effetto il funzionamento del runtime. Un valore di `true` non danneggia il runtime, ma può influenzare i risultati della profilatura.  
  
## <a name="remarks"></a>Note  
 È possibile ricevere più di una coppia di `ReJITCompilationStarted` e [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) metodo viene chiamato per ogni funzione a causa della modalità il runtime gestisce i costruttori di classe. Ad esempio, il runtime Avvia ricompilazione di un metodo, ma deve essere eseguito il costruttore della classe per classe B. Pertanto, il runtime ricompila il costruttore per la classe B e lo esegue. Mentre il costruttore è in esecuzione, che effettua una chiamata al metodo A, che fa sì che il metodo venga ricompilato nuovamente. In questo scenario, la ricompilazione prima del metodo verrà interrotta. Tuttavia, entrambi tenta di ricompilare metodo un oggetto vengono segnalata con eventi di ricompilazione JIT.  
  
 I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread contemporaneamente dei callback. Ad esempio, il thread chiama `ReJITCompilationStarted`; tuttavia, prima che il thread chiami [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), il thread B chiama [ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID (funzione) dal `ReJITCompilationStarted` callback per il thread A. Può sembrare che l'ID di funzione non deve ancora essere valido perché una chiamata a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) non ha ancora ricevuto dal profiler. Tuttavia, in questo caso, l'ID di funzione è valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [Metodo JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [Metodo ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
