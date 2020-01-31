---
title: Metodo ICorProfilerInfo4::RequestRevert
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestRevert
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestRevert
helpviewer_keywords:
- RequestRevert method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestRevert method [.NET Framework profiling]
ms.assetid: 70261da5-5933-4e25-9de0-ddf51cba56cc
topic_type:
- apiref
ms.openlocfilehash: 73d122b1ffa890bfa43f8eef7e24595ac0d26ebe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861788"
---
# <a name="icorprofilerinfo4requestrevert-method"></a><span data-ttu-id="ab8df-102">Metodo ICorProfilerInfo4::RequestRevert</span><span class="sxs-lookup"><span data-stu-id="ab8df-102">ICorProfilerInfo4::RequestRevert Method</span></span>
<span data-ttu-id="ab8df-103">Ripristina tutte le istanze delle funzioni specificate alle versioni originali.</span><span class="sxs-lookup"><span data-stu-id="ab8df-103">Reverts all instances of the specified functions to their original versions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab8df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab8df-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestRevert (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[],  
   [out, size_is(cFunctions)]  HRESULT status[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab8df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab8df-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="ab8df-106">[in] Numero delle funzioni da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="ab8df-106">[in] The number of functions to revert.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="ab8df-107">[in] Specifica la parte `moduleId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="ab8df-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="ab8df-108">[in] Specifica la parte `methodId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="ab8df-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `status`  
 <span data-ttu-id="ab8df-109">[out] Matrice di HRESULT riportati nella sezione "HRESULT di stato" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ab8df-109">[out] An array of HRESULTs listed in the "Status HRESULTs" section later in this topic.</span></span> <span data-ttu-id="ab8df-110">Ciascun HRESULT indica la riuscita o la mancata riuscita del ripristino di ogni funzione specificata nelle matrici `moduleIds` e `methodIds` parallele.</span><span class="sxs-lookup"><span data-stu-id="ab8df-110">Each HRESULT indicates the success or failure of trying to revert each function specified in the parallel arrays `moduleIds` and `methodIds`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab8df-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ab8df-111">Return Value</span></span>  
 <span data-ttu-id="ab8df-112">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ab8df-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ab8df-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab8df-113">HRESULT</span></span>|<span data-ttu-id="ab8df-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab8df-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab8df-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab8df-115">S_OK</span></span>|<span data-ttu-id="ab8df-116">È stato effettuato un tentativo di ripristinare tutte le richieste. Tuttavia, la matrice di stato restituito deve essere verificata per determinare quali funzioni sono state annullate correttamente.</span><span class="sxs-lookup"><span data-stu-id="ab8df-116">An attempt was made to revert all requests; however, the returned status array must be checked to determine which functions were successfully reverted.</span></span>|  
|<span data-ttu-id="ab8df-117">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="ab8df-117">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="ab8df-118">Il profiler deve implementare l'interfaccia [ICorProfilerCallback4](icorprofilercallback4-interface.md) per il supporto di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="ab8df-118">The profiler must implement the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="ab8df-119">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="ab8df-119">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="ab8df-120">La ricompilazione JIT non è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="ab8df-120">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="ab8df-121">È necessario abilitare la ricompilazione JIT durante l'inizializzazione usando il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare il flag di `COR_PRF_ENABLE_REJIT`.</span><span class="sxs-lookup"><span data-stu-id="ab8df-121">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="ab8df-122">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ab8df-122">E_INVALIDARG</span></span>|<span data-ttu-id="ab8df-123">Il parametro `cFunctions` è pari a 0 oppure `moduleIds` o `methodIds` è `NULL`.</span><span class="sxs-lookup"><span data-stu-id="ab8df-123">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|<span data-ttu-id="ab8df-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ab8df-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ab8df-125">CLR non è stato in grado di completare la richiesta a causa di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="ab8df-125">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="status-hresults"></a><span data-ttu-id="ab8df-126">HRESULT di stato</span><span class="sxs-lookup"><span data-stu-id="ab8df-126">Status HRESULTS</span></span>  
  
|<span data-ttu-id="ab8df-127">HRESULT matrice di stato</span><span class="sxs-lookup"><span data-stu-id="ab8df-127">Status array HRESULT</span></span>|<span data-ttu-id="ab8df-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab8df-128">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="ab8df-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab8df-129">S_OK</span></span>|<span data-ttu-id="ab8df-130">La funzione corrispondente è stata ripristinata.</span><span class="sxs-lookup"><span data-stu-id="ab8df-130">The corresponding function was successfully reverted.</span></span>|  
|<span data-ttu-id="ab8df-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ab8df-131">E_INVALIDARG</span></span>|<span data-ttu-id="ab8df-132">Il parametro `moduleID` o il parametro `methodDef` è `NULL`.</span><span class="sxs-lookup"><span data-stu-id="ab8df-132">The `moduleID` or `methodDef` parameter is `NULL`.</span></span>|  
|<span data-ttu-id="ab8df-133">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="ab8df-133">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="ab8df-134">Il modulo non è ancora completamente caricato o è in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="ab8df-134">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="ab8df-135">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="ab8df-135">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="ab8df-136">Il modulo specificato è stato generato dinamicamente (ad esempio da `Reflection.Emit`).</span><span class="sxs-lookup"><span data-stu-id="ab8df-136">The specified module was dynamically generated (for example by `Reflection.Emit`).</span></span> <span data-ttu-id="ab8df-137">Di conseguenza, non è supportato da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ab8df-137">Therefore, it is not supported by this method.</span></span>|  
|<span data-ttu-id="ab8df-138">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="ab8df-138">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span></span>|<span data-ttu-id="ab8df-139">CLR non può ripristinare la funzione specificata, perché non è stata trovata una richiesta di ricompilazione attiva corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ab8df-139">The CLR could not revert the specified function, because a corresponding active recompilation request was not found.</span></span> <span data-ttu-id="ab8df-140">La ricompilazione non è stata mai richiesta oppure la funzione era già stata ripristinata.</span><span class="sxs-lookup"><span data-stu-id="ab8df-140">Either the recompilation was never requested or the function was already reverted.</span></span>|  
|<span data-ttu-id="ab8df-141">Altro</span><span class="sxs-lookup"><span data-stu-id="ab8df-141">Other</span></span>|<span data-ttu-id="ab8df-142">Il sistema operativo ha restituito un errore esterno al controllo di CLR.</span><span class="sxs-lookup"><span data-stu-id="ab8df-142">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="ab8df-143">Ad esempio, se una chiamata al sistema per modificare la sicurezza di accesso di una pagina di memoria non riesce, viene visualizzato un errore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ab8df-143">For example, if a system call to change the access protection of a page of memory fails, the operating system error will be displayed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab8df-144">Note</span><span class="sxs-lookup"><span data-stu-id="ab8df-144">Remarks</span></span>  
 <span data-ttu-id="ab8df-145">La volta successiva che verranno chiamate tutte le istanze di funzione ripristinate, verranno eseguite le versioni originali delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="ab8df-145">The next time any of the revereted function instances are called, the original versions of the functions will be run.</span></span> <span data-ttu-id="ab8df-146">Se una funzione è già in esecuzione, verrà terminata l'esecuzione della versione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ab8df-146">If a function is already running, it will finish executing the version that is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab8df-147">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ab8df-147">Requirements</span></span>  
 <span data-ttu-id="ab8df-148">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab8df-148">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab8df-149">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab8df-149">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab8df-150">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab8df-150">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab8df-151">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab8df-151">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab8df-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab8df-152">See also</span></span>

- [<span data-ttu-id="ab8df-153">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="ab8df-153">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="ab8df-154">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="ab8df-154">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ab8df-155">Profilatura</span><span class="sxs-lookup"><span data-stu-id="ab8df-155">Profiling</span></span>](index.md)
