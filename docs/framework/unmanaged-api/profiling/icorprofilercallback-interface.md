---
title: Interfaccia ICorProfilerCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback
helpviewer_keywords: ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type: apiref
caps.latest.revision: "29"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3370dade937d67aa40be263faf3a433d142d932c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback-interface"></a>Interfaccia ICorProfilerCallback
Fornisce i metodi utilizzati da common language runtime (CLR) per notificare a un code profiler quando si verificano gli eventi a cui ha effettuato la sottoscrizione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[AppDomainCreationFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al profiler che è stato creato un dominio applicazione.|  
|[AppDomainCreationStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al profiler la creazione di un dominio applicazione.|  
|[AppDomainShutdownFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al profiler che un dominio applicazione è stato scaricato da un processo.|  
|[AppDomainShutdownStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al profiler che un dominio applicazione è in corso lo scaricamento da un processo.|  
|[AssemblyLoadFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Notifica al profiler che un assembly è stato completato il caricamento.|  
|[AssemblyLoadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Notifica al profiler che un assembly viene caricato.|  
|[AssemblyUnloadFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al profiler che un assembly è stato scaricato.|  
|[AssemblyUnloadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al profiler che un assembly è stato scaricato.|  
|[ClassLoadFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Notifica al profiler che ha terminato il caricamento di una classe.|  
|[ClassLoadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Notifica al profiler che una classe venga caricata.|  
|[ClassUnloadFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Notifica al profiler che una classe è terminato lo scaricamento.|  
|[ClassUnloadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Notifica al profiler che è in corso lo scaricamento di una classe.|  
|[COMClassicVTableCreated (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al profiler che è stato creato un runtime callable wrapper (RCW) per l'IID e la classe specificata.|  
|[COMClassicVTableDestroyed (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al profiler che è in corso l'eliminazione di un RCW.|  
|[ExceptionCatcherEnter (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al profiler che viene passato a appropriato controllo `catch` blocco.|  
|[ExceptionCatcherLeave (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al profiler che controllo viene passato appropriata `catch` blocco.|  
|[ExceptionCLRCatcherExecute (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Obsoleti in .NET Framework versione 2.0.|  
|[ExceptionCLRCatcherFound (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Obsoleti in .NET Framework 2.0.|  
|[ExceptionOSHandlerEnter (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Non implementato. Un profiler che richiede informazioni sull'eccezione non gestita è necessario ottenere queste informazioni tramite altri mezzi.|  
|[ExceptionOSHandlerLeave (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Non implementato. Un profiler che richiede informazioni sull'eccezione non gestita è necessario ottenere queste informazioni tramite altri mezzi.|  
|[ExceptionSearchCatcherFound (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha individuato un gestore per l'eccezione generata.|  
|[ExceptionSearchFilterEnter (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al profiler che un filtro utente è in esecuzione.|  
|[ExceptionSearchFilterLeave (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al profiler che un filtro utente appena terminata l'esecuzione.|  
|[ExceptionSearchFunctionEnter (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha immesso una funzione.|  
|[ExceptionSearchFunctionLeave (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha terminato la ricerca di una funzione.|  
|[ExceptionThrown (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Notifica al profiler che è stata generata un'eccezione.|  
|[ExceptionUnwindFinallyEnter (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al profiler che la fase di rimozione dell'eccezione gestione sta entrando in un `finally` clausola contenuta nella funzione specificata.|  
|[ExceptionUnwindFinallyLeave (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al profiler che la fase di rimozione dell'eccezione Gestione ha lasciato una `finally` clausola.|  
|[ExceptionUnwindFunctionEnter (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al profiler che la fase di rimozione di gestione delle eccezioni ha immesso una funzione.|  
|[ExceptionUnwindFunctionLeave (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al profiler che la fase di rimozione di gestione delle eccezioni ha terminato la rimozione di una funzione.|  
|[FunctionUnloadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Notifica al profiler che il runtime ha iniziato a scaricare una funzione.|  
|[Initialize (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Chiamato per inizializzare il profiler ogni volta che viene avviata una nuova applicazione CLR.|  
|[JITCachedFunctionSearchFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al profiler che una ricerca è stato completato per una funzione che è stata compilata in precedenza usando NGen.exe.|  
|[JITCachedFunctionSearchStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al profiler che si è iniziata una ricerca per una funzione che è stata compilata in precedenza usando NGen.exe.|  
|[JITCompilationFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Notifica al profiler che il compilatore JIT ha terminato la compilazione di una funzione.|  
|[JITCompilationStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato per la compilazione di una funzione.|  
|[JITFunctionPitched (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Notifica al profiler che una funzione che è stato compilato tramite JIT è stato rimosso dalla memoria.|  
|[JITInlining (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Notifica al profiler che il compilatore JIT sta per inserire una funzione in linea con un'altra funzione.|  
|[ManagedToUnmanagedTransition (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al profiler che si è verificata una transizione da codice gestito a codice non gestito.|  
|[ModuleAttachedToAssembly (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al profiler che un modulo viene allegato a tale assembly.|  
|[ModuleLoadFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Notifica al profiler che un modulo ha terminato il caricamento.|  
|[ModuleLoadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Notifica al profiler che un modulo caricato.|  
|[ModuleUnloadFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Notifica al profiler che un modulo è terminato lo scaricamento.|  
|[ModuleUnloadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Notifica al profiler che sta per essere scaricato un modulo.|  
|[MovedReferences (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Notifica al profiler sui riferimenti a oggetti che sono stati spostati durante l'operazione di garbage collection.|  
|[ObjectAllocated (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Notifica al profiler che è stata allocata memoria nell'heap per un oggetto.|  
|[ObjectReferences (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Notifica al profiler gli oggetti in memoria a cui fa riferimento l'oggetto specificato.|  
|[ObjectsAllocatedByClass (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al profiler il numero di istanze di ogni classe specificata che sono stati creati dall'operazione di garbage collection precedente.|  
|[RemotingClientInvocationFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al profiler che una chiamata remota completamento dell'esecuzione nel client.|  
|[RemotingClientInvocationStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al profiler che ha avviato una chiamata remota.|  
|[RemotingClientReceivingReply (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al profiler che la parte del server di una chiamata remota è stata completata e il client è ora di ricezione e sta per elaborare la risposta.|  
|[RemotingClientSendingMessage (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al profiler che il client invia una richiesta al server.|  
|[RemotingServerInvocationReturned (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al profiler che il processo è terminato chiamando un metodo in risposta a una richiesta di chiamata di metodo remoto.|  
|[RemotingServerInvocationStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al profiler che il processo richiama un metodo in risposta a una richiesta di chiamata di metodo remoto.|  
|[RemotingServerReceivingMessage (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al profiler che il processo riceve una richiesta di attivazione o la chiamata di metodo remoto.|  
|[RemotingServerSendingReply (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata di metodo remoto e sta per trasmettere la risposta tramite un canale.|  
|[RootReferences (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Notifica al profiler con informazioni sui riferimenti principali dopo l'operazione di garbage collection.|  
|[RuntimeResumeFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Notifica al profiler che il runtime ha ripreso tutti i thread di runtime e ha restituito al normale funzionamento.|  
|[RuntimeResumeStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Notifica al profiler che il runtime viene ripresa di tutti i thread in fase di esecuzione.|  
|[RuntimeSuspendAborted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al profiler che il runtime ha interrotto la sospensione in fase di esecuzione in corso.|  
|[RuntimeSuspendFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al profiler che il runtime è stata completata la sospensione di tutti i thread in fase di esecuzione.|  
|[RuntimeSuspendStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al profiler che il runtime sta per sospendere tutti i thread in fase di esecuzione.|  
|[RuntimeThreadResumed (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Notifica al profiler che il thread specificato ha ripreso dopo la sospensione.|  
|[RuntimeThreadSuspended (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al profiler che il thread specificato è stata o sta per essere sospeso.|  
|[Shutdown (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Notifica al profiler che l'applicazione è in fase di chiusura.|  
|[ThreadAssignedToOSThread (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al profiler che un thread gestito viene implementato utilizzando un thread del sistema operativo specifico (sistema operativo).|  
|[ThreadCreated (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Notifica al profiler che un thread è stato creato.|  
|[ThreadDestroyed (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Notifica al profiler che un thread è stato eliminato.|  
|[UnmanagedToManagedTransition (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al profiler che si è verificata una transizione da codice non gestito a codice gestito.|  
  
## <a name="remarks"></a>Note  
 CLR chiama un metodo di `ICorProfilerCallback` (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) interfaccia per notificare al profiler di eventi, a cui il profiler ha effettuato la sottoscrizione, si verifica. Si tratta dell'interfaccia di callback da CLR per comunicare con il profiler di codice.  
  
 Un code profiler deve implementare i metodi del `ICorProfilerCallback` interfaccia. Per .NET Framework versione 2.0 o versione successiva, il profiler deve implementare anche il `ICorProfilerCallback2` metodi. Ogni implementazione del metodo deve restituire un HRESULT che ha un valore S_OK in caso di esito positivo o E_FAIL in caso di errore. Attualmente, CLR ignora il valore HRESULT restituito da ogni callback a eccezione di [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Nel Registro di sistema Microsoft Windows, un code profiler deve registrare il proprio oggetto di modello COM (Component Object) che implementa il `ICorProfilerCallback` e `ICorProfilerCallback2` interfacce. Un code profiler sottoscrive gli eventi per il quale desidera ricevere notifica chiamando [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Questa operazione viene in genere eseguita nell'implementazione del profiler di [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Quindi, il profiler è in grado di ricevere una notifica dal runtime quando un evento sta per verificarsi o si è appena verificato in un processo di runtime in esecuzione.  
  
> [!NOTE]
>  Il profiler si registra un singolo oggetto COM. Se il profiler è destinato a .NET Framework versione 1.0 o 1.1, che deve implementare solo i metodi dell'oggetto COM `ICorProfilerCallback`. Se è destinato a .NET Framework versione 2.0 o versione successiva, l'oggetto COM deve implementare anche i metodi di `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback2 (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [ICorProfilerCallback3 (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerCallback4 (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
