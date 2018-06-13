---
title: ICorDebugThread Interface1
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
ms.openlocfilehash: 404f1bdf5865733648084e34a558b7b20a59b3ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423078"
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="7eab1-102">ICorDebugThread Interface1</span><span class="sxs-lookup"><span data-stu-id="7eab1-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="7eab1-103">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="7eab1-103">Represents a thread in a process.</span></span> <span data-ttu-id="7eab1-104">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="7eab1-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7eab1-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7eab1-105">Methods</span></span>  
  
|<span data-ttu-id="7eab1-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7eab1-106">Method</span></span>|<span data-ttu-id="7eab1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7eab1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7eab1-108">Metodo ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="7eab1-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="7eab1-109">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="7eab1-109">This method is not implemented.</span></span> <span data-ttu-id="7eab1-110">Non usarlo.</span><span class="sxs-lookup"><span data-stu-id="7eab1-110">Do not use it.</span></span>|  
|[<span data-ttu-id="7eab1-111">Metodo CreateEval</span><span class="sxs-lookup"><span data-stu-id="7eab1-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="7eab1-112">Crea un oggetto ICorDebugEval che agisce su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-113">Metodo CreateStepper</span><span class="sxs-lookup"><span data-stu-id="7eab1-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="7eab1-114">Crea un oggetto ICorDebugStepper che consente l'esecuzione passo passo del frame attivo in questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-115">Metodo EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="7eab1-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="7eab1-116">Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum contenente tutte le catene dello stack in `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-117">Metodo GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="7eab1-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="7eab1-118">Ottiene un puntatore a interfaccia ICorDebugChain attiva su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-119">Metodo GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="7eab1-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="7eab1-120">Ottiene un puntatore a interfaccia ICorDebugFrame attiva su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-121">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="7eab1-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="7eab1-122">Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui `ICorDebugThread` è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7eab1-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="7eab1-123">Metodo GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="7eab1-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="7eab1-124">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="7eab1-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="7eab1-125">Metodo GetDebugState</span><span class="sxs-lookup"><span data-stu-id="7eab1-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="7eab1-126">Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-127">Metodo GetHandle</span><span class="sxs-lookup"><span data-stu-id="7eab1-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="7eab1-128">Ottiene l'handle corrente per la parte attiva di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-129">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="7eab1-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="7eab1-130">Ottiene l'identificatore del sistema operativo corrente della parte attiva di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-131">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="7eab1-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="7eab1-132">Ottiene un puntatore a interfaccia per il thread di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7eab1-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="7eab1-133">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="7eab1-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="7eab1-134">Ottiene un puntatore a interfaccia per il processo di cui `ICorDebugThread` costituisce una parte.</span><span class="sxs-lookup"><span data-stu-id="7eab1-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="7eab1-135">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="7eab1-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="7eab1-136">Ottiene un puntatore a interfaccia al set di registri associato a questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-137">Metodo GetUserState</span><span class="sxs-lookup"><span data-stu-id="7eab1-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="7eab1-138">Ottiene una combinazione bit per bit di valori CorDebugUserState che descrivono lo stato corrente di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7eab1-139">Metodo SetDebugState</span><span class="sxs-lookup"><span data-stu-id="7eab1-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="7eab1-140">Ottiene una combinazione bit per bit di `CorDebugThreadState` valori che descrivono lo stato di debug di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7eab1-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eab1-141">Note</span><span class="sxs-lookup"><span data-stu-id="7eab1-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7eab1-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="7eab1-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eab1-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7eab1-143">Requirements</span></span>  
 <span data-ttu-id="7eab1-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eab1-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eab1-145">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7eab1-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eab1-146">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7eab1-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eab1-147">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eab1-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eab1-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eab1-148">See Also</span></span>  
 [<span data-ttu-id="7eab1-149">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7eab1-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
