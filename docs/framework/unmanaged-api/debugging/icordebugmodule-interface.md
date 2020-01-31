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
ms.openlocfilehash: c573e6b768aee1e8b681dcf2e828dc24d409025b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793007"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="0ecc4-102">Interfaccia ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="0ecc4-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="0ecc4-103">Rappresenta un modulo di Common Language Runtime (CLR), ovvero un file eseguibile o una libreria a collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="0ecc4-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ecc4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0ecc4-104">Methods</span></span>  
  
|<span data-ttu-id="0ecc4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0ecc4-105">Method</span></span>|<span data-ttu-id="0ecc4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ecc4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ecc4-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0ecc4-107">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="0ecc4-108">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-108">Not implemented.</span></span>|  
|[<span data-ttu-id="0ecc4-109">Metodo EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="0ecc4-109">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="0ecc4-110">Determina se i callback [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-110">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="0ecc4-111">Metodo EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="0ecc4-111">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="0ecc4-112">Determina se il compilatore JIT (just-in-Time) conserva le informazioni di debug per i metodi all'interno di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="0ecc4-113">Metodo GetAssembly</span><span class="sxs-lookup"><span data-stu-id="0ecc4-113">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="0ecc4-114">Ottiene l'assembly contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="0ecc4-115">Metodo GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="0ecc4-115">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="0ecc4-116">Ottiene l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="0ecc4-117">Metodo GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="0ecc4-117">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="0ecc4-118">Ottiene l'oggetto ICorDebugClass dai metadati.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="0ecc4-119">Metodo GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="0ecc4-119">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="0ecc4-120">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-120">Deprecated.</span></span>|  
|[<span data-ttu-id="0ecc4-121">Metodo GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="0ecc4-121">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="0ecc4-122">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-122">Not implemented.</span></span>|  
|[<span data-ttu-id="0ecc4-123">Metodo GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="0ecc4-123">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="0ecc4-124">Ottiene la funzione specificata dal token di metadati.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="0ecc4-125">Metodo GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="0ecc4-125">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="0ecc4-126">Ottiene un oggetto valore per la variabile globale specificata.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="0ecc4-127">Metodo GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="0ecc4-127">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="0ecc4-128">Ottiene un puntatore a interfaccia dei metadati che può essere utilizzato per esaminare i metadati per il modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="0ecc4-129">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="0ecc4-129">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="0ecc4-130">Ottiene il nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="0ecc4-131">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="0ecc4-131">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="0ecc4-132">Ottiene il processo contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="0ecc4-133">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="0ecc4-133">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="0ecc4-134">Ottiene le dimensioni in byte del modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="0ecc4-135">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="0ecc4-135">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="0ecc4-136">Ottiene il token per la voce della tabella per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="0ecc4-137">Metodo IsDynamic</span><span class="sxs-lookup"><span data-stu-id="0ecc4-137">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="0ecc4-138">Indica se il modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="0ecc4-139">Metodo IsInMemory</span><span class="sxs-lookup"><span data-stu-id="0ecc4-139">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="0ecc4-140">Indica se il modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ecc4-141">Note</span><span class="sxs-lookup"><span data-stu-id="0ecc4-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ecc4-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="0ecc4-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ecc4-143">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0ecc4-143">Requirements</span></span>  
 <span data-ttu-id="0ecc4-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ecc4-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ecc4-145">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ecc4-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ecc4-146">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ecc4-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ecc4-147">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ecc4-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecc4-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ecc4-148">See also</span></span>

- [<span data-ttu-id="0ecc4-149">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="0ecc4-149">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="0ecc4-150">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0ecc4-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
