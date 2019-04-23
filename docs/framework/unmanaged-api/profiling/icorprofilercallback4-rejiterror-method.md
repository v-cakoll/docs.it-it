---
title: Metodo ICorProfilerCallback4::ReJITError
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f152279a21f28b54acebbf0be7c65bb73efa70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150592"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="0d8ca-102">Metodo ICorProfilerCallback4::ReJITError</span><span class="sxs-lookup"><span data-stu-id="0d8ca-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="0d8ca-103">Notifica al profiler che il compilatore di just-in-time (JIT) ha rilevato un errore nel processo di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d8ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d8ca-104">Syntax</span></span>  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d8ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d8ca-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="0d8ca-106">[in] Il `ModuleID` in cui è stato effettuato il tentativo di ricompilazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="0d8ca-107">[in] Il `MethodDef` del metodo in cui è stato effettuato il tentativo di ricompilazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="0d8ca-108">[in] L'istanza della funzione che verrà ricompilata o contrassegnata per la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="0d8ca-109">Questo valore può essere `NULL` se l'errore si è verificato su una base di ciascun metodo invece di base per istanza (ad esempio, se il profiler specificato un token di metadati non validi per il metodo di ricompilazione).</span><span class="sxs-lookup"><span data-stu-id="0d8ca-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="0d8ca-110">[in] HRESULT che indica la natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="0d8ca-111">Vedere la sezione di HRESULT di stato per un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d8ca-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0d8ca-112">Return Value</span></span>  
 <span data-ttu-id="0d8ca-113">I valori restituiti da questo callback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="0d8ca-114">HRESULT di stato</span><span class="sxs-lookup"><span data-stu-id="0d8ca-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="0d8ca-115">HRESULT matrice di stato</span><span class="sxs-lookup"><span data-stu-id="0d8ca-115">Status array HRESULT</span></span>|<span data-ttu-id="0d8ca-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d8ca-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="0d8ca-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0d8ca-117">E_INVALIDARG</span></span>|<span data-ttu-id="0d8ca-118">Il `moduleID` oppure `methodDef` token è `NULL`.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="0d8ca-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="0d8ca-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="0d8ca-120">Il modulo non è ancora completamente caricato o è in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="0d8ca-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="0d8ca-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="0d8ca-122">Il modulo specificato è stato generato dinamicamente (ad esempio, da `Reflection.Emit`) e pertanto non è supportato da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="0d8ca-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="0d8ca-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="0d8ca-124">Il metodo viene creata un'istanza in un assembly ritirabile e pertanto non può essere ricompilato.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="0d8ca-125">Si noti che i tipi e funzioni definite in un contesto non di reflection (ad esempio, `List<MyCollectibleStruct>`) è possibile creare istanze in un assembly ritirabile.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="0d8ca-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0d8ca-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0d8ca-127">Il CLR ha esaurito la memoria durante il tentativo di contrassegnare il metodo specificato per la ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="0d8ca-128">Altro</span><span class="sxs-lookup"><span data-stu-id="0d8ca-128">Other</span></span>|<span data-ttu-id="0d8ca-129">Il sistema operativo ha restituito un errore esterno al controllo di CLR.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="0d8ca-130">Ad esempio, se una chiamata di sistema per modificare la protezione di accesso di una pagina di memoria ha esito negativo, viene visualizzato l'errore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0d8ca-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d8ca-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d8ca-131">Requirements</span></span>  
 <span data-ttu-id="0d8ca-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d8ca-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d8ca-133">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d8ca-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0d8ca-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d8ca-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d8ca-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d8ca-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8ca-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d8ca-136">See also</span></span>

- [<span data-ttu-id="0d8ca-137">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0d8ca-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0d8ca-138">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="0d8ca-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
