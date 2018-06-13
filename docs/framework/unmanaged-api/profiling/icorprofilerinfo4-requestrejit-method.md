---
title: Metodo ICorProfilerInfo4::RequestReJIT
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be7184e07815ebe222b8ff8736c26fd3879c8777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460708"
---
# <a name="icorprofilerinfo4requestrejit-method"></a>Metodo ICorProfilerInfo4::RequestReJIT
Richiede la ricompilazione JIT di tutte le istanze delle funzioni specificate.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cFunctions`  
 [in] Numero di funzioni da ricompilare.  
  
 `moduleIds`  
 [in] Specifica la parte `moduleId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ricompilare.  
  
 `methodIds`  
 [in] Specifica la parte `methodId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ricompilare.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Si è tentato di contrassegnare tutti i metodi per la ricompilazione JIT. Il profiler deve implementare il [icorprofilercallback4:: Rejiterror](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) metodo per determinare quali metodi sono stati correttamente contrassegnati per la ricompilazione JIT.|  
|CORPROF_E_CALLBACK4_REQUIRED|Il profiler deve implementare il [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaccia per la chiamata a essere supportato.|  
|CORPROF_E_REJIT_NOT_ENABLED|La ricompilazione JIT non è stata abilitata. È necessario abilitare la ricompilazione JIT durante l'inizializzazione mediante la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare il `COR_PRF_ENABLE_REJIT` flag.|  
|E_INVALIDARG|Il parametro `cFunctions` è pari a 0 oppure `moduleIds` o `methodIds` è `NULL`.|  
|||  
|E_OUTOFMEMORY|CLR non è stato in grado di completare la richiesta a causa di memoria insufficiente.|  
  
## <a name="remarks"></a>Note  
 Chiamare `RequestReJIT` per ottenere la ricompilazione tramite il runtime di un set di funzioni specificato. Un code profiler può quindi utilizzare il [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfaccia per modificare il codice che viene generato quando vengono ricompilate le funzioni. Questa operazione non influisce sulle funzioni attualmente in esecuzione, ma solo sulle chiamate di funzione future. Se una delle funzioni specificate è stata precedentemente ricompilata tramite JIT, la richiesta di ricompilazione equivale al ripristino e alla ricompilazione della funzione. Per mantenere la reversibilità, quando il compilatore JIT compila la versione originale di una funzione, considera solo le versioni originali dei relativi chiamati per le decisioni di incorporamento (inlining). Quando il compilatore JIT ricompila una funzione, considera le versioni correnti (ricompilate o originali) dei relativi chiamati per l'incorporamento.  
  
 In genere, un profiler chiama `RequestReJIT` in risposta all'input dell'utente che richiede al profiler di instrumentare uno o più metodi. `RequestReJIT` in genere sospende il runtime per eseguire le proprie attività e potrebbe attivare una Garbage Collection. Di conseguenza, il profiler dovrebbe chiamare `RequestReJIT` da un thread creato in precedenza e non da un thread creato da CLR che sta eseguendo un callback del profiler.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
