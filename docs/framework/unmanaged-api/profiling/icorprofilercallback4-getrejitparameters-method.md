---
title: Metodo ICorProfilerCallback4::GetReJITParameters
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: 858d65783515a89a434cf719ef9d5a999643094c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865311"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>Metodo ICorProfilerCallback4::GetReJITParameters
Consente all'Code Profiler di impostare flag di generazione del codice alternativi per un nuovo corpo del metodo ricompilato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in Il modulo che contiene il metodo per il quale CLR necessita di parametri di ricompilazione JIT.  
  
 `methodId`  
 in `MethodDef` del metodo per il quale CLR necessita di parametri di ricompilazione JIT.  
  
 `pFunctionControl`  
 in Puntatore a un'interfaccia [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) che il profiler può usare per fornire informazioni sulla ricompilazione JIT per il metodo in fase di ricompilazione.  
  
## <a name="remarks"></a>Note  
 CLR emette un callback `GetReJITParameters` in modo che il profiler possa specificare i parametri per la ricompilazione di un determinato metodo. Il callback `GetReJITParameters` viene emesso una sola volta per ogni funzione. i parametri forniti dal profiler si applicano a tutte le istanze di tale funzione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Metodo JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
- [Metodo ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)
