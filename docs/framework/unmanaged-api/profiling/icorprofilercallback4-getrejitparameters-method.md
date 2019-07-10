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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03b7ca218318df517832d198e72d4f79d30827b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779234"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>Metodo ICorProfilerCallback4::GetReJITParameters
Consente al profiler di codice impostare i flag di generazione di codice alternativo per il corpo di un nuovo metodo ricompilata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] Il modulo che contiene il metodo per cui CLR richiede parametri di ricompilazione JIT.  
  
 `methodId`  
 [in] Il `MethodDef` del metodo cui CLR richiedono parametri di ricompilazione JIT.  
  
 `pFunctionControl`  
 [in] Un puntatore a un [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfaccia che il profiler può usare per fornire informazioni di ricompilazione JIT per il metodo vengano ricompilata.  
  
## <a name="remarks"></a>Note  
 I problemi CLR un `GetReJITParameters` callback in modo che il profiler può specificare i parametri per la ricompilazione di un determinato metodo. Il `GetReJITParameters` callback viene eseguito una sola volta per ogni funzione; i parametri forniti dal profiler si applicano a tutte le istanze di tale funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [Metodo JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [Metodo ReJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
