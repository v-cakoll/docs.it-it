---
title: Interfaccia ICorProfilerCallback
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback
helpviewer_keywords:
- ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61660a668e152accee7557c8663e8eec77a953ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711681"
---
# <a name="icorprofilercallback-interface"></a>Interfaccia ICorProfilerCallback
Fornisce metodi che vengono usati da common language runtime (CLR) per notificare un code profiler quando si verificano gli eventi a cui il profiler ha effettuato la sottoscrizione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al profiler che un dominio dell'applicazione sia stato creato.|  
|[Metodo AppDomainCreationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al profiler che un dominio dell'applicazione viene creato.|  
|[Metodo AppDomainShutdownFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al profiler che un dominio dell'applicazione è stato scaricato da un processo.|  
|[Metodo AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al profiler che un dominio dell'applicazione è in corso lo scaricamento da un processo.|  
|[Metodo AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Notifica al profiler che un assembly ha terminato il caricamento.|  
|[Metodo AssemblyLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Notifica al profiler che un assembly viene caricato.|  
|[Metodo AssemblyUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al profiler che un assembly è stato scaricato.|  
|[Metodo AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al profiler che un assembly è stato scaricato.|  
|[Metodo ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Notifica al profiler che una classe ha terminato il caricamento.|  
|[Metodo ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Notifica al profiler che venga caricata una classe.|  
|[Metodo ClassUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Notifica al profiler che ha terminato lo scaricamento di una classe.|  
|[Metodo ClassUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Notifica al profiler che è in corso lo scaricamento di una classe.|  
|[Metodo COMClassicVTableCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al profiler che è stato creato un runtime callable wrapper (RCW) per l'IID e la classe specificata.|  
|[Metodo COMClassicVTableDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al profiler che è in corso l'eliminazione di un RCW.|  
|[Metodo ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al profiler che controllo viene passato a appropriato `catch` blocco.|  
|[Metodo ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al profiler che controllo viene passato all'esterno di appropriato `catch` blocco.|  
|[Metodo ExceptionCLRCatcherExecute](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Obsoleti in .NET Framework versione 2.0.|  
|[Metodo ExceptionCLRCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Obsoleti in .NET Framework 2.0.|  
|[Metodo ExceptionOSHandlerEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Non implementato. Un profiler che richiede informazioni sull'eccezione non gestita è necessario ottenere queste informazioni tramite altri mezzi.|  
|[Metodo ExceptionOSHandlerLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Non implementato. Un profiler che richiede informazioni sull'eccezione non gestita è necessario ottenere queste informazioni tramite altri mezzi.|  
|[Metodo ExceptionSearchCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha individuato un gestore per l'eccezione generata.|  
|[Metodo ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al profiler che un filtro utente è in esecuzione.|  
|[Metodo ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al profiler che un filtro utente appena terminata l'esecuzione.|  
|[Metodo ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha immesso una funzione.|  
|[Metodo ExceptionSearchFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha terminato la ricerca di una funzione.|  
|[Metodo ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Notifica al profiler che è stata generata un'eccezione.|  
|[Metodo ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al profiler che la fase di rimozione dell'eccezione gestione sta entrando in un `finally` clausola contenuta nella funzione specificata.|  
|[Metodo ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al profiler che la fase di rimozione dell'eccezione che ha lasciato la gestione una `finally` clausola.|  
|[Metodo ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha immesso una funzione.|  
|[Metodo ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha completato la rimozione di una funzione.|  
|[Metodo FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Notifica al profiler che il runtime ha iniziato a scaricare una funzione.|  
|[Metodo Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Chiamato per inizializzare il profiler, ogni volta che viene avviata una nuova applicazione CLR.|  
|[Metodo JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al profiler di completamento di una ricerca per una funzione che è stata compilata in precedenza utilizzando NGen.exe.|  
|[Metodo JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al profiler che ha avviato una ricerca per una funzione che è stata compilata in precedenza utilizzando NGen.exe.|  
|[Metodo JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Notifica al profiler che il compilatore JIT ha terminato la compilazione di una funzione.|  
|[Metodo JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Notifica al profiler che il compilatore JIT just-in-time è iniziata la compilazione di una funzione.|  
|[Metodo JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Notifica al profiler che una funzione che è stato compilato tramite JIT è stato rimosso dalla memoria.|  
|[Metodo JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Notifica al profiler che il compilatore JIT sta per inserire una funzione in linea con un'altra funzione.|  
|[Metodo ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al profiler che si è verificata una transizione da codice gestito a codice non gestito.|  
|[Metodo ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al profiler che un modulo viene allegato a tale assembly.|  
|[Metodo ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Notifica al profiler che un modulo ha terminato il caricamento.|  
|[Metodo ModuleLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Notifica al profiler che viene viene caricato un modulo.|  
|[Metodo ModuleUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Notifica al profiler che un modulo è terminato lo scaricamento.|  
|[Metodo ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Notifica al profiler che un modulo verrà scaricato.|  
|[Metodo MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Notifica al profiler sui riferimenti a oggetti che sono state spostate durante l'operazione di garbage collection.|  
|[Metodo ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Notifica al profiler che è stata allocata memoria all'interno dell'heap per un oggetto.|  
|[Metodo ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Notifica al profiler sugli oggetti in memoria fa riferimento l'oggetto specificato.|  
|[Metodo ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al profiler sul numero di istanze di ogni classe specificata che sono stati creati dopo il precedente di garbage collection.|  
|[Metodo RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al profiler che una chiamata remota completamento dell'esecuzione nel client.|  
|[Metodo RemotingClientInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al profiler che ha avviato una chiamata remota.|  
|[Metodo RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al profiler che la parte del server di una chiamata remota è stata completata e il client sta ricevendo ora e sta per elaborare la risposta.|  
|[Metodo RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al profiler che il client stia inviando una richiesta al server.|  
|[Metodo RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al profiler che il processo ha terminato la chiamata di un metodo in risposta a una richiesta di chiamata al metodo remoto.|  
|[Metodo RemotingServerInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al profiler che il processo richiama un metodo in risposta a una richiesta di chiamata al metodo remoto.|  
|[Metodo RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al profiler che il processo riceve una richiesta di attivazione o chiamata al metodo remoto.|  
|[Metodo RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata al metodo remote e sta per trasmettere la risposta tramite un canale.|  
|[Metodo RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Notifica al profiler con le informazioni sui riferimenti principali dopo l'operazione di garbage collection.|  
|[Metodo RuntimeResumeFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Notifica al profiler che il runtime è stata ripresa di tutti i thread di runtime e ha restituito al normale funzionamento.|  
|[Metodo RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Notifica al profiler che il runtime viene ripresa di tutti i thread fase di esecuzione.|  
|[Metodo RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al profiler che il runtime è stata interrotta la sospensione di runtime che è stato in corso.|  
|[Metodo RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al profiler che il runtime è stata completata la sospensione di tutti i thread fase di esecuzione.|  
|[Metodo RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al profiler che il runtime sta per sospendere tutti i thread fase di esecuzione.|  
|[Metodo RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Notifica al profiler che il thread specificato ha ripreso dopo una sospensione.|  
|[Metodo RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al profiler che il thread specificato è stata o sta per essere sospeso.|  
|[Metodo Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Notifica al profiler che l'applicazione è in corso l'arresto.|  
|[Metodo ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al profiler che un thread gestito viene implementato utilizzando un thread specifico sistema operativo (OS).|  
|[Metodo ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Notifica al profiler che un thread è stato creato.|  
|[Metodo ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Notifica al profiler che un thread è stato eliminato.|  
|[Metodo UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al profiler che si è verificata una transizione da codice non gestito a codice gestito.|  
  
## <a name="remarks"></a>Note  
 CLR chiama un metodo `ICorProfilerCallback` (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) dell'interfaccia per notificare al profiler quando un evento, a cui il profiler ha effettuato la sottoscrizione, si verifica. Si tratta dell'interfaccia di callback da CLR per comunicare con il profiler di codice.  
  
 Un code profiler deve implementare i metodi del `ICorProfilerCallback` interfaccia. Per .NET Framework versione 2.0 o versione successiva, il profiler deve implementare anche il `ICorProfilerCallback2` metodi. Ogni implementazione del metodo deve restituire un valore HRESULT che ha un valore S_OK se l'operazione riesce o E_FAIL in caso di errore. Attualmente, CLR ignora il valore HRESULT restituito da ogni callback tranne [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Nel Registro di sistema Microsoft Windows, un code profiler devono registrare il proprio oggetto modello COM (Component Object) che implementa il `ICorProfilerCallback` e `ICorProfilerCallback2` interfacce. Un code profiler sottoscrive gli eventi per cui vuole ricevere notifica chiamando [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Ciò avviene solitamente nell'implementazione del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Quindi, il profiler è in grado di ricevere una notifica dal runtime quando un evento sta per verificarsi o è stata eseguita in un processo di runtime in esecuzione.  
  
> [!NOTE]
>  Il profiler si registra un singolo oggetto COM. Se il profiler è destinato a .NET Framework versione 1.0 o 1.1, che deve implementare solo i metodi dell'oggetto COM `ICorProfilerCallback`. Se è destinata a .NET Framework versione 2.0 o versione successiva, l'oggetto COM deve implementare anche i metodi di `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Interfaccia ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [Interfaccia ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
