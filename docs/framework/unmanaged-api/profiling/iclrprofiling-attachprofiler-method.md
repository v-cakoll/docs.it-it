---
title: Metodo ICLRProfiling::AttachProfiler
ms.date: 03/30/2017
api_name:
- IClrProfiling.AttachProfiler Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- IClrProfiling::AttachProfiler
helpviewer_keywords:
- AttachProfiler method [.NET Framework profiling]
- IClrProfiling::AttachProfiler method [.NET Framework profiling]
ms.assetid: 535a6839-c443-405b-a6f4-e2af90725d5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e3898fb836409df3b685d985d0d72ab63230a93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174174"
---
# <a name="iclrprofilingattachprofiler-method"></a><span data-ttu-id="d8d2a-102">Metodo ICLRProfiling::AttachProfiler</span><span class="sxs-lookup"><span data-stu-id="d8d2a-102">ICLRProfiling::AttachProfiler Method</span></span>
<span data-ttu-id="d8d2a-103">Connette il profiler specificato al processo specificato.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-103">Attaches the specified profiler to the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8d2a-104">Syntax</span></span>  
  
```  
HRESULT AttachProfiler(  
  [in] DWORD dwProfileeProcessID,  
  [in] DWORD dwMillisecondsMax,                     // optional  
  [in] const CLSID * pClsidProfiler,  
  [in] LPCWSTR wszProfilerPath,                     // optional  
  [in] size_is(cbClientData)] void * pvClientData,  // optional  
  [in] UINT cbClientData);                          // optional  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8d2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8d2a-105">Parameters</span></span>  
 `dwProfileeProcessID`  
 <span data-ttu-id="d8d2a-106">[in] ID del processo a cui connettere il profiler.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-106">[in] The process ID of the process to which the profiler should be attached.</span></span> <span data-ttu-id="d8d2a-107">In un computer a 64 bit, il numero di bit del processo profilato deve corrispondere a quello del processo trigger che chiama `AttachProfiler`.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-107">On a 64-bit machine, the profiled process's bitness must match the bitness of the trigger process that is calling `AttachProfiler`.</span></span> <span data-ttu-id="d8d2a-108">Se l'account utente in cui viene chiamato `AttachProfiler` dispone di privilegi amministrativi, il processo di destinazione può essere qualsiasi processo nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-108">If the user account under which `AttachProfiler` is called has administrative privileges, the target process may be any process on the system.</span></span> <span data-ttu-id="d8d2a-109">In caso contrario, il processo di destinazione deve essere di proprietà dello stesso account utente.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-109">Otherwise, the target process must be owned by the same user account.</span></span>  
  
 `dwMillisecondsMax`  
 <span data-ttu-id="d8d2a-110">[in] Intervallo di tempo, in millisecondi, richiesto per il completamento di `AttachProfiler`.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-110">[in] The time duration, in milliseconds, for `AttachProfiler` to complete.</span></span> <span data-ttu-id="d8d2a-111">Il processo trigger deve passare un timeout sufficiente a garantire l'effettivo completamento dell'inizializzazione del profiler specifico.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-111">The trigger process should pass a timeout that is known to be sufficient for the particular profiler to complete its initialization.</span></span>  
  
 `pClsidProfiler`  
 <span data-ttu-id="d8d2a-112">[in] Puntatore al CLSID del profiler da caricare.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-112">[in] A pointer to the CLSID of the profiler to be loaded.</span></span> <span data-ttu-id="d8d2a-113">Il processo trigger può riutilizzare questa memoria dopo che `AttachProfiler` restituisce un risultato.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-113">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span>  
  
 `wszProfilerPath`  
 <span data-ttu-id="d8d2a-114">[in] Percorso completo del file DLL del profiler da caricare.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-114">[in] The full path to the profiler’s DLL file to be loaded.</span></span> <span data-ttu-id="d8d2a-115">Questa stringa deve contenere al massimo 260 caratteri, compreso il terminatore null.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-115">This string should contain no more than 260 characters, including the null terminator.</span></span> <span data-ttu-id="d8d2a-116">Se `wszProfilerPath` è null o una stringa vuota, Common Language Runtime (CLR) tenterà di determinare il percorso del file DLL del profiler cercando nel Registro di sistema il CLSID a cui `pClsidProfiler` punta.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-116">If `wszProfilerPath` is null or an empty string, the common language runtime (CLR) will try to find the location of the profiler’s DLL file by looking in the registry for the CLSID that `pClsidProfiler` points to.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="d8d2a-117">[in] Un puntatore ai dati da passare al profiler tramite la [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d8d2a-117">[in] A pointer to data to be passed to the profiler by the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method.</span></span> <span data-ttu-id="d8d2a-118">Il processo trigger può riutilizzare questa memoria dopo che `AttachProfiler` restituisce un risultato.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-118">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span> <span data-ttu-id="d8d2a-119">Se `pvClientData` è null, `cbClientData` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="d8d2a-119">If `pvClientData` is null, `cbClientData` must be 0 (zero).</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="d8d2a-120">[in] Dimensioni in byte dei dati a cui `pvClientData` punta.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-120">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8d2a-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d8d2a-121">Return Value</span></span>  
 <span data-ttu-id="d8d2a-122">Questo metodo restituisce gli HRESULT seguenti.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-122">This method returns the following HRESULTs.</span></span>  
  
|<span data-ttu-id="d8d2a-123">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8d2a-123">HRESULT</span></span>|<span data-ttu-id="d8d2a-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8d2a-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8d2a-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8d2a-125">S_OK</span></span>|<span data-ttu-id="d8d2a-126">Il profiler specificato è stato connesso correttamente al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-126">The specified profiler has successfully attached to the target process.</span></span>|  
|<span data-ttu-id="d8d2a-127">CORPROF_E_PROFILER_ALREADY_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="d8d2a-127">CORPROF_E_PROFILER_ALREADY_ACTIVE</span></span>|<span data-ttu-id="d8d2a-128">È già presente un profiler attivo o connesso al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-128">There is already a profiler active or attaching to the target process.</span></span>|  
|<span data-ttu-id="d8d2a-129">CORPROF_E_PROFILER_NOT_ATTACHABLE</span><span class="sxs-lookup"><span data-stu-id="d8d2a-129">CORPROF_E_PROFILER_NOT_ATTACHABLE</span></span>|<span data-ttu-id="d8d2a-130">Il profiler specificato non supporta la connessione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-130">The specified profiler does not support attachment.</span></span> <span data-ttu-id="d8d2a-131">Il processo trigger può tentare di connettere un profiler diverso.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-131">The trigger process may attempt to attach a different profiler.</span></span>|  
|<span data-ttu-id="d8d2a-132">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span><span class="sxs-lookup"><span data-stu-id="d8d2a-132">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span></span>|<span data-ttu-id="d8d2a-133">Non è stato possibile richiedere una connessione del profiler poiché la versione del processo di destinazione è incompatibile con il processo corrente che chiama `AttachProfiler`.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-133">Unable to request a profiler attachment, because the version of the target process is incompatible with the current process that is calling `AttachProfiler`.</span></span>|  
|<span data-ttu-id="d8d2a-134">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span><span class="sxs-lookup"><span data-stu-id="d8d2a-134">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span></span>|<span data-ttu-id="d8d2a-135">L'utente del processo trigger non ha accesso al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-135">The user of the trigger process does not have access to the target process.</span></span>|  
|<span data-ttu-id="d8d2a-136">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span><span class="sxs-lookup"><span data-stu-id="d8d2a-136">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span></span>|<span data-ttu-id="d8d2a-137">L'utente del processo trigger non dispone dei privilegi necessari a connettere un profiler al processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-137">The user of the trigger process does not have the privileges necessary to attach a profiler to the given target process.</span></span> <span data-ttu-id="d8d2a-138">Il log eventi dell'applicazione può contenere altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-138">The application event log may contain more information.</span></span>|  
|<span data-ttu-id="d8d2a-139">CORPROF_E_IPC_FAILED</span><span class="sxs-lookup"><span data-stu-id="d8d2a-139">CORPROF_E_IPC_FAILED</span></span>|<span data-ttu-id="d8d2a-140">Si è verificato un errore durante la comunicazione con il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-140">A failure occurred when communicating with the target process.</span></span> <span data-ttu-id="d8d2a-141">In genere questo errore si verifica se il processo di destinazione è in fase di chiusura.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-141">This commonly happens if the target process was shutting down.</span></span>|  
|<span data-ttu-id="d8d2a-142">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="d8d2a-142">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span></span>|<span data-ttu-id="d8d2a-143">Il processo di destinazione non esiste o non restituisce un runtime che supporti la connessione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-143">The target process does not exist or is not running a CLR that supports attachment.</span></span> <span data-ttu-id="d8d2a-144">Ciò può indicare che il runtime è stato scaricato dopo la chiamata al metodo di enumerazione dei runtime.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-144">This may indicate that the CLR was unloaded since the call to the runtime enumeration method.</span></span>|  
|<span data-ttu-id="d8d2a-145">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span><span class="sxs-lookup"><span data-stu-id="d8d2a-145">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span></span>|<span data-ttu-id="d8d2a-146">Si è verificato il timeout prima dell'inizio del caricamento del profiler.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-146">The timeout expired without beginning to load the profiler.</span></span> <span data-ttu-id="d8d2a-147">È possibile ritentare l'operazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-147">You can retry the attach operation.</span></span> <span data-ttu-id="d8d2a-148">I timeout si verificano quando un finalizzatore nel processo di destinazione viene eseguito per un tempo maggiore del valore di timeout.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-148">Timeouts occur when a finalizer in the target process runs for a longer time than the timeout value.</span></span>|  
|<span data-ttu-id="d8d2a-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d8d2a-149">E_INVALIDARG</span></span>|<span data-ttu-id="d8d2a-150">Uno o più parametri presentano valori non validi.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-150">One or more parameters have invalid values.</span></span>|  
|<span data-ttu-id="d8d2a-151">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8d2a-151">E_FAIL</span></span>|<span data-ttu-id="d8d2a-152">Si è verificato un errore non specificato di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-152">Some other, unspecified failure occurred.</span></span>|  
|<span data-ttu-id="d8d2a-153">Altri codici di errore</span><span class="sxs-lookup"><span data-stu-id="d8d2a-153">Other error codes</span></span>|<span data-ttu-id="d8d2a-154">Se il profiler [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) metodo restituisce un HRESULT che indica un errore, `AttachProfiler` restituisce lo stesso HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-154">If the profiler’s [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method returns an HRESULT that indicates failure, `AttachProfiler` returns that same HRESULT.</span></span> <span data-ttu-id="d8d2a-155">In questo caso, E_NOTIMPL viene convertito in CORPROF_E_PROFILER_NOT_ATTACHABLE.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-155">In this case, E_NOTIMPL is converted to CORPROF_E_PROFILER_NOT_ATTACHABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8d2a-156">Note</span><span class="sxs-lookup"><span data-stu-id="d8d2a-156">Remarks</span></span>  
  
## <a name="memory-management"></a><span data-ttu-id="d8d2a-157">Gestione della memoria</span><span class="sxs-lookup"><span data-stu-id="d8d2a-157">Memory Management</span></span>  
 <span data-ttu-id="d8d2a-158">In conformità alle convenzioni COM, il chiamante di `AttachProfiler` (ad esempio, il codice del trigger creato dallo sviluppatore del profiler) è responsabile dell'allocazione e della deallocazione della memoria dei dati a cui punta il parametro `pvClientData`.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-158">In keeping with COM conventions, the caller of `AttachProfiler` (for example, the trigger code authored by the profiler developer) is responsible for allocating and de-allocating the memory for the data that the `pvClientData` parameter points to.</span></span> <span data-ttu-id="d8d2a-159">Quando CLR esegue la chiamata a `AttachProfiler` fa una copia della memoria a cui `pvClientData` punta e la trasmette al processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-159">When the CLR executes the `AttachProfiler` call, it makes a copy of the memory that `pvClientData` points to and transmits it to the target process.</span></span> <span data-ttu-id="d8d2a-160">Quando il runtime CLR nel processo di destinazione riceve la propria copia del blocco `pvClientData` lo passa al profiler tramite il metodo `InitializeForAttach`, quindi dealloca la propria copia del blocco `pvClientData` dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d8d2a-160">When the CLR inside the target process receives its own copy of the `pvClientData` block, it passes the block to the profiler through the `InitializeForAttach` method, and then deallocates its copy of the `pvClientData` block from the target process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d2a-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8d2a-161">Requirements</span></span>  
 <span data-ttu-id="d8d2a-162">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d2a-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d2a-163">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8d2a-163">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8d2a-164">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8d2a-164">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d8d2a-165">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d8d2a-165">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8d2a-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8d2a-166">See also</span></span>

- [<span data-ttu-id="d8d2a-167">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d8d2a-167">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d8d2a-168">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="d8d2a-168">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="d8d2a-169">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="d8d2a-169">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d8d2a-170">Profilatura</span><span class="sxs-lookup"><span data-stu-id="d8d2a-170">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
