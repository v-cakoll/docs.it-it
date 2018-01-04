---
title: Metodo ICorProfilerCallback4::ReJITError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITError
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c746d0f7a6be96f95f1a051e22de0ad1bd2d2269
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="f940c-102">Metodo ICorProfilerCallback4::ReJITError</span><span class="sxs-lookup"><span data-stu-id="f940c-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="f940c-103">Notifica al profiler che il compilatore di just-in-time (JIT) ha rilevato un errore nel processo di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="f940c-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f940c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f940c-104">Syntax</span></span>  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f940c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f940c-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="f940c-106">[in] Il `ModuleID` in cui è stato effettuato il tentativo di ricompilazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="f940c-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="f940c-107">[in] Il `MethodDef` del metodo in cui è stato effettuato il tentativo di ricompilazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="f940c-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="f940c-108">[in] L'istanza della funzione che viene ricompilata o contrassegnata per la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="f940c-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="f940c-109">Questo valore può essere `NULL` se l'errore si è verificato in una base di ciascun metodo anziché una base per istanza (ad esempio, se il profiler ha specificato un token di metadati non validi per il metodo per la ricompilazione).</span><span class="sxs-lookup"><span data-stu-id="f940c-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="f940c-110">[in] Un valore HRESULT che indica la natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="f940c-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="f940c-111">Vedere la sezione HRESULT di stato per un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="f940c-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f940c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f940c-112">Return Value</span></span>  
 <span data-ttu-id="f940c-113">I valori restituiti da questo callback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="f940c-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="f940c-114">HRESULT di stato</span><span class="sxs-lookup"><span data-stu-id="f940c-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="f940c-115">HRESULT matrice di stato</span><span class="sxs-lookup"><span data-stu-id="f940c-115">Status array HRESULT</span></span>|<span data-ttu-id="f940c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f940c-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="f940c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f940c-117">E_INVALIDARG</span></span>|<span data-ttu-id="f940c-118">Il `moduleID` o `methodDef` token è `NULL`.</span><span class="sxs-lookup"><span data-stu-id="f940c-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="f940c-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="f940c-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="f940c-120">Il modulo non è ancora completamente caricato o è in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="f940c-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="f940c-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="f940c-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="f940c-122">Il modulo specificato è stato generato dinamicamente (ad esempio, da `Reflection.Emit`) e pertanto non è supportato da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="f940c-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="f940c-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="f940c-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="f940c-124">Il metodo viene creata un'istanza in un assembly ritirabile e pertanto non è in grado di essere ricompilata.</span><span class="sxs-lookup"><span data-stu-id="f940c-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="f940c-125">Si noti che i tipi e funzioni definite in un contesto di reflection non (ad esempio, `List<MyCollectibleStruct>`) può essere creata un'istanza in un assembly ritirabile.</span><span class="sxs-lookup"><span data-stu-id="f940c-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="f940c-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f940c-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f940c-127">CLR ha esaurito la memoria durante il tentativo di contrassegnare il metodo specificato per la ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="f940c-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="f940c-128">Altro</span><span class="sxs-lookup"><span data-stu-id="f940c-128">Other</span></span>|<span data-ttu-id="f940c-129">Il sistema operativo ha restituito un errore esterno al controllo di CLR.</span><span class="sxs-lookup"><span data-stu-id="f940c-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="f940c-130">Ad esempio, se una chiamata di sistema per modificare la protezione di accesso di una pagina di memoria non riesce, viene visualizzato l'errore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f940c-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f940c-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f940c-131">Requirements</span></span>  
 <span data-ttu-id="f940c-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f940c-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f940c-133">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f940c-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f940c-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f940c-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f940c-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f940c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f940c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f940c-136">See Also</span></span>  
 [<span data-ttu-id="f940c-137">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f940c-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f940c-138">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="f940c-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
