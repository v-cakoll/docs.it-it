---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb3e382a93f28ea99c66268e6e402ea275961047
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387195"
---
# <a name="corprofeunsupportedcallsequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT è stata introdotta in .NET Framework versione 2.0. Il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] restituisce questo valore HRESULT in due scenari:  
  
-   Quando un profiler che forzatamente Reimposta un thread registrare contesto in un momento arbitrario in modo che il thread tenta di accedere alle strutture che sono in uno stato incoerente.  
  
-   Quando un profiler tenta di chiamare un metodo informativo che attiva l'operazione di garbage collection da un metodo di callback che impedisce l'operazione di garbage collection.  
  
 Questi due scenari sono illustrati nelle sezioni seguenti.  
  
## <a name="hijacking-profilers"></a>Hijack del profiler  
 (In questo scenario è principalmente un problema con l'Hijack profiler, anche se vi sono casi in cui profiler non Hijack possono visualizzare questo valore HRESULT).  
  
 In questo scenario, un profiler che forzatamente Reimposta il contesto un thread registratore di cassa in un momento arbitrario in modo che il thread è possibile immettere il codice del profiler o immettere nuovamente common language runtime (CLR) tramite un [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) (metodo).  
  
 Molti degli ID che l'API di profilatura fornisce punto alle strutture di dati in Common Language Runtime. Molti `ICorProfilerInfo` chiama semplicemente leggere le informazioni da queste strutture di dati e passarli nuovamente. Tuttavia, CLR potrebbe cambiare in tali strutture come l'esecuzione e per eseguire questa operazione potrebbe utilizzare blocchi. Si supponga che Common Language Runtime è stato già che contiene (o tentativo di acquisizione) un blocco al momento il profiler soggetta a Hijack del thread. Se il thread immette nuovamente il CLR e tenta di acquisire altri blocchi o esaminare strutture che erano in corso di modifica, queste strutture potrebbero essere in uno stato incoerente. Violazioni di accesso e di deadlock possono verificarsi con facilità in tali situazioni.  
  
 In generale, quando viene eseguito codice all'interno di un profiler non Hijack un [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) metodo e le chiamate a un `ICorProfilerInfo` metodo con i parametri validi, opportuno non causare un deadlock o ricevono una violazione di accesso. Ad esempio, il codice del profiler viene eseguito all'interno di [ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) metodo può richiedere informazioni sulla classe chiamando il [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) metodo. Il codice potrebbe ricevere un HRESULT CORPROF_E_DATAINCOMPLETE per indicare che le informazioni sono disponibili; Tuttavia, non verrà deadlock o ricevono una violazione di accesso. Questa classe di chiamate all'interno `ICorProfilerInfo` vengono chiamate sincrone, poiché questi vengono prodotti da un `ICorProfilerCallback` (metodo).  
  
 Tuttavia, un thread gestito che esegue codice che non rientra in un `ICorProfilerCallback` metodo viene considerato per essere effettua una chiamata asincrona. In .NET Framework versione 1, era difficile determinare cosa potrebbe accadere in una chiamata asincrona. La chiamata potrebbe causare un deadlock, arresto anomalo del sistema o fornire una risposta non valida. .NET Framework versione 2.0 ha introdotto alcuni controlli semplici per permettere di evitare questo problema. In .NET Framework 2.0, se si chiama un tipo unsafe `ICorProfilerInfo` funzionare in modo asincrono, avrà esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 In generale, le chiamate asincrone non sono sicuri. Tuttavia, i metodi seguenti sono sicuri e in particolare supportano chiamate asincrone:  
  
-   [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
-   [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
-   [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
-   [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
-   [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
-   [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
-   [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
-   [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
-   [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
-   [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
-   [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
-   [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
-   [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
-   [IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
-   [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
-   [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Per altre informazioni, vedere l'intervento [motivo per cui abbiamo CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://go.microsoft.com/fwlink/?LinkId=169156) nel blog di API di profilatura di CLR.  
  
## <a name="triggering-garbage-collections"></a>Attivazione di Garbage Collection  
 Questo scenario prevede un profiler che è in esecuzione all'interno di un metodo di callback (ad esempio, uno del `ICorProfilerCallback` metodi) che impedisce a garbage collection. Se il profiler tenta di chiamare un metodo informativo (ad esempio, un metodo su di `ICorProfilerInfo` interface) che potrebbe attivare una garbage collection, il metodo informativo ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Nella tabella seguente visualizza i metodi di callback che impediscono operazioni di garbage collection e metodi informativo che potrebbero attivare una garbage collection. Se il profiler viene eseguito all'interno di uno dei metodi di callback elencate e chiama uno dei metodi elencati informativi, tale metodo informativo ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Metodi di callback che impediscono operazioni di garbage collection|Metodi informativo che attivano operazioni di garbage collection|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [Interfaccia ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
