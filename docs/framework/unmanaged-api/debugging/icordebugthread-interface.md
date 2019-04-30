---
title: Interfaccia ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993980"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="6d9fa-102">Interfaccia ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="6d9fa-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="6d9fa-103">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-103">Represents a thread in a process.</span></span> <span data-ttu-id="6d9fa-104">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d9fa-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="6d9fa-105">Methods</span></span>  
  
|<span data-ttu-id="6d9fa-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="6d9fa-106">Method</span></span>|<span data-ttu-id="6d9fa-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d9fa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d9fa-108">Metodo ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="6d9fa-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="6d9fa-109">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-109">This method is not implemented.</span></span> <span data-ttu-id="6d9fa-110">Non usarlo.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-110">Do not use it.</span></span>|  
|[<span data-ttu-id="6d9fa-111">Metodo CreateEval</span><span class="sxs-lookup"><span data-stu-id="6d9fa-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="6d9fa-112">Crea un oggetto ICorDebugEval che opera su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-113">Metodo CreateStepper</span><span class="sxs-lookup"><span data-stu-id="6d9fa-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="6d9fa-114">Crea un oggetto ICorDebugStepper che consente di scorrere il frame attivo in questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-115">Metodo EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="6d9fa-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="6d9fa-116">Ottiene un puntatore a interfaccia per un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-117">Metodo GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="6d9fa-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="6d9fa-118">Ottiene un puntatore a interfaccia ICorDebugChain attiva su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-119">Metodo GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="6d9fa-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="6d9fa-120">Ottiene un puntatore a interfaccia ICorDebugFrame attiva su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-121">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="6d9fa-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="6d9fa-122">Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui questo `ICorDebugThread` è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="6d9fa-123">Metodo GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="6d9fa-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="6d9fa-124">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="6d9fa-125">Metodo GetDebugState</span><span class="sxs-lookup"><span data-stu-id="6d9fa-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="6d9fa-126">Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-127">Metodo GetHandle</span><span class="sxs-lookup"><span data-stu-id="6d9fa-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="6d9fa-128">Ottiene l'handle corrente per la parte attiva di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-129">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="6d9fa-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="6d9fa-130">Ottiene l'identificatore del sistema operativo corrente della parte attiva di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-131">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="6d9fa-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="6d9fa-132">Ottiene un puntatore a interfaccia per il thread di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6d9fa-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="6d9fa-133">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="6d9fa-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="6d9fa-134">Ottiene un puntatore a interfaccia per il processo di cui questo `ICorDebugThread` costituisce una parte.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="6d9fa-135">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="6d9fa-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="6d9fa-136">Ottiene un puntatore di interfaccia al set di registri associato a questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-137">Metodo GetUserState</span><span class="sxs-lookup"><span data-stu-id="6d9fa-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="6d9fa-138">Ottiene una combinazione bit per bit dei valori CorDebugUserState che descrivono lo stato corrente di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6d9fa-139">Metodo SetDebugState</span><span class="sxs-lookup"><span data-stu-id="6d9fa-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="6d9fa-140">Imposta una combinazione bit per bit di `CorDebugThreadState` i valori che descrivono lo stato di debug di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d9fa-141">Note</span><span class="sxs-lookup"><span data-stu-id="6d9fa-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d9fa-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6d9fa-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d9fa-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d9fa-143">Requirements</span></span>  
 <span data-ttu-id="6d9fa-144">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d9fa-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d9fa-145">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d9fa-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d9fa-146">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d9fa-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d9fa-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d9fa-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9fa-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d9fa-148">See also</span></span>

- [<span data-ttu-id="6d9fa-149">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6d9fa-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
