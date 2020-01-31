---
title: Interfaccia ICorProfilerCallback3
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: ad9c5445cbef0be7919570db64b027556d923752
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865571"
---
# <a name="icorprofilercallback3-interface"></a>Interfaccia ICorProfilerCallback3
Fornisce metodi di callback utilizzati dal Common Language Runtime (CLR) per comunicare le informazioni sullo stato di collegamento e scollegamento al profiler.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo InitializeForAttach](icorprofilercallback3-initializeforattach-method.md)|Chiamato da CLR per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.|  
|[Metodo ProfilerAttachComplete](icorprofilercallback3-profilerattachcomplete-method.md)|Chiamato da CLR per indicare che il profiler può ora chiamare i metodi di recupero.|  
|[Metodo ProfilerDetachSucceeded](icorprofilercallback3-profilerdetachsucceeded-method.md)|Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
