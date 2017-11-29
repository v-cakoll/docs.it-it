---
title: ICorDebugModule Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule
helpviewer_keywords: ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ced01c9c01a32468f371a8e172c878337fb79757
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmodule-interface1"></a><span data-ttu-id="c8799-102">ICorDebugModule Interface1</span><span class="sxs-lookup"><span data-stu-id="c8799-102">ICorDebugModule Interface1</span></span>
<span data-ttu-id="c8799-103">Rappresenta un modulo common language runtime (CLR), ovvero un file eseguibile o una libreria di collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="c8799-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8799-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c8799-104">Methods</span></span>  
  
|<span data-ttu-id="c8799-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c8799-105">Method</span></span>|<span data-ttu-id="c8799-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8799-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8799-107">CreateBreakpoint (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="c8799-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="c8799-108">Not implemented.</span></span>|  
|[<span data-ttu-id="c8799-109">EnableClassLoadCallbacks (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="c8799-110">Determina se il [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="c8799-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="c8799-111">EnableJITDebugging (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="c8799-112">Determina se il compilatore di just-in-time (JIT) consente di mantenere le informazioni di debug per i metodi all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="c8799-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="c8799-113">GetAssembly (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="c8799-114">Ottiene l'assembly per il modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c8799-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="c8799-115">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="c8799-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="c8799-116">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="c8799-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="c8799-117">GetClassFromToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="c8799-118">Ottiene l'oggetto ICorDebugClass dai metadati.</span><span class="sxs-lookup"><span data-stu-id="c8799-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="c8799-119">GetEditAndContinueSnapshot (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="c8799-120">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="c8799-120">Deprecated.</span></span>|  
|[<span data-ttu-id="c8799-121">GetFunctionFromRVA (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="c8799-122">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="c8799-122">Not implemented.</span></span>|  
|[<span data-ttu-id="c8799-123">GetFunctionFromToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="c8799-124">Ottiene la funzione specificata dal token di metadati.</span><span class="sxs-lookup"><span data-stu-id="c8799-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="c8799-125">GetGlobalVariableValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="c8799-126">Ottiene un oggetto valore per la variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="c8799-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="c8799-127">GetMetaDataInterface (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="c8799-128">Ottiene un puntatore di interfaccia di metadati che può essere utilizzato per esaminare i metadati per il modulo.</span><span class="sxs-lookup"><span data-stu-id="c8799-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="c8799-129">GetName (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="c8799-130">Ottiene il nome del file del modulo.</span><span class="sxs-lookup"><span data-stu-id="c8799-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="c8799-131">GetProcess (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="c8799-132">Ottiene il processo di contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="c8799-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="c8799-133">GetSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="c8799-134">Ottiene le dimensioni del modulo in byte.</span><span class="sxs-lookup"><span data-stu-id="c8799-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="c8799-135">GetToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="c8799-136">Ottiene il token per la voce della tabella per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="c8799-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="c8799-137">IsDynamic (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="c8799-138">Indica se il modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="c8799-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="c8799-139">IsInMemory (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8799-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="c8799-140">Indica se questo modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="c8799-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8799-141">Note</span><span class="sxs-lookup"><span data-stu-id="c8799-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8799-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c8799-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8799-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8799-143">Requirements</span></span>  
 <span data-ttu-id="c8799-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8799-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8799-145">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c8799-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8799-146">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8799-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8799-147">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8799-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8799-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8799-148">See Also</span></span>  
 [<span data-ttu-id="c8799-149">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c8799-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="c8799-150">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c8799-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
