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
ms.openlocfilehash: 585b3d605d0df9169c12ca10198846ec0a7fe6d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793615"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="d6a31-102">Metodo ICLRDebugging::OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="d6a31-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="d6a31-103">Ottiene l'interfaccia ICorDebugProcess che corrisponde a un modulo Common Language Runtime (CLR) caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="d6a31-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6a31-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d6a31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6a31-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="d6a31-106">in Indirizzo di base di un modulo nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d6a31-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="d6a31-107">Se il modulo specificato non è un modulo CLR, verrà restituito COR_E_NOT_CLR.</span><span class="sxs-lookup"><span data-stu-id="d6a31-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="d6a31-108">in Astrazione di destinazione dati che consente al debugger gestito di ispezionare lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="d6a31-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="d6a31-109">Il debugger deve implementare l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d6a31-109">The debugger must implement the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="d6a31-110">È necessario implementare l'interfaccia [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) per supportare scenari in cui il CLR di cui è in corso il debug non è installato localmente nel computer.</span><span class="sxs-lookup"><span data-stu-id="d6a31-110">You should implement the [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="d6a31-111">in Interfaccia di callback del provider di librerie che consente di posizionare e caricare su richiesta librerie di debug specifiche della versione.</span><span class="sxs-lookup"><span data-stu-id="d6a31-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="d6a31-112">Questo parametro è obbligatorio solo se `ppProcess` o `pFlags` non è `null`.</span><span class="sxs-lookup"><span data-stu-id="d6a31-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="d6a31-113">in Versione più recente di CLR di cui questo debugger è in grado di eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="d6a31-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="d6a31-114">È necessario specificare le versioni principale, secondaria e di build dalla versione CLR più recente supportata da questo debugger, quindi impostare il numero di revisione su 65535 per supportare le future versioni di manutenzione CLR sul posto.</span><span class="sxs-lookup"><span data-stu-id="d6a31-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="d6a31-115">in ID dell'interfaccia ICorDebugProcess da recuperare.</span><span class="sxs-lookup"><span data-stu-id="d6a31-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="d6a31-116">Attualmente, gli unici valori accettati sono IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 e IID_CORDEBUGPROCESS.</span><span class="sxs-lookup"><span data-stu-id="d6a31-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="d6a31-117">out Puntatore all'interfaccia COM identificata da `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="d6a31-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="d6a31-118">[in, out] Versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="d6a31-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="d6a31-119">In input, questo valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="d6a31-119">On input, this value can be `null`.</span></span> <span data-ttu-id="d6a31-120">Può anche puntare a una struttura di [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) , nel qual caso il campo `wStructVersion` della struttura deve essere inizializzato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="d6a31-120">It can also point to a [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="d6a31-121">Nell'output, la struttura di `CLR_DEBUGGING_VERSION` restituita verrà compilata con le informazioni sulla versione per CLR.</span><span class="sxs-lookup"><span data-stu-id="d6a31-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="d6a31-122">out Flag informativi sul runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="d6a31-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="d6a31-123">Per una descrizione dei flag, vedere l'argomento [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d6a31-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6a31-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d6a31-124">Return Value</span></span>  
 <span data-ttu-id="d6a31-125">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="d6a31-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d6a31-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6a31-126">HRESULT</span></span>|<span data-ttu-id="d6a31-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6a31-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d6a31-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6a31-128">S_OK</span></span>|<span data-ttu-id="d6a31-129">Il metodo è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d6a31-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="d6a31-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d6a31-130">E_POINTER</span></span>|<span data-ttu-id="d6a31-131">`pDataTarget` è `null`.</span><span class="sxs-lookup"><span data-stu-id="d6a31-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="d6a31-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="d6a31-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="d6a31-133">Il callback [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) restituisce un errore o non fornisce un handle valido.</span><span class="sxs-lookup"><span data-stu-id="d6a31-133">The [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="d6a31-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="d6a31-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="d6a31-135">`pDataTarget` non implementa le interfacce di destinazione dati richieste per questa versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="d6a31-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="d6a31-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="d6a31-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="d6a31-137">Il modulo indicato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="d6a31-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="d6a31-138">Questo HRESULT viene restituito anche quando non è possibile rilevare un modulo CLR perché la memoria è stata danneggiata, il modulo non è disponibile o la versione di CLR è successiva alla versione shim.</span><span class="sxs-lookup"><span data-stu-id="d6a31-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="d6a31-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="d6a31-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="d6a31-140">Questa versione di runtime non supporta questo modello di debug.</span><span class="sxs-lookup"><span data-stu-id="d6a31-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="d6a31-141">Attualmente, il modello di debug non è supportato dalle versioni CLR prima del .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d6a31-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="d6a31-142">Il parametro di output `pwszVersion` è ancora impostato sul valore corretto dopo l'errore.</span><span class="sxs-lookup"><span data-stu-id="d6a31-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="d6a31-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="d6a31-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="d6a31-144">La versione di CLR è maggiore della versione che questo debugger dichiara di supportare.</span><span class="sxs-lookup"><span data-stu-id="d6a31-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="d6a31-145">Il parametro di output `pwszVersion` è ancora impostato sul valore corretto dopo l'errore.</span><span class="sxs-lookup"><span data-stu-id="d6a31-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="d6a31-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="d6a31-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="d6a31-147">L'interfaccia `riidProcess` non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d6a31-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="d6a31-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="d6a31-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="d6a31-149">La struttura `CLR_DEBUGGING_VERSION` non dispone di un valore riconosciuto per `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="d6a31-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="d6a31-150">L'unico valore accettato in questa fase è 0.</span><span class="sxs-lookup"><span data-stu-id="d6a31-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d6a31-151">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="d6a31-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6a31-152">Note</span><span class="sxs-lookup"><span data-stu-id="d6a31-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6a31-153">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d6a31-153">Requirements</span></span>  
 <span data-ttu-id="d6a31-154">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6a31-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6a31-155">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6a31-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6a31-156">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6a31-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6a31-157">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6a31-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a31-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6a31-158">See also</span></span>

- [<span data-ttu-id="d6a31-159">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d6a31-159">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d6a31-160">Debug</span><span class="sxs-lookup"><span data-stu-id="d6a31-160">Debugging</span></span>](index.md)
