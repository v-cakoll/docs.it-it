---
title: Metodo ICorProfilerInfo4::RequestReJIT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4da57e95813afa1135482bef7cf6ab50ee6365cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4requestrejit-method"></a><span data-ttu-id="43686-102">Metodo ICorProfilerInfo4::RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="43686-102">ICorProfilerInfo4::RequestReJIT Method</span></span>
<span data-ttu-id="43686-103">Richiede la ricompilazione JIT di tutte le istanze delle funzioni specificate.</span><span class="sxs-lookup"><span data-stu-id="43686-103">Requests a JIT recompilation of all instances of the specified functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43686-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43686-104">Syntax</span></span>  
  
```  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43686-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43686-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="43686-106">[in] Numero di funzioni da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="43686-106">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="43686-107">[in] Specifica la parte `moduleId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="43686-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="43686-108">[in] Specifica la parte `methodId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="43686-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43686-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="43686-109">Return Value</span></span>  
 <span data-ttu-id="43686-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="43686-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="43686-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43686-111">HRESULT</span></span>|<span data-ttu-id="43686-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43686-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43686-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="43686-113">S_OK</span></span>|<span data-ttu-id="43686-114">Si è tentato di contrassegnare tutti i metodi per la ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="43686-114">An attempt was made to mark all the methods for JIT recompilation.</span></span> <span data-ttu-id="43686-115">Il profiler deve implementare il [icorprofilercallback4:: Rejiterror](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) metodo per determinare quali metodi sono stati correttamente contrassegnati per la ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="43686-115">The profiler must implement the [ICorProfilerCallback4::ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.</span></span>|  
|<span data-ttu-id="43686-116">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="43686-116">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="43686-117">Il profiler deve implementare il [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaccia per la chiamata a essere supportato.</span><span class="sxs-lookup"><span data-stu-id="43686-117">The profiler must implement the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="43686-118">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="43686-118">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="43686-119">La ricompilazione JIT non è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="43686-119">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="43686-120">È necessario abilitare la ricompilazione JIT durante l'inizializzazione mediante la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare il `COR_PRF_ENABLE_REJIT` flag.</span><span class="sxs-lookup"><span data-stu-id="43686-120">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="43686-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="43686-121">E_INVALIDARG</span></span>|<span data-ttu-id="43686-122">Il parametro `cFunctions` è pari a 0 oppure `moduleIds` o `methodIds` è `NULL`.</span><span class="sxs-lookup"><span data-stu-id="43686-122">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|||  
|<span data-ttu-id="43686-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="43686-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="43686-124">CLR non è stato in grado di completare la richiesta a causa di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="43686-124">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43686-125">Note</span><span class="sxs-lookup"><span data-stu-id="43686-125">Remarks</span></span>  
 <span data-ttu-id="43686-126">Chiamare `RequestReJIT` per ottenere la ricompilazione tramite il runtime di un set di funzioni specificato.</span><span class="sxs-lookup"><span data-stu-id="43686-126">Call `RequestReJIT` to have the runtime recompile a specified set of functions.</span></span> <span data-ttu-id="43686-127">Un code profiler può quindi utilizzare il [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfaccia per modificare il codice che viene generato quando vengono ricompilate le funzioni.</span><span class="sxs-lookup"><span data-stu-id="43686-127">A code profiler can then use the [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled.</span></span> <span data-ttu-id="43686-128">Questa operazione non influisce sulle funzioni attualmente in esecuzione, ma solo sulle chiamate di funzione future.</span><span class="sxs-lookup"><span data-stu-id="43686-128">This does not affect currently executing functions, only future function invocations.</span></span> <span data-ttu-id="43686-129">Se una delle funzioni specificate è stata precedentemente ricompilata tramite JIT, la richiesta di ricompilazione equivale al ripristino e alla ricompilazione della funzione.</span><span class="sxs-lookup"><span data-stu-id="43686-129">If any of the specified functions has previously been JIT-recompiled, requesting a recompilation is equivalent to reverting and recompiling the function.</span></span> <span data-ttu-id="43686-130">Per mantenere la reversibilità, quando il compilatore JIT compila la versione originale di una funzione, considera solo le versioni originali dei relativi chiamati per le decisioni di incorporamento (inlining).</span><span class="sxs-lookup"><span data-stu-id="43686-130">To preserve reversibility, when the JIT compiler compiles the original version of a function, it considers only the original versions of its callees for inlining decisions.</span></span> <span data-ttu-id="43686-131">Quando il compilatore JIT ricompila una funzione, considera le versioni correnti (ricompilate o originali) dei relativi chiamati per l'incorporamento.</span><span class="sxs-lookup"><span data-stu-id="43686-131">When the JIT compiler recompiles a function, it considers the current versions (recompiled or original) of its callees for inlining.</span></span>  
  
 <span data-ttu-id="43686-132">In genere, un profiler chiama `RequestReJIT` in risposta all'input dell'utente che richiede al profiler di instrumentare uno o più metodi.</span><span class="sxs-lookup"><span data-stu-id="43686-132">A profiler typically calls `RequestReJIT` in response to user input requesting that the profiler instrument one or more methods.</span></span> <span data-ttu-id="43686-133">`RequestReJIT` in genere sospende il runtime per eseguire le proprie attività e potrebbe attivare una Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="43686-133">`RequestReJIT` typically suspends the runtime in order to do some of its work, and can potentially trigger a garbage collection.</span></span> <span data-ttu-id="43686-134">Di conseguenza, il profiler dovrebbe chiamare `RequestReJIT` da un thread creato in precedenza e non da un thread creato da CLR che sta eseguendo un callback del profiler.</span><span class="sxs-lookup"><span data-stu-id="43686-134">As such, the profiler should call `RequestReJIT` from a thread it previously created, and not from a CLR-created thread that is currently executing a profiler callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43686-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43686-135">Requirements</span></span>  
 <span data-ttu-id="43686-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43686-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43686-137">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43686-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43686-138">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43686-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43686-139">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43686-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43686-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43686-140">See Also</span></span>  
 [<span data-ttu-id="43686-141">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="43686-141">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="43686-142">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="43686-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="43686-143">Profilatura</span><span class="sxs-lookup"><span data-stu-id="43686-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
