---
title: Enumerazione COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c92ba2b5eac5eb1368a7d7ccf3b666886f4ca92a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454714"
---
# <a name="corprfhighmonitor-enumeration"></a><span data-ttu-id="22a9e-102">Enumerazione COR_PRF_HIGH_MONITOR</span><span class="sxs-lookup"><span data-stu-id="22a9e-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>
<span data-ttu-id="22a9e-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="22a9e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="22a9e-104">Fornisce flag oltre a quelli di [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione che il profiler può specificare per il [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo durante il caricamento.</span><span class="sxs-lookup"><span data-stu-id="22a9e-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a9e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22a9e-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,     
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,    
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="22a9e-106">Membri</span><span class="sxs-lookup"><span data-stu-id="22a9e-106">Members</span></span>  
  
|<span data-ttu-id="22a9e-107">Membro</span><span class="sxs-lookup"><span data-stu-id="22a9e-107">Member</span></span>|<span data-ttu-id="22a9e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22a9e-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="22a9e-109">Nessun flag impostato.</span><span class="sxs-lookup"><span data-stu-id="22a9e-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="22a9e-110">Controlli di [icorprofilercallback6:: Getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback per l'aggiunta di riferimenti ad assembly durante il percorso di chiusura del riferimento assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="22a9e-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="22a9e-111">Controlli di [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback per gli aggiornamenti per il flusso di simboli associato a un modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="22a9e-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="22a9e-112">I controlli di [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback per indicare quando un metodo dinamico è stato sottoposto a garbage collection e scaricato.</span><span class="sxs-lookup"><span data-stu-id="22a9e-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|   
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="22a9e-113">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che richiedono le immagini ottimizzate per il profiler.</span><span class="sxs-lookup"><span data-stu-id="22a9e-113">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="22a9e-114">Corrisponde alla `COR_PRF_REQUIRE_PROFILE_IMAGE` flag nel [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="22a9e-114">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="22a9e-115">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22a9e-115">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="22a9e-116">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati solo durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="22a9e-116">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="22a9e-117">Se si prova a modificare uno di questi flag altrove, viene restituito un valore `HRESULT` che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="22a9e-117">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22a9e-118">Note</span><span class="sxs-lookup"><span data-stu-id="22a9e-118">Remarks</span></span>  
 <span data-ttu-id="22a9e-119">Il `COR_PRF_HIGH_MONITOR` flag sono utilizzati con il `pdwEventsHigh` parametro del [icorprofilerinfo5:: Geteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) e [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="22a9e-119">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="22a9e-120">A partire dal [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], il valore di `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` modificato da 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="22a9e-120">Starting with the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="22a9e-121">A partire da .NET Framework 4.7.2, modificarne il valore da `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span><span class="sxs-lookup"><span data-stu-id="22a9e-121">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

<span data-ttu-id="22a9e-122">`COR_PRF_HIGH_MONITOR_IMMUTABLE` deve essere una maschera di bit che rappresenta tutti i flag che possono essere impostati solo durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="22a9e-122">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="22a9e-123">Si prova a modificare uno di questi flag altrove, viene restituito un errore `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="22a9e-123">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="22a9e-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22a9e-124">Requirements</span></span>  
 <span data-ttu-id="22a9e-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22a9e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a9e-126">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22a9e-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22a9e-127">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="22a9e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22a9e-128">**Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a9e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a9e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22a9e-129">See Also</span></span>  
 [<span data-ttu-id="22a9e-130">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="22a9e-130">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [<span data-ttu-id="22a9e-131">Enumerazione COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="22a9e-131">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 [<span data-ttu-id="22a9e-132">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="22a9e-132">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
