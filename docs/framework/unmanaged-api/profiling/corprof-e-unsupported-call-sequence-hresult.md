---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: b4ab5c8f7cdca1303cb4fbbc4fa39db3c5977c15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867009"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT

Il valore HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE è stato introdotto nella versione .NET Framework 2,0. .NET Framework 4 restituisce questo valore HRESULT in due scenari:  
  
- Quando un profiler di Hijack reimposta forzatamente il contesto di registro di un thread in un momento arbitrario, in modo che il thread tenti di accedere a strutture in uno stato incoerente.  
  
- Quando un profiler tenta di chiamare un metodo informativo che attiva Garbage Collection da un metodo di callback che impedisce l'Garbage Collection.  
  
Questi due scenari sono illustrati nelle sezioni seguenti.  
  
## <a name="hijacking-profilers"></a>Hijack di Profiler  

  Questo scenario è principalmente un problema con il Hijack dei profiler, sebbene in alcuni casi i profiler non di Hijack possano visualizzare questo HRESULT.  
  
 In questo scenario, un profiler di Hijack reimposta forzatamente il contesto di registro di un thread in un momento arbitrario, in modo che il thread possa immettere codice del profiler o immettere nuovamente il Common Language Runtime (CLR) tramite un metodo [ICorProfilerInfo](icorprofilerinfo-interface.md) .  
  
 Molti degli ID che l'API di profilatura fornisce punti alle strutture di dati in CLR. Molti `ICorProfilerInfo` chiamano semplicemente le informazioni da queste strutture di dati e le passano nuovamente. Tuttavia, il CLR potrebbe modificare gli elementi di tali strutture durante l'esecuzione e potrebbe usare i blocchi per farlo. Si supponga che CLR sia già in possesso (o che tenti di acquisire) un blocco nel momento in cui il profiler ha eseguito il hijack del thread. Se il thread immette nuovamente CLR e tenta di assumere più blocchi o ispezionare le strutture in corso di modifica, è possibile che queste strutture siano in uno stato incoerente. In tali situazioni è possibile che si verifichino facilmente deadlock e violazioni di accesso.  
  
 In generale, quando un profiler non di Hijack esegue codice all'interno di un metodo [ICorProfilerCallback](icorprofilercallback-interface.md) e chiama un metodo di `ICorProfilerInfo` con parametri validi, non dovrebbe verificarsi un deadlock o ricevere una violazione di accesso. Ad esempio, il codice del profiler eseguito all'interno del metodo [ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) può richiedere informazioni sulla classe chiamando il metodo [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) . Il codice potrebbe ricevere un CORPROF_E_DATAINCOMPLETE HRESULT per indicare che le informazioni non sono disponibili. Tuttavia, non si verifica un deadlock o riceve una violazione di accesso. Queste chiamate in `ICorProfilerInfo` vengono considerate sincrone, in quanto vengono eseguite da un `ICorProfilerCallback` metodo.  
  
 Tuttavia, un thread gestito che esegue codice che non si trova all'interno di un metodo di `ICorProfilerCallback` viene considerato come una chiamata asincrona. In .NET Framework versione 1 è difficile determinare cosa può accadere in una chiamata asincrona. La chiamata potrebbe causare un deadlock, un arresto anomalo o una risposta non valida. In .NET Framework versione 2,0 sono stati introdotti alcuni semplici controlli che consentono di evitare questo problema. In .NET Framework 2,0, se si chiama una funzione di `ICorProfilerInfo` non sicura in modo asincrono, l'operazione ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 In generale, le chiamate asincrone non sono sicure. Tuttavia, i metodi seguenti sono sicuri e supportano in modo specifico le chiamate asincrone:  
  
- [GetEventMask](icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](icorprofilerinfo-getthreadcontext-method.md)  
  
- [GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)  
  
- [GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [IsArrayClass restituirà](icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Per ulteriori informazioni, vedere la voce relativa al [motivo della CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) nel Blog dell'API di profilatura CLR.  
  
## <a name="triggering-garbage-collections"></a>Attivazione di Garbage Collection  
 Questo scenario prevede un profiler in esecuzione all'interno di un metodo di callback (ad esempio, uno dei metodi di `ICorProfilerCallback`) che impedisce Garbage Collection. Se il profiler tenta di chiamare un metodo informativo (ad esempio, un metodo sull'interfaccia `ICorProfilerInfo`) che potrebbe attivare una Garbage Collection, il metodo informativo ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Nella tabella seguente vengono illustrati i metodi di callback che proibiscono le operazioni di Garbage Collection e i metodi informativi che possono attivare operazioni di Garbage Collection. Se il profiler viene eseguito all'interno di uno dei metodi di callback elencati e chiama uno dei metodi informativi elencati, il metodo informativo ha esito negativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Metodi di callback che proibiscono le operazioni di Garbage Collection|Metodi informativi che attivano operazioni di Garbage Collection|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Interfaccia ICorProfilerCallback3](icorprofilercallback3-interface.md)
- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
- [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
