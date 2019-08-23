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
ms.openlocfilehash: 1517d686c50923f5599e33436e0ad6126e8be140
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923148"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="fcc3a-102">Interfaccia ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="fcc3a-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="fcc3a-103">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-103">Represents a thread in a process.</span></span> <span data-ttu-id="fcc3a-104">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcc3a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fcc3a-105">Methods</span></span>  
  
|<span data-ttu-id="fcc3a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="fcc3a-106">Method</span></span>|<span data-ttu-id="fcc3a-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="fcc3a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcc3a-108">Metodo ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="fcc3a-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="fcc3a-109">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-109">This method is not implemented.</span></span> <span data-ttu-id="fcc3a-110">Non usarlo.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-110">Do not use it.</span></span>|  
|[<span data-ttu-id="fcc3a-111">Metodo CreateEval</span><span class="sxs-lookup"><span data-stu-id="fcc3a-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="fcc3a-112">Crea un oggetto ICorDebugEval che opera su `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-113">Metodo CreateStepper</span><span class="sxs-lookup"><span data-stu-id="fcc3a-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="fcc3a-114">Crea un oggetto ICorDebugStepper che consente l'esecuzione del frame attivo in questo `ICorDebugThread`oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-115">Metodo EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="fcc3a-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="fcc3a-116">Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum che contiene tutte le catene dello `ICorDebugThread`stack in questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-117">Metodo GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="fcc3a-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="fcc3a-118">Ottiene un puntatore a interfaccia per l'oggetto ICorDebugChain attivo `ICorDebugThread`in questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-119">Metodo GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="fcc3a-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="fcc3a-120">Ottiene un puntatore a interfaccia per l'oggetto ICorDebugFrame attivo `ICorDebugThread`in questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-121">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="fcc3a-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="fcc3a-122">Ottiene un puntatore a interfaccia per il dominio dell'applicazione in `ICorDebugThread` cui è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="fcc3a-123">Metodo GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="fcc3a-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="fcc3a-124">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione attualmente generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="fcc3a-125">Metodo GetDebugState</span><span class="sxs-lookup"><span data-stu-id="fcc3a-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="fcc3a-126">Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di `ICorDebugThread`questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-127">Metodo GetHandle</span><span class="sxs-lookup"><span data-stu-id="fcc3a-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="fcc3a-128">Ottiene l'handle corrente per la parte attiva di questo `ICorDebugThread`oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-129">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="fcc3a-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="fcc3a-130">Ottiene l'identificatore del sistema operativo corrente della parte attiva di questo `ICorDebugThread`oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-131">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="fcc3a-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="fcc3a-132">Ottiene un puntatore a interfaccia al thread di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fcc3a-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="fcc3a-133">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="fcc3a-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="fcc3a-134">Ottiene un puntatore a interfaccia per il processo di cui `ICorDebugThread` fa parte.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="fcc3a-135">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="fcc3a-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="fcc3a-136">Ottiene un puntatore a interfaccia per il set di registri associato `ICorDebugThread`a questo.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-137">Metodo GetUserState</span><span class="sxs-lookup"><span data-stu-id="fcc3a-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="fcc3a-138">Ottiene una combinazione bit per bit di valori CorDebugUserState che descrivono lo stato `ICorDebugThread`corrente di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="fcc3a-139">Metodo SetDebugState</span><span class="sxs-lookup"><span data-stu-id="fcc3a-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="fcc3a-140">Imposta una combinazione bit per `CorDebugThreadState` bit di valori che descrivono lo stato `ICorDebugThread`di debug di.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc3a-141">Note</span><span class="sxs-lookup"><span data-stu-id="fcc3a-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcc3a-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="fcc3a-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcc3a-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fcc3a-143">Requirements</span></span>  
 <span data-ttu-id="fcc3a-144">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcc3a-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc3a-145">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fcc3a-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcc3a-146">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcc3a-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcc3a-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc3a-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc3a-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc3a-148">See also</span></span>

- [<span data-ttu-id="fcc3a-149">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fcc3a-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
