---
title: Interfaccia ICorProfilerCallback4
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: 295d3d440529623f4569fd6c5f4debe7e4558990
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499441"
---
# <a name="icorprofilercallback4-interface"></a>Interfaccia ICorProfilerCallback4
Fornisce metodi di callback utilizzati dal Common Language Runtime (CLR) per comunicare le informazioni al profiler.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)|Consente all'Code Profiler di impostare flag di generazione del codice alternativi per un nuovo corpo del metodo ricompilato.|  
|[Metodo MovedReferences2](icorprofilercallback4-movedreferences2-method.md)|Segnala il nuovo layout degli oggetti nell'heap in seguito a un Garbage Collection di compattazione.|  
|[Metodo ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)|Notifica al profiler che il compilatore just-in-time (JIT) ha completato la ricompilazione di una funzione.|  
|[Metodo ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)|Notifica al profiler che il compilatore JIT (just-in-Time) ha iniziato a ricompilare una funzione.|  
|[Metodo ReJITError](icorprofilercallback4-rejiterror-method.md)|Segnala un errore rilevato durante l'elaborazione di una richiesta di ricompilazione.|  
|[Metodo SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md)|Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.|  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
