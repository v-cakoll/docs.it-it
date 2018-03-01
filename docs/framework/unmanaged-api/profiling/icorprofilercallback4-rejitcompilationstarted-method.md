---
title: Metodo ICorProfilerCallback4::ReJITCompilationStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Metodo ICorProfilerCallback4::ReJITCompilationStarted
Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato ricompilare una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che il compilatore JIT è stata avviata da ricompilare.  
  
 `rejitId`  
 [in] L'ID della ricompilazione della nuova versione della funzione.  
  
 `fIsSafeToBlock`  
 [in] `true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante da questo callback; `false` per indicare che il blocco non avranno effetto l'operazione di runtime. Il valore `true` non influisce sul runtime, ma possono influenzare i risultati di profilatura.  
  
## <a name="remarks"></a>Note  
 È possibile ricevere più di una coppia di `ReJITCompilationStarted` e [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) metodo chiama per ogni funzione a causa del modo il runtime gestisce i costruttori di classe. Ad esempio, il runtime Avvia ricompilazione di un metodo, ma il costruttore della classe per classe B deve essere eseguito. Pertanto, il runtime ricompila il costruttore di classe B e lo esegue. Durante l'esecuzione, il costruttore che effettua una chiamata al metodo che determina il metodo per la ricompilazione nuovamente. In questo scenario, viene interrotta la ricompilazione prima del metodo. Tuttavia, entrambi tenta ricompilare metodo vengono segnalata con gli eventi di ricompilazione JIT.  
  
 I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread effettuano callback simultaneamente. Ad esempio, il thread chiama `ReJITCompilationStarted`; tuttavia, prima di un thread chiama [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID (funzione) dal `ReJITCompilationStarted` callback per thread A. Potrebbe sembrare che l'ID della funzione non deve ancora essere valido perché una chiamata a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) non ha ancora ricevuto dal profiler. Tuttavia, in questo caso, l'ID della funzione è valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [Metodo JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [Metodo ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
