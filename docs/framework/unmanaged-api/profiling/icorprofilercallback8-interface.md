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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8-interface"></a>Interfaccia ICorProfilerCallback8
[Supportato in .NET Framework 4.7 e versioni successive]  

 Una sottoclasse [ICorProfilerCallback7](icorprofilercallback7-interface.md) che fornisce i metodi di callback usati da common language runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è stato avviato e completato. 
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Notifica al profiler che la compilazione JIT di un metodo dinamico è stato avviato.|  
|[Metodo DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Notifica al profiler che la compilazione JIT di un metodo dinamico è stato completato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
**Versioni di .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche  
[Interfacce di profilatura](profiling-interfaces.md)   
[Interfaccia ICorProfilerCallback9](icorprofilercallback9-interface.md)
