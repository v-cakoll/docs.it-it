---
title: Enumerazione COR_PRF_MONITOR
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: 2d7984ce109fb2bac5a36ab5e4c83f386de5a488
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867100"
---
# <a name="cor_prf_monitor-enumeration"></a><span data-ttu-id="e9fb9-102">Enumerazione COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="e9fb9-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="e9fb9-103">Contiene i valori usati per specificare il comportamento, le funzionalità o gli eventi ai quali il profiler intende effettuare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9fb9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9fb9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="e9fb9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e9fb9-105">Members</span></span>  
 <span data-ttu-id="e9fb9-106">Le sezioni seguenti elencano `COR_PRF_MONITOR` membri dell'enumerazione per categoria.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="e9fb9-107">Le categorie sono:</span><span class="sxs-lookup"><span data-stu-id="e9fb9-107">The categories are:</span></span>  
  
- [<span data-ttu-id="e9fb9-108">Nessun flag impostato</span><span class="sxs-lookup"><span data-stu-id="e9fb9-108">No flags set</span></span>](#None)  
  
- [<span data-ttu-id="e9fb9-109">Flag di callback</span><span class="sxs-lookup"><span data-stu-id="e9fb9-109">Callback flags</span></span>](#Callback)  
  
- [<span data-ttu-id="e9fb9-110">Flag di abilitazione delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="e9fb9-110">Feature-enabling flags</span></span>](#Feature)  
  
- [<span data-ttu-id="e9fb9-111">Flag di configurazione</span><span class="sxs-lookup"><span data-stu-id="e9fb9-111">Configuration flags</span></span>](#Config)  
  
- [<span data-ttu-id="e9fb9-112">Flag compositi</span><span class="sxs-lookup"><span data-stu-id="e9fb9-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a><span data-ttu-id="e9fb9-113">Nessun flag impostato</span><span class="sxs-lookup"><span data-stu-id="e9fb9-113">No flags set</span></span>  
  
|<span data-ttu-id="e9fb9-114">Member</span><span class="sxs-lookup"><span data-stu-id="e9fb9-114">Member</span></span>|<span data-ttu-id="e9fb9-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9fb9-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="e9fb9-116">Nessun flag impostato.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a><span data-ttu-id="e9fb9-117">Flag di callback</span><span class="sxs-lookup"><span data-stu-id="e9fb9-117">Callback flags</span></span>  
  
|<span data-ttu-id="e9fb9-118">Member</span><span class="sxs-lookup"><span data-stu-id="e9fb9-118">Member</span></span>|<span data-ttu-id="e9fb9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9fb9-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="e9fb9-120">Abilita tutti gli eventi di callback.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="e9fb9-121">Controlla la `AppDomainCreation*` e `AppDomainShutdown*` i callback nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="e9fb9-122">Controlla la `AssemblyLoad*` e `AssemblyUnload*` i callback nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="e9fb9-123">Controlla i callback di `JITCachedFunctionSearch*` nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="e9fb9-124">Il comportamento di questo flag è stato modificato in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="e9fb9-125">Controlla i callback di `COMClassicVTable*` nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="e9fb9-126">Controlla la `ClassLoad*` e `ClassUnload*` i callback nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="e9fb9-127">Controlla i callback di `ExceptionCLRCatcher*` nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="e9fb9-128">Controlla i callback [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) e [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="e9fb9-128">Controls the [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="e9fb9-129">Controlla le [funzioni statiche globali di profilatura](profiling-global-static-functions.md)`FunctionEnter*`, `FunctionLeave*`e `FunctionTailCall*`.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="e9fb9-130">Controlla il callback di [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) e i callback `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`e `ExceptionCatcher*` nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-130">Controls the [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="e9fb9-131">Controlla il callback di [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-131">Controls the [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="e9fb9-132">Controlla i callback di [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md), [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)e [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) nelle interfacce del `ICorProfilerCallback*`.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-132">Controls the [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span> <span data-ttu-id="e9fb9-133">Quando `COR_PRF_MONITOR_GC` viene allocato, il Garbage Collection simultaneo è disattivato.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-133">When `COR_PRF_MONITOR_GC` is allocated, concurrent garbage collection is turned off.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="e9fb9-134">Controlla i callback `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)e [JITInlining](icorprofilercallback-jitinlining-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-134">Controls the `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="e9fb9-135">Controlla i callback `ModuleLoad*`, `ModuleUnload*`e [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-135">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="e9fb9-136">Controlla il callback di [ObjectAllocated](icorprofilercallback-objectallocated-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-136">Controls the [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="e9fb9-137">Controlla i callback di `Remoting*` nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-137">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="e9fb9-138">Controlla se i callback di `Remoting*` monitoreranno gli eventi asincroni.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-138">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="e9fb9-139">Controlla se un cookie viene passato ai callback di `Remoting*`.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-139">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="e9fb9-140">Controlla i callback `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)e [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-140">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="e9fb9-141">Controlla i callback di [ThreadCreated](icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)e [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) nelle interfacce [ICorProfilerCallback](icorprofilercallback-interface.md) e [ICorProfilerCallback2](icorprofilercallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-141">Controls the [ThreadCreated](icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](icorprofilercallback-interface.md) and [ICorProfilerCallback2](icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a><span data-ttu-id="e9fb9-142">Flag di abilitazione delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="e9fb9-142">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="e9fb9-143">Member</span><span class="sxs-lookup"><span data-stu-id="e9fb9-143">Member</span></span>|<span data-ttu-id="e9fb9-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9fb9-144">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="e9fb9-145">Consente il recupero di un `ClassID` esatto per una funzione generica chiamando il metodo [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) con un valore `COR_PRF_FRAME_INFO` restituito dal callback [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-145">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="e9fb9-146">Abilita la traccia degli argomenti usando il callback di [FunctionEnter2](functionenter2-function.md) o il callback di [FunctionEnter3WithInfo](functionenter3withinfo-function.md) e il metodo [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-146">Enables argument tracing using the [FunctionEnter2](functionenter2-function.md) callback or the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="e9fb9-147">Abilita la traccia dei valori restituiti usando il callback [FunctionLeave2](functionleave2-function.md) o il callback di [FunctionLeave3WithInfo](functionleave3withinfo-function.md) e il metodo [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-147">Enables tracing of return values by using the [FunctionLeave2](functionleave2-function.md) callback or the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="e9fb9-148">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-148">Deprecated.</span></span><br /><br /> <span data-ttu-id="e9fb9-149">Il debug in-process non è supportato.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-149">In process debugging is not supported.</span></span> <span data-ttu-id="e9fb9-150">Questo flag non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-150">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="e9fb9-151">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-151">Deprecated.</span></span><br /><br /> <span data-ttu-id="e9fb9-152">Consente al profiler di ottenere mappe da IL a native usando [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span><span class="sxs-lookup"><span data-stu-id="e9fb9-152">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="e9fb9-153">A partire da .NET Framework versione 2.0, il runtime tiene sempre traccia dei mapping da codice IL a codice nativo, pertanto questo flag sarà considerato sempre impostato.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-153">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="e9fb9-154">Indica al runtime di notificare al profiler le allocazioni degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-154">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="e9fb9-155">Questo flag deve essere impostato durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-155">This flag must be set during initialization.</span></span> <span data-ttu-id="e9fb9-156">Consente al profiler di usare successivamente il flag di `COR_PRF_MONITOR_OBJECT_ALLOCATED` per ricevere callback [ObjectAllocated](icorprofilercallback-objectallocated-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-156">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="e9fb9-157">Consente le chiamate ai metodi [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) e [RequestRevert](icorprofilerinfo4-requestrevert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-157">Enables calls to the [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="e9fb9-158">Il profiler deve impostare questo flag all'avvio.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-158">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="e9fb9-159">Se il profiler specifica questo flag, deve specificare anche `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-159">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="e9fb9-160">Consente le chiamate al metodo [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb9-160">Enables calls to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a><span data-ttu-id="e9fb9-161">Flag di configurazione</span><span class="sxs-lookup"><span data-stu-id="e9fb9-161">Configuration flags</span></span>  
  
|<span data-ttu-id="e9fb9-162">Member</span><span class="sxs-lookup"><span data-stu-id="e9fb9-162">Member</span></span>|<span data-ttu-id="e9fb9-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9fb9-163">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="e9fb9-164">Impedisce il caricamento di tutte le immagini native, comprese le immagini ottimizzate per il profiler.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-164">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="e9fb9-165">Se vengono specificati sia questo flag che il flag `COR_PRF_USE_PROFILE_IMAGES`, verrà usato il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-165">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="e9fb9-166">Disabilita tutte le funzionalità inline.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-166">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="e9fb9-167">Disabilita tutte le ottimizzazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-167">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="e9fb9-168">Disabilita i controlli per la trasparenza della sicurezza eseguiti generalmente durante la compilazione JIT e il caricamento delle classi per gli assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-168">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="e9fb9-169">Ciò può rendere alcune strumentazioni più facili da eseguire.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-169">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="e9fb9-170">Fa sì che la ricerca delle immagini native venga avviata per le immagini ottimizzate per il profiler.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-170">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="e9fb9-171">Se non viene trovata alcuna immagine ottimizzata per il profiler relativa a un assembly specifico, Common Language Runtime esegue il fallback a JIT per tale assembly.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-171">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="e9fb9-172">Se vengono specificati sia questo flag che il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`, verrà usato il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-172">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a><span data-ttu-id="e9fb9-173">Flag composti</span><span class="sxs-lookup"><span data-stu-id="e9fb9-173">Composite flags</span></span>  
  
|<span data-ttu-id="e9fb9-174">Member</span><span class="sxs-lookup"><span data-stu-id="e9fb9-174">Member</span></span>|<span data-ttu-id="e9fb9-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9fb9-175">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="e9fb9-176">Rappresenta tutti i valori del flag `COR_PRF_MONITOR`.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-176">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="e9fb9-177">Rappresenta tutti i flag `COR_PRF_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-177">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="e9fb9-178">La sezione sintassi indica i singoli flag presenti in questa maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-178">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="e9fb9-179">Abilita tutti gli eventi di callback.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-179">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="e9fb9-180">Rappresenta tutti i flag `COR_PRF_MONITOR` che possono essere impostati solo durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-180">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="e9fb9-181">Se si prova a modificare uno di questi flag dopo l'inizializzazione, viene restituito un valore `HRESULT` che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-181">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="e9fb9-182">Rappresenta tutti i flag `COR_PRF_MONITOR` che richiedono le immagini ottimizzate per il profiler.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-182">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9fb9-183">Note</span><span class="sxs-lookup"><span data-stu-id="e9fb9-183">Remarks</span></span>  
 <span data-ttu-id="e9fb9-184">Un valore `COR_PRF_MONITOR` viene usato con i metodi [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per definire le notifiche degli eventi che la Common Language Runtime apporta al profiler.</span><span class="sxs-lookup"><span data-stu-id="e9fb9-184">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9fb9-185">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e9fb9-185">Requirements</span></span>  
 <span data-ttu-id="e9fb9-186">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9fb9-186">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9fb9-187">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9fb9-187">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9fb9-188">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9fb9-188">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9fb9-189">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9fb9-189">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9fb9-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9fb9-190">See also</span></span>

- [<span data-ttu-id="e9fb9-191">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="e9fb9-191">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="e9fb9-192">Metodo GetEventMask</span><span class="sxs-lookup"><span data-stu-id="e9fb9-192">GetEventMask Method</span></span>](icorprofilerinfo-geteventmask-method.md)
- [<span data-ttu-id="e9fb9-193">Metodo SetEventMask</span><span class="sxs-lookup"><span data-stu-id="e9fb9-193">SetEventMask Method</span></span>](icorprofilerinfo-seteventmask-method.md)
