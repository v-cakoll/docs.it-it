---
title: Interfaccia ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4516c8f9673052b521c1f0f594978236fef1e0ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136446"
---
# <a name="icorprofilercallback8-interface"></a>Interfaccia ICorProfilerCallback8
[Supportato in .NET Framework 4,7 e versioni successive]  

 Sottoclasse di [ICorProfilerCallback7](icorprofilercallback7-interface.md) che fornisce metodi di callback utilizzati dalla Common Language Runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è stata avviata e completata. 
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Notifica al profiler che è stata avviata la compilazione JIT di un metodo dinamico.|  
|[Metodo DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Notifica al profiler che la compilazione JIT di un metodo dinamico è stata completata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerCallback9](icorprofilercallback9-interface.md)
