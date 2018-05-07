---
title: Interfaccia ICorProfilerCallback2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a218b58ed2ab40505204768f7d6071dea6db5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback2-interface"></a>Interfaccia ICorProfilerCallback2
Fornisce i metodi utilizzati da common language runtime (CLR) per notificare a un code profiler quando si verificano gli eventi a cui ha effettuato la sottoscrizione. Il `ICorProfilerCallback2` interfaccia è un'estensione del [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia. In altri termini, fornisce nuovi callback introdotto in .NET Framework versione 2.0.  
  
> [!NOTE]
>  Ogni implementazione del metodo deve restituire un HRESULT con un valore S_OK esito positivo o E_FAIL in caso di errore. Attualmente, CLR ignora il valore HRESULT restituito da ogni callback a eccezione di [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|Notifica al profiler di codice che un oggetto con un finalizzatore è stato accodato per il thread del finalizzatore per l'esecuzione del relativo `Finalize` metodo.|  
|[Metodo GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|Notifica al profiler che è stata completata un'operazione di garbage collection e rilasciati per tale tutti i callback di garbage collection.|  
|[Metodo GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|Notifica al profiler di codice che ha avviato un'operazione di garbage collection.|  
|[Metodo HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|Notifica al profiler di codice che è stato creato l'handle di garbage collection.|  
|[Metodo HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|Notifica al profiler di codice che è stato eliminato un handle di garbage collection.|  
|[Metodo RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|Notifica al profiler sui riferimenti principali dopo un'operazione di garbage collection. Questo metodo è un'estensione del [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) metodo.|  
|[Metodo SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|Notifica al profiler sui riferimenti a oggetti rimasti dopo un'operazione di garbage collection.|  
|[Metodo ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|Notifica al profiler di codice che il nome di un thread è stato modificato.|  
  
## <a name="remarks"></a>Note  
 CLR chiama un metodo di `ICorProfilerCallback` (o `ICorProfilerCallback2`) interfaccia per notificare al profiler di eventi, a cui il profiler ha eseguito la sottoscrizione, si verifica. Si tratta dell'interfaccia di callback da CLR per comunicare con il profiler di codice.  
  
 Un code profiler deve implementare i metodi del `ICorProfilerCallback` interfaccia. Per .NET Framework 2.0 e versioni successive, il profiler deve implementare anche il `ICorProfilerCallback2` metodi. Ogni implementazione del metodo deve restituire un HRESULT con un valore S_OK esito positivo o E_FAIL in caso di errore. Attualmente, CLR ignora il valore HRESULT restituito da ogni callback a eccezione di [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Un code profiler deve registrare nel Registro di sistema Microsoft Windows, il relativo oggetto COM che implementa il `ICorProfilerCallback` e `ICorProfilerCallback2` interfacce. Un code profiler sottoscrive gli eventi per il quale desidera ricevere notifica chiamando [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Questa operazione viene in genere eseguita nell'implementazione del profiler di [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Quindi, il profiler è in grado di ricevere una notifica dal runtime quando un evento sta per verificarsi o si è appena verificato in un processo di runtime in esecuzione.  
  
> [!NOTE]
>  Il profiler si registra un singolo oggetto COM. Se il profiler è destinato a .NET Framework versione 1.0 o 1.1, l'oggetto COM deve implementare solo i metodi di `ICorProfilerCallback`. Se è destinato a .NET Framework versione 2.0 e versioni successive, l'oggetto COM deve anche implementare i metodi di `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
