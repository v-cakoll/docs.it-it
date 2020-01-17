---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: 0cf3e05a0353a17541ee890f0871d694acac09fd
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116553"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT

Il valore HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE è stato introdotto nella versione .NET Framework 2,0. .NET Framework 4 restituisce questo valore HRESULT in due scenari:  
  
- Quando un profiler di Hijack reimposta forzatamente il contesto di registro di un thread in un momento arbitrario, in modo che il thread tenti di accedere a strutture in uno stato incoerente.  
  
- Quando un profiler tenta di chiamare un metodo informativo che attiva Garbage Collection da un metodo di callback che impedisce l'Garbage Collection.  
  
Questi due scenari sono illustrati nelle sezioni seguenti.  
  
## <a name="hijacking-profilers"></a>Hijack di Profiler  

  Questo scenario è principalmente un problema con il Hijack dei profiler, sebbene in alcuni casi i profiler non di Hijack possano visualizzare questo HRESULT.  
  
 In questo scenario, un profiler di Hijack reimposta forzatamente il contesto di registro di un thread in un momento arbitrario, in modo che il thread possa immettere codice del profiler o immettere nuovamente il Common Language Runtime (CLR) tramite un metodo [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) .  
  
 Molti degli ID che l'API di profilatura fornisce punti alle strutture di dati in CLR. Molti `ICorProfilerInfo` chiamano semplicemente le informazioni da queste strutture di dati e le passano nuovamente. Tuttavia, il CLR potrebbe modificare gli elementi di tali strutture durante l'esecuzione e potrebbe usare i blocchi per farlo. Si supponga che CLR sia già in possesso (o che tenti di acquisire) un blocco nel momento in cui il profiler ha eseguito il hijack del thread. Se il thread immette nuovamente CLR e tenta di assumere più blocchi o ispezionare le strutture in corso di modifica, è possibile che queste strutture siano in uno stato incoerente. In tali situazioni è possibile che si verifichino facilmente deadlock e violazioni di accesso.  
  
 In generale, quando un profiler non di Hijack esegue codice all'interno di un metodo [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) e chiama un metodo di `ICorProfilerInfo` con parametri validi, non dovrebbe verificarsi un deadlock o ricevere una violazione di accesso. Ad esempio, il codice del profiler eseguito all'interno del metodo [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) può richiedere informazioni sulla classe chiamando il metodo [ICorProfilerInfo2:: GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) . Il codice potrebbe ricevere un CORPROF_E_DATAINCOMPLETE HRESULT per indicare che le informazioni non sono disponibili. Tuttavia, non si verifica un deadlock o riceve una violazione di accesso. Queste chiamate in `ICorProfilerInfo` vengono considerate sincrone, in quanto vengono eseguite da un `ICorProfilerCallback` metodo.  
  
 Tuttavia, un thread gestito che esegue codice che non si trova all'interno di un metodo di `ICorProfilerCallback` viene considerato come una chiamata asincrona. In .NET Framework versione 1 è difficile determinare cosa può accadere in una chiamata asincrona. La chiamata potrebbe causare un deadlock, un arresto anomalo o una risposta non valida. In .NET Framework versione 2,0 sono stati introdotti alcuni semplici controlli che consentono di evitare questo problema. In .NET Framework 2,0, se si chiama una funzione di `ICorProfilerInfo` non sicura in modo asincrono, l'operazione ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 In generale, le chiamate asincrone non sono sicure. Tuttavia, i metodi seguenti sono sicuri e supportano in modo specifico le chiamate asincrone:  
  
- [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
- [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
- [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [IsArrayClass restituirà](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Per ulteriori informazioni, vedere la voce relativa al [motivo della CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) nel Blog dell'API di profilatura CLR.  
  
## <a name="triggering-garbage-collections"></a>Attivazione di Garbage Collection  
 Questo scenario prevede un profiler in esecuzione all'interno di un metodo di callback (ad esempio, uno dei metodi di `ICorProfilerCallback`) che impedisce Garbage Collection. Se il profiler tenta di chiamare un metodo informativo (ad esempio, un metodo sull'interfaccia `ICorProfilerInfo`) che potrebbe attivare una Garbage Collection, il metodo informativo ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Nella tabella seguente vengono illustrati i metodi di callback che proibiscono le operazioni di Garbage Collection e i metodi informativi che possono attivare operazioni di Garbage Collection. Se il profiler viene eseguito all'interno di uno dei metodi di callback elencati e chiama uno dei metodi informativi elencati, il metodo informativo ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Metodi di callback che proibiscono le operazioni di Garbage Collection|Metodi informativi che attivano operazioni di Garbage Collection|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [Interfaccia ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
