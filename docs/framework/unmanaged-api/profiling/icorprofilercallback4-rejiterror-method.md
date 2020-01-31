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
ms.openlocfilehash: 66195ea9df4c8e9ce847b38f7d020a3bebffcd37
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865181"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="0c1dd-102">Metodo ICorProfilerCallback4::ReJITError</span><span class="sxs-lookup"><span data-stu-id="0c1dd-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="0c1dd-103">Notifica al profiler che il compilatore JIT (just-in-Time) ha rilevato un errore nel processo di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c1dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c1dd-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c1dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c1dd-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="0c1dd-106">in `ModuleID` in cui è stato effettuato il tentativo di ricompilazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="0c1dd-107">in `MethodDef` del metodo in cui è stato effettuato il tentativo di ricompilazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="0c1dd-108">in Istanza della funzione che viene ricompilata o contrassegnata per la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="0c1dd-109">Questo valore può essere `NULL` se l'errore si è verificato per singolo metodo anziché per ogni singola istanza, ad esempio se il profiler ha specificato un token di metadati non valido per il metodo da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="0c1dd-110">in HRESULT che indica la natura dell'errore.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="0c1dd-111">Per un elenco di valori, vedere la sezione stato HRESULTs.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c1dd-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c1dd-112">Return Value</span></span>  
 <span data-ttu-id="0c1dd-113">I valori restituiti da questo callback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="0c1dd-114">HRESULT di stato</span><span class="sxs-lookup"><span data-stu-id="0c1dd-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="0c1dd-115">HRESULT matrice di stato</span><span class="sxs-lookup"><span data-stu-id="0c1dd-115">Status array HRESULT</span></span>|<span data-ttu-id="0c1dd-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c1dd-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="0c1dd-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0c1dd-117">E_INVALIDARG</span></span>|<span data-ttu-id="0c1dd-118">Il token `moduleID` o `methodDef` è `NULL`.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="0c1dd-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="0c1dd-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="0c1dd-120">Il modulo non è ancora completamente caricato o è in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="0c1dd-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="0c1dd-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="0c1dd-122">Il modulo specificato è stato generato dinamicamente (ad esempio, da `Reflection.Emit`) e pertanto non è supportato da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="0c1dd-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="0c1dd-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="0c1dd-124">Viene creata un'istanza del metodo in un assembly ritirabile e pertanto non può essere ricompilata.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="0c1dd-125">Si noti che è possibile creare un'istanza di tipi e funzioni definiti in un contesto non di reflection, ad esempio `List<MyCollectibleStruct>`, in un assembly ritirabile.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="0c1dd-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0c1dd-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0c1dd-127">Memoria insufficiente per CLR durante il tentativo di contrassegnare il metodo specificato per la ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="0c1dd-128">Altro</span><span class="sxs-lookup"><span data-stu-id="0c1dd-128">Other</span></span>|<span data-ttu-id="0c1dd-129">Il sistema operativo ha restituito un errore esterno al controllo di CLR.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="0c1dd-130">Se, ad esempio, una chiamata di sistema per modificare la protezione dell'accesso di una pagina di memoria non riesce, viene visualizzato l'errore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0c1dd-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c1dd-131">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0c1dd-131">Requirements</span></span>  
 <span data-ttu-id="0c1dd-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c1dd-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c1dd-133">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c1dd-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c1dd-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c1dd-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c1dd-135">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c1dd-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1dd-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c1dd-136">See also</span></span>

- [<span data-ttu-id="0c1dd-137">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0c1dd-137">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0c1dd-138">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="0c1dd-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
