---
title: Enumerazione COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 5c6e34746368a7658c43fe0e2472000c29292569
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175213"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="18920-102">Enumerazione COR_PRF_HIGH_MONITOR</span><span class="sxs-lookup"><span data-stu-id="18920-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="18920-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="18920-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="18920-104">Fornisce flag oltre a quelli presenti nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) che il profiler può specificare per il [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) metodo durante il caricamento.</span><span class="sxs-lookup"><span data-stu-id="18920-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18920-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18920-105">Syntax</span></span>  
  
```cpp
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,
    COR_PRF_HIGH_DISABLE_TIERED_COMPILATION       = 0x00000008,
    COR_PRF_HIGH_BASIC_GC                         = 0x00000010,
    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS         = 0x00000020,
    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED    = 0x00000040,
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED |
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS |
                                                    COR_PRF_HIGH_BASIC_GC |
                                                    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS |
                                                    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = COR_PRF_HIGH_DISABLE_TIERED_COMPILATION  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="18920-106">Members</span><span class="sxs-lookup"><span data-stu-id="18920-106">Members</span></span>  
  
|<span data-ttu-id="18920-107">Membro</span><span class="sxs-lookup"><span data-stu-id="18920-107">Member</span></span>|<span data-ttu-id="18920-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18920-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="18920-109">Nessun flag impostato.</span><span class="sxs-lookup"><span data-stu-id="18920-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="18920-110">Controlla il callback [di ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) per l'aggiunta di riferimenti all'assembly durante il percorso di chiusura dei riferimenti all'assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="18920-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="18920-111">Controlla il callback [di ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) per gli aggiornamenti al flusso di simboli associato a un modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="18920-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="18920-112">Controlla il callback [di ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) per indicare quando un metodo dinamico è stato sottoposto a Garbage Collection e scaricato.</span><span class="sxs-lookup"><span data-stu-id="18920-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="18920-113">.NET Core 3.0 e versioni successive solo: disabilita la [compilazione a livelli](../../../core/whats-new/dotnet-core-3-0.md) per i profiler.</span><span class="sxs-lookup"><span data-stu-id="18920-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="18920-114">.NET Core 3.0 e versioni successive solo: fornisce [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)un'opzione di profilatura GC leggera rispetto a .</span><span class="sxs-lookup"><span data-stu-id="18920-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="18920-115">Controlla solo i callback [di GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)e [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) .</span><span class="sxs-lookup"><span data-stu-id="18920-115">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="18920-116">A `COR_PRF_MONITOR_GC` differenza `COR_PRF_HIGH_BASIC_GC` del flag, non disabilita l'operazione di Garbage Collection simultanea.</span><span class="sxs-lookup"><span data-stu-id="18920-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="18920-117">.NET Core 3.0 e versioni successive solo: abilita i callback [MovedReferences](icorprofilercallback-movedreferences-method.md) e [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) solo per la compattazione di NC.</span><span class="sxs-lookup"><span data-stu-id="18920-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="18920-118">.NET Core 3.0 e versioni [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)successive solo: simile a , ma fornisce informazioni sulle allocazioni di oggetti solo per l'heap oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="18920-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="18920-119">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che richiedono le immagini ottimizzate per il profiler.</span><span class="sxs-lookup"><span data-stu-id="18920-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="18920-120">Corrisponde al `COR_PRF_REQUIRE_PROFILE_IMAGE` flag nell'enumerazione [COR_PRF_MONITOR.](cor-prf-monitor-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="18920-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="18920-121">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="18920-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="18920-122">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati solo durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="18920-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="18920-123">Se si prova a modificare uno di questi flag altrove, viene restituito un valore `HRESULT` che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="18920-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18920-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="18920-124">Remarks</span></span>

<span data-ttu-id="18920-125">I `COR_PRF_HIGH_MONITOR` flag vengono `pdwEventsHigh` utilizzati con il parametro dei metodi [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) e [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="18920-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="18920-126">A partire da .NET Framework 4.6.1, il valore del `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` valore modificato da 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="18920-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="18920-127">A partire da .NET Framework 4.7.2, il relativo valore è stato modificato da `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span><span class="sxs-lookup"><span data-stu-id="18920-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>

<span data-ttu-id="18920-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE`deve essere una maschera di bit che rappresenta tutti i flag che possono essere impostati solo durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="18920-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="18920-129">Se si tenta di modificare uno di `HRESULT`questi flag altrove, si ottiene un errore.</span><span class="sxs-lookup"><span data-stu-id="18920-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="18920-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18920-130">Requirements</span></span>

<span data-ttu-id="18920-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18920-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="18920-132">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18920-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="18920-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18920-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="18920-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18920-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18920-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18920-135">See also</span></span>

- [<span data-ttu-id="18920-136">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="18920-136">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="18920-137">Enumerazione COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="18920-137">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="18920-138">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="18920-138">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
