---
title: ICorDebugThread Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread
helpviewer_keywords: ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2df43a35e510695d7af0c38cbb8fb3b051f5f354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="b6fc3-102">ICorDebugThread Interface1</span><span class="sxs-lookup"><span data-stu-id="b6fc3-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="b6fc3-103">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-103">Represents a thread in a process.</span></span> <span data-ttu-id="b6fc3-104">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6fc3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b6fc3-105">Methods</span></span>  
  
|<span data-ttu-id="b6fc3-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b6fc3-106">Method</span></span>|<span data-ttu-id="b6fc3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6fc3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6fc3-108">Metodo ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="b6fc3-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="b6fc3-109">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-109">This method is not implemented.</span></span> <span data-ttu-id="b6fc3-110">Non usarlo.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-110">Do not use it.</span></span>|  
|[<span data-ttu-id="b6fc3-111">Metodo CreateEval</span><span class="sxs-lookup"><span data-stu-id="b6fc3-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="b6fc3-112">Crea un oggetto ICorDebugEval che agisce su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-113">Metodo CreateStepper</span><span class="sxs-lookup"><span data-stu-id="b6fc3-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="b6fc3-114">Crea un oggetto ICorDebugStepper che consente l'esecuzione passo passo del frame attivo in questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-115">Metodo EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="b6fc3-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="b6fc3-116">Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum contenente tutte le catene dello stack in `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-117">Metodo GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="b6fc3-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="b6fc3-118">Ottiene un puntatore a interfaccia ICorDebugChain attiva su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-119">Metodo GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="b6fc3-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="b6fc3-120">Ottiene un puntatore a interfaccia ICorDebugFrame attiva su questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-121">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="b6fc3-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="b6fc3-122">Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui `ICorDebugThread` è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="b6fc3-123">Metodo GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="b6fc3-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="b6fc3-124">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="b6fc3-125">Metodo GetDebugState</span><span class="sxs-lookup"><span data-stu-id="b6fc3-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="b6fc3-126">Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-127">Metodo GetHandle</span><span class="sxs-lookup"><span data-stu-id="b6fc3-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="b6fc3-128">Ottiene l'handle corrente per la parte attiva di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-129">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="b6fc3-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="b6fc3-130">Ottiene l'identificatore del sistema operativo corrente della parte attiva di `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-131">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="b6fc3-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="b6fc3-132">Ottiene un puntatore a interfaccia per il thread di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b6fc3-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="b6fc3-133">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="b6fc3-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="b6fc3-134">Ottiene un puntatore a interfaccia per il processo di cui `ICorDebugThread` costituisce una parte.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="b6fc3-135">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="b6fc3-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="b6fc3-136">Ottiene un puntatore a interfaccia al set di registri associato a questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-137">Metodo GetUserState</span><span class="sxs-lookup"><span data-stu-id="b6fc3-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="b6fc3-138">Ottiene una combinazione bit per bit di valori CorDebugUserState che descrivono lo stato corrente di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="b6fc3-139">Metodo SetDebugState</span><span class="sxs-lookup"><span data-stu-id="b6fc3-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="b6fc3-140">Ottiene una combinazione bit per bit di `CorDebugThreadState` valori che descrivono lo stato di debug di questo `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6fc3-141">Note</span><span class="sxs-lookup"><span data-stu-id="b6fc3-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6fc3-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6fc3-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6fc3-143">Requirements</span></span>  
 <span data-ttu-id="b6fc3-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6fc3-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6fc3-145">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b6fc3-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6fc3-146">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6fc3-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6fc3-147">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6fc3-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fc3-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6fc3-148">See Also</span></span>  
 [<span data-ttu-id="b6fc3-149">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b6fc3-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
