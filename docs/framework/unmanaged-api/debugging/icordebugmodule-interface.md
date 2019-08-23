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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dce4f5859568c1288610e171286a5919dc8b19b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962436"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="8fbce-102">Interfaccia ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="8fbce-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="8fbce-103">Rappresenta un modulo di Common Language Runtime (CLR), ovvero un file eseguibile o una libreria a collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="8fbce-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fbce-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8fbce-104">Methods</span></span>  
  
|<span data-ttu-id="8fbce-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8fbce-105">Method</span></span>|<span data-ttu-id="8fbce-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8fbce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8fbce-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8fbce-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="8fbce-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8fbce-108">Not implemented.</span></span>|  
|[<span data-ttu-id="8fbce-109">Metodo EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="8fbce-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="8fbce-110">Determina se i callback [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="8fbce-111">Metodo EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="8fbce-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="8fbce-112">Determina se il compilatore JIT (just-in-Time) conserva le informazioni di debug per i metodi all'interno di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="8fbce-113">Metodo GetAssembly</span><span class="sxs-lookup"><span data-stu-id="8fbce-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="8fbce-114">Ottiene l'assembly contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="8fbce-115">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="8fbce-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="8fbce-116">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="8fbce-117">Metodo GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="8fbce-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="8fbce-118">Ottiene l'oggetto ICorDebugClass dai metadati.</span><span class="sxs-lookup"><span data-stu-id="8fbce-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="8fbce-119">Metodo GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="8fbce-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="8fbce-120">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="8fbce-120">Deprecated.</span></span>|  
|[<span data-ttu-id="8fbce-121">Metodo GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="8fbce-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="8fbce-122">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="8fbce-122">Not implemented.</span></span>|  
|[<span data-ttu-id="8fbce-123">Metodo GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="8fbce-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="8fbce-124">Ottiene la funzione specificata dal token di metadati.</span><span class="sxs-lookup"><span data-stu-id="8fbce-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="8fbce-125">Metodo GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="8fbce-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="8fbce-126">Ottiene un oggetto valore per la variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="8fbce-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="8fbce-127">Metodo GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="8fbce-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="8fbce-128">Ottiene un puntatore a interfaccia dei metadati che può essere utilizzato per esaminare i metadati per il modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="8fbce-129">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="8fbce-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="8fbce-130">Ottiene il nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="8fbce-131">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="8fbce-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="8fbce-132">Ottiene il processo contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="8fbce-133">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="8fbce-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="8fbce-134">Ottiene le dimensioni in byte del modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="8fbce-135">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="8fbce-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="8fbce-136">Ottiene il token per la voce della tabella per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="8fbce-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="8fbce-137">Metodo IsDynamic</span><span class="sxs-lookup"><span data-stu-id="8fbce-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="8fbce-138">Indica se il modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="8fbce-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="8fbce-139">Metodo IsInMemory</span><span class="sxs-lookup"><span data-stu-id="8fbce-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="8fbce-140">Indica se il modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="8fbce-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fbce-141">Note</span><span class="sxs-lookup"><span data-stu-id="8fbce-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8fbce-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8fbce-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fbce-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fbce-143">Requirements</span></span>  
 <span data-ttu-id="8fbce-144">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fbce-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fbce-145">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8fbce-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fbce-146">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fbce-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fbce-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fbce-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fbce-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fbce-148">See also</span></span>

- [<span data-ttu-id="8fbce-149">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="8fbce-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="8fbce-150">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8fbce-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
