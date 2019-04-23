---
title: Interfaccia ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1711def5e2aa41fd63912361ef8250ad160fb88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227756"
---
# <a name="icorprofilercallback9-interface"></a>Interfaccia ICorProfilerCallback9
[Supportato in .NET Framework 4.7.2 e versioni successive]  

 Una sottoclasse [ICorProfilerCallback8](icorprofilercallback8-interface.md) che fornisce un metodo di callback usato da common language runtime per notificare al profiler che un metodo dinamico è stato sottoposto a garbage raccolti e successivamente scaricata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DynamicMethodUnloaded](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Notifica al profiler che un metodo dinamico è stato sottoposto a garbage raccolti e successivamente scaricata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerCallback8](icorprofilercallback9-interface.md)
- [Metodo ICorProfilerCallback8.DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Metodo ICorProfilerCallback8.DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
