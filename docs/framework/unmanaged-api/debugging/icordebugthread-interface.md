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
ms.openlocfilehash: edcc0ebcadc1bd95574b0276bfd0e2d42e5474fd
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379813"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="1e648-102">Interfaccia ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="1e648-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="1e648-103">Rappresenta un thread in un processo.</span><span class="sxs-lookup"><span data-stu-id="1e648-103">Represents a thread in a process.</span></span> <span data-ttu-id="1e648-104">Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="1e648-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e648-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1e648-105">Methods</span></span>  
  
|<span data-ttu-id="1e648-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1e648-106">Method</span></span>|<span data-ttu-id="1e648-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e648-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e648-108">Metodo ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="1e648-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="1e648-109">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="1e648-109">This method is not implemented.</span></span> <span data-ttu-id="1e648-110">Non usarlo.</span><span class="sxs-lookup"><span data-stu-id="1e648-110">Do not use it.</span></span>|  
|[<span data-ttu-id="1e648-111">Metodo CreateEval</span><span class="sxs-lookup"><span data-stu-id="1e648-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="1e648-112">Crea un oggetto ICorDebugEval che opera su `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-113">Metodo CreateStepper</span><span class="sxs-lookup"><span data-stu-id="1e648-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="1e648-114">Crea un oggetto ICorDebugStepper che consente l'esecuzione del frame attivo in questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-115">Metodo EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="1e648-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="1e648-116">Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-117">Metodo GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="1e648-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="1e648-118">Ottiene un puntatore a interfaccia per l'oggetto ICorDebugChain attivo in questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-119">Metodo GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="1e648-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="1e648-120">Ottiene un puntatore a interfaccia per l'oggetto ICorDebugFrame attivo in questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-121">Metodo GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="1e648-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="1e648-122">Ottiene un puntatore a interfaccia per il dominio dell'applicazione in cui `ICorDebugThread` è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1e648-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="1e648-123">Metodo GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="1e648-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="1e648-124">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione attualmente generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1e648-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="1e648-125">Metodo GetDebugState</span><span class="sxs-lookup"><span data-stu-id="1e648-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="1e648-126">Ottiene un valore CorDebugThreadState che descrive lo stato di debug corrente di questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-127">Metodo GetHandle</span><span class="sxs-lookup"><span data-stu-id="1e648-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="1e648-128">Ottiene l'handle corrente per la parte attiva di questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-129">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="1e648-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="1e648-130">Ottiene l'identificatore del sistema operativo corrente della parte attiva di questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-131">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="1e648-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="1e648-132">Ottiene un puntatore a interfaccia al thread di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1e648-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="1e648-133">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="1e648-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="1e648-134">Ottiene un puntatore a interfaccia per il processo di cui fa `ICorDebugThread` parte.</span><span class="sxs-lookup"><span data-stu-id="1e648-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="1e648-135">Metodo GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="1e648-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="1e648-136">Ottiene un puntatore a interfaccia per il set di registri associato a questo `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-137">Metodo GetUserState</span><span class="sxs-lookup"><span data-stu-id="1e648-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="1e648-138">Ottiene una combinazione bit per bit di valori CorDebugUserState che descrivono lo stato corrente di questo oggetto `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="1e648-139">Metodo SetDebugState</span><span class="sxs-lookup"><span data-stu-id="1e648-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="1e648-140">Imposta una combinazione bit per bit di `CorDebugThreadState` valori che descrivono lo stato di debug di `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="1e648-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e648-141">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1e648-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e648-142">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="1e648-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e648-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e648-143">Requirements</span></span>  
 <span data-ttu-id="1e648-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e648-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e648-145">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e648-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e648-146">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e648-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e648-147">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e648-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e648-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e648-148">See also</span></span>

- [<span data-ttu-id="1e648-149">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1e648-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
