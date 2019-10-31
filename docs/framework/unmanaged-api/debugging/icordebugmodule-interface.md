---
title: Interfaccia ICorDebugModule
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
ms.openlocfilehash: 971d6a6a2157c48dcb9105e9f523b1f077098479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129477"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="7ef1d-102">Interfaccia ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="7ef1d-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="7ef1d-103">Rappresenta un modulo di Common Language Runtime (CLR), ovvero un file eseguibile o una libreria a collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="7ef1d-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ef1d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7ef1d-104">Methods</span></span>  
  
|<span data-ttu-id="7ef1d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7ef1d-105">Method</span></span>|<span data-ttu-id="7ef1d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ef1d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ef1d-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef1d-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="7ef1d-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-108">Not implemented.</span></span>|  
|[<span data-ttu-id="7ef1d-109">Metodo EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="7ef1d-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="7ef1d-110">Determina se i callback [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="7ef1d-111">Metodo EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="7ef1d-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="7ef1d-112">Determina se il compilatore JIT (just-in-Time) conserva le informazioni di debug per i metodi all'interno di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="7ef1d-113">Metodo GetAssembly</span><span class="sxs-lookup"><span data-stu-id="7ef1d-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="7ef1d-114">Ottiene l'assembly contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="7ef1d-115">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="7ef1d-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="7ef1d-116">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="7ef1d-117">Metodo GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="7ef1d-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="7ef1d-118">Ottiene l'oggetto ICorDebugClass dai metadati.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="7ef1d-119">Metodo GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="7ef1d-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="7ef1d-120">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-120">Deprecated.</span></span>|  
|[<span data-ttu-id="7ef1d-121">Metodo GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="7ef1d-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="7ef1d-122">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-122">Not implemented.</span></span>|  
|[<span data-ttu-id="7ef1d-123">Metodo GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="7ef1d-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="7ef1d-124">Ottiene la funzione specificata dal token di metadati.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="7ef1d-125">Metodo GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="7ef1d-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="7ef1d-126">Ottiene un oggetto valore per la variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="7ef1d-127">Metodo GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="7ef1d-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="7ef1d-128">Ottiene un puntatore a interfaccia dei metadati che può essere utilizzato per esaminare i metadati per il modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="7ef1d-129">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="7ef1d-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="7ef1d-130">Ottiene il nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="7ef1d-131">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="7ef1d-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="7ef1d-132">Ottiene il processo contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="7ef1d-133">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="7ef1d-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="7ef1d-134">Ottiene le dimensioni in byte del modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="7ef1d-135">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="7ef1d-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="7ef1d-136">Ottiene il token per la voce della tabella per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="7ef1d-137">Metodo IsDynamic</span><span class="sxs-lookup"><span data-stu-id="7ef1d-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="7ef1d-138">Indica se il modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="7ef1d-139">Metodo IsInMemory</span><span class="sxs-lookup"><span data-stu-id="7ef1d-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="7ef1d-140">Indica se il modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ef1d-141">Note</span><span class="sxs-lookup"><span data-stu-id="7ef1d-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ef1d-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="7ef1d-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef1d-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ef1d-143">Requirements</span></span>  
 <span data-ttu-id="7ef1d-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ef1d-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef1d-145">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ef1d-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ef1d-146">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ef1d-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ef1d-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ef1d-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef1d-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef1d-148">See also</span></span>

- [<span data-ttu-id="7ef1d-149">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="7ef1d-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="7ef1d-150">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7ef1d-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
