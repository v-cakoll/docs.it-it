---
title: Metodo ICLRDebugging::OpenVirtualProcess
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f1f71f42f10c3d25714998d1697b20a5ee13e055
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="63fdf-102">Metodo ICLRDebugging::OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="63fdf-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="63fdf-103">Ottiene l'interfaccia ICorDebugProcess che corrisponde a un modulo common language runtime (CLR) caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="63fdf-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63fdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63fdf-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="63fdf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63fdf-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="63fdf-106">[in] L'indirizzo di base di un modulo nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="63fdf-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="63fdf-107">COR_E_NOT_CLR verrà restituito se il modulo specificato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="63fdf-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="63fdf-108">[in] Un'astrazione di destinazione dei dati che consente al debugger gestito controllare lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="63fdf-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="63fdf-109">Il debugger deve implementare il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="63fdf-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="63fdf-110">È necessario implementare la [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia per supportare scenari in cui il runtime che viene eseguito il debug non è installato localmente nel computer.</span><span class="sxs-lookup"><span data-stu-id="63fdf-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="63fdf-111">[in] Un'interfaccia di callback provider libreria che consente di individuare e caricare su richiesta librerie di debug specifiche della versione.</span><span class="sxs-lookup"><span data-stu-id="63fdf-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="63fdf-112">Questo parametro è obbligatorio solo se `ppProcess` o `pFlags` non `null`.</span><span class="sxs-lookup"><span data-stu-id="63fdf-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="63fdf-113">[in] La versione più recente di questo debugger può eseguire il debug CLR.</span><span class="sxs-lookup"><span data-stu-id="63fdf-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="63fdf-114">Si deve specificare la versione principale e secondario, compilare versioni dell'ultima versione di CLR che supporta e impostare il numero di revisione e 65535 per supportare Common Language Runtime sul posto di future Service Release.</span><span class="sxs-lookup"><span data-stu-id="63fdf-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="63fdf-115">[in] ID dell'interfaccia ICorDebugProcess da recuperare.</span><span class="sxs-lookup"><span data-stu-id="63fdf-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="63fdf-116">Attualmente, i valori accettati sono solo IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 e IID_CORDEBUGPROCESS.</span><span class="sxs-lookup"><span data-stu-id="63fdf-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="63fdf-117">[out] Un puntatore a interfaccia COM che è identificato da `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="63fdf-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="63fdf-118">[in, out] La versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="63fdf-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="63fdf-119">Per l'input, questo valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="63fdf-119">On input, this value can be `null`.</span></span> <span data-ttu-id="63fdf-120">Può inoltre puntare a un [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) struttura, nel qual caso la struttura `wStructVersion` campo deve essere inizializzato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="63fdf-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="63fdf-121">Nell'output, l'oggetto restituito `CLR_DEBUGGING_VERSION` struttura verrà compilata con le informazioni sulla versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="63fdf-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="63fdf-122">[out] Contrassegni informativi sul runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="63fdf-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="63fdf-123">Vedere il [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) argomento per una descrizione dei flag.</span><span class="sxs-lookup"><span data-stu-id="63fdf-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63fdf-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="63fdf-124">Return Value</span></span>  
 <span data-ttu-id="63fdf-125">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="63fdf-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="63fdf-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63fdf-126">HRESULT</span></span>|<span data-ttu-id="63fdf-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63fdf-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63fdf-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="63fdf-128">S_OK</span></span>|<span data-ttu-id="63fdf-129">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="63fdf-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="63fdf-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="63fdf-130">E_POINTER</span></span>|<span data-ttu-id="63fdf-131">`pDataTarget` è `null`.</span><span class="sxs-lookup"><span data-stu-id="63fdf-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="63fdf-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="63fdf-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="63fdf-133">Il [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback restituisce un errore o non fornisce un handle valido.</span><span class="sxs-lookup"><span data-stu-id="63fdf-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="63fdf-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="63fdf-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="63fdf-135">`pDataTarget`non implementa le interfacce di destinazione di dati necessari per questa versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="63fdf-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="63fdf-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="63fdf-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="63fdf-137">Il modulo indicato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="63fdf-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="63fdf-138">Questo valore di HRESULT viene restituito anche quando un modulo CLR non può essere rilevato perché la memoria è stata danneggiata, il modulo non è disponibile o la versione CLR è successiva alla versione di shim.</span><span class="sxs-lookup"><span data-stu-id="63fdf-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="63fdf-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="63fdf-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="63fdf-140">Questa versione di runtime non supporta il modello di debug.</span><span class="sxs-lookup"><span data-stu-id="63fdf-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="63fdf-141">Attualmente, il modello di debug non è supportato dalle versioni precedenti CLR il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63fdf-141">Currently, the debugging model is not supported by CLR versions before the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="63fdf-142">Il `pwszVersion` parametro di output è ancora impostato sul valore corretto dopo questo errore.</span><span class="sxs-lookup"><span data-stu-id="63fdf-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="63fdf-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="63fdf-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="63fdf-144">La versione di CLR è maggiore della versione che per il supporto di attestazioni questo debugger.</span><span class="sxs-lookup"><span data-stu-id="63fdf-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="63fdf-145">Il `pwszVersion` parametro di output è ancora impostato sul valore corretto dopo questo errore.</span><span class="sxs-lookup"><span data-stu-id="63fdf-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="63fdf-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="63fdf-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="63fdf-147">Il `riidProcess` interfaccia non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="63fdf-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="63fdf-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="63fdf-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="63fdf-149">Il `CLR_DEBUGGING_VERSION` struttura non dispone di un valore riconosciuto per `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="63fdf-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="63fdf-150">L'unico valore ammesso in questa fase è 0.</span><span class="sxs-lookup"><span data-stu-id="63fdf-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="63fdf-151">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="63fdf-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63fdf-152">Note</span><span class="sxs-lookup"><span data-stu-id="63fdf-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63fdf-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63fdf-153">Requirements</span></span>  
 <span data-ttu-id="63fdf-154">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63fdf-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63fdf-155">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="63fdf-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63fdf-156">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63fdf-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63fdf-157">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63fdf-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fdf-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63fdf-158">See Also</span></span>  
 [<span data-ttu-id="63fdf-159">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="63fdf-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="63fdf-160">Debug</span><span class="sxs-lookup"><span data-stu-id="63fdf-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
