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
ms.openlocfilehash: f628bd1270b529264c14236ca7cdc03bf7afd9d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454205"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>Metodo ICorProfilerCallback4::GetReJITParameters
Consente al profiler di codice impostare i flag di generazione del codice alternativo per un nuovo corpo del metodo ricompilata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] Il modulo che contiene il metodo per la quale CLR deve parametri di ricompilazione JIT.  
  
 `methodId`  
 [in] Il `MethodDef` del metodo per la quale CLR deve parametri di ricompilazione JIT.  
  
 `pFunctionControl`  
 [in] Un puntatore a un [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfaccia che il profiler può utilizzare per fornire informazioni di ricompilazione JIT per il metodo viene ricompilato.  
  
## <a name="remarks"></a>Note  
 I problemi CLR un `GetReJITParameters` callback in modo che il profiler può specificare i parametri per la ricompilazione di un metodo specificato. Il `GetReJITParameters` callback viene eseguito una sola volta per ogni funzione, i parametri forniti dal profiler si applicano a tutte le istanze di tale funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [Metodo JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [Metodo ReJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
