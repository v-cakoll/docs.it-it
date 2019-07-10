---
title: Metodo ICLRDebugging::OpenVirtualProcess
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c460bc644017f32fdb96d35e5f42981ac09f825
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738377"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="7f39f-102">Metodo ICLRDebugging::OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="7f39f-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="7f39f-103">Ottiene l'interfaccia ICorDebugProcess che corrisponde a un modulo common language runtime (CLR) caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="7f39f-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f39f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f39f-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f39f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f39f-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="7f39f-106">[in] L'indirizzo di base di un modulo nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f39f-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="7f39f-107">COR_E_NOT_CLR verrà restituito se il modulo specificato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="7f39f-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="7f39f-108">[in] Un'astrazione di destinazione dei dati che consente al debugger gestito controllare lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="7f39f-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="7f39f-109">Il debugger deve implementare il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7f39f-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="7f39f-110">È consigliabile implementare il [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia per supportare scenari in cui CLR in fase di debug non è installato localmente nel computer.</span><span class="sxs-lookup"><span data-stu-id="7f39f-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="7f39f-111">[in] Un'interfaccia di callback provider libreria che consente di individuare e caricare su richiesta librerie di debug specifiche della versione.</span><span class="sxs-lookup"><span data-stu-id="7f39f-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="7f39f-112">Questo parametro è obbligatorio solo se `ppProcess` oppure `pFlags` non è `null`.</span><span class="sxs-lookup"><span data-stu-id="7f39f-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="7f39f-113">[in] La versione più recente di Common Language Runtime che è possibile eseguire il debug questo debugger.</span><span class="sxs-lookup"><span data-stu-id="7f39f-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="7f39f-114">Si deve specificare il numero principale, secondario, compilare versioni dell'ultima versione di CLR che supporta e impostare il numero di revisione e 65535 per supportare Common Language Runtime sul posto di future Service Release.</span><span class="sxs-lookup"><span data-stu-id="7f39f-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="7f39f-115">[in] L'ID dell'interfaccia ICorDebugProcess da recuperare.</span><span class="sxs-lookup"><span data-stu-id="7f39f-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="7f39f-116">Attualmente, gli unici valori accettati sono IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 e IID_CORDEBUGPROCESS.</span><span class="sxs-lookup"><span data-stu-id="7f39f-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7f39f-117">[out] Un puntatore a interfaccia COM che è identificato da `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="7f39f-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="7f39f-118">[in, out] La versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="7f39f-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="7f39f-119">Per l'input, questo valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="7f39f-119">On input, this value can be `null`.</span></span> <span data-ttu-id="7f39f-120">Anche possibile puntare a un [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) struttura, nel qual caso la struttura `wStructVersion` campo deve essere inizializzato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="7f39f-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="7f39f-121">Nell'output restituito `CLR_DEBUGGING_VERSION` struttura verrà compilata con le informazioni sulla versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="7f39f-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="7f39f-122">[out] Flag informativo sul runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="7f39f-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="7f39f-123">Vedere le [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) argomento per una descrizione dei flag.</span><span class="sxs-lookup"><span data-stu-id="7f39f-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f39f-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7f39f-124">Return Value</span></span>  
 <span data-ttu-id="7f39f-125">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="7f39f-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7f39f-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f39f-126">HRESULT</span></span>|<span data-ttu-id="7f39f-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f39f-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f39f-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f39f-128">S_OK</span></span>|<span data-ttu-id="7f39f-129">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f39f-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="7f39f-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7f39f-130">E_POINTER</span></span>|<span data-ttu-id="7f39f-131">`pDataTarget` è `null`.</span><span class="sxs-lookup"><span data-stu-id="7f39f-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="7f39f-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="7f39f-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="7f39f-133">Il [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback restituisce un errore o non fornisce un handle valido.</span><span class="sxs-lookup"><span data-stu-id="7f39f-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="7f39f-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="7f39f-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="7f39f-135">`pDataTarget` non implementa le interfacce di destinazione i dati necessari per questa versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="7f39f-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="7f39f-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="7f39f-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="7f39f-137">Il modulo indicato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="7f39f-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="7f39f-138">Questo valore di HRESULT viene restituito anche quando un modulo CLR non può essere rilevato memoria è stata danneggiata, il modulo non è disponibile, oppure la versione di CLR successiva alla versione di shim.</span><span class="sxs-lookup"><span data-stu-id="7f39f-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="7f39f-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="7f39f-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="7f39f-140">Questa versione di runtime non supporta questo modello di debug.</span><span class="sxs-lookup"><span data-stu-id="7f39f-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="7f39f-141">Attualmente, il modello di debug non è supportato dalle versioni precedenti di Common Language Runtime di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7f39f-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="7f39f-142">Il `pwszVersion` parametro di output è ancora impostato sul valore corretto dopo questo errore.</span><span class="sxs-lookup"><span data-stu-id="7f39f-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="7f39f-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="7f39f-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="7f39f-144">La versione di CLR è maggiore della versione che questo debugger dichiara di supportare.</span><span class="sxs-lookup"><span data-stu-id="7f39f-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="7f39f-145">Il `pwszVersion` parametro di output è ancora impostato sul valore corretto dopo questo errore.</span><span class="sxs-lookup"><span data-stu-id="7f39f-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="7f39f-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="7f39f-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="7f39f-147">Il `riidProcess` interfaccia non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="7f39f-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="7f39f-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="7f39f-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="7f39f-149">Il `CLR_DEBUGGING_VERSION` struttura non dispone di un valore riconosciuto per `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="7f39f-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="7f39f-150">L'unico valore accettato in questa fase è 0.</span><span class="sxs-lookup"><span data-stu-id="7f39f-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7f39f-151">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="7f39f-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f39f-152">Note</span><span class="sxs-lookup"><span data-stu-id="7f39f-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f39f-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f39f-153">Requirements</span></span>  
 <span data-ttu-id="7f39f-154">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f39f-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f39f-155">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f39f-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f39f-156">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f39f-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f39f-157">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f39f-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f39f-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f39f-158">See also</span></span>

- [<span data-ttu-id="7f39f-159">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7f39f-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7f39f-160">Debug</span><span class="sxs-lookup"><span data-stu-id="7f39f-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
