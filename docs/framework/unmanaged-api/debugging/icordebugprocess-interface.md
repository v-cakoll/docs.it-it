---
title: Interfaccia ICorDebugProcess
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
ms.openlocfilehash: ab48efccc88787f099a182627777db95304cdc3e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212074"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="a171e-102">Interfaccia ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="a171e-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="a171e-103">Rappresenta un processo che esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a171e-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="a171e-104">Questa interfaccia è una sottoclasse di ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="a171e-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a171e-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a171e-105">Methods</span></span>  
  
|<span data-ttu-id="a171e-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a171e-106">Method</span></span>|<span data-ttu-id="a171e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a171e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a171e-108">Metodo ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="a171e-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="a171e-109">Cancella l'eccezione non gestita corrente sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="a171e-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="a171e-110">Metodo EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="a171e-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="a171e-111">Abilita e Disabilita l'invio di messaggi di log al debugger.</span><span class="sxs-lookup"><span data-stu-id="a171e-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="a171e-112">Metodo EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="a171e-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="a171e-113">Enumera tutti i domini applicazione nel processo.</span><span class="sxs-lookup"><span data-stu-id="a171e-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="a171e-114">Metodo EnumerateObjects</span><span class="sxs-lookup"><span data-stu-id="a171e-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="a171e-115">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="a171e-115">Not implemented.</span></span>|  
|[<span data-ttu-id="a171e-116">Metodo GetHandle</span><span class="sxs-lookup"><span data-stu-id="a171e-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="a171e-117">Ottiene un handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="a171e-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="a171e-118">Metodo GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="a171e-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="a171e-119">Ottiene l'ID del thread del sistema operativo per il thread helper interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="a171e-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="a171e-120">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="a171e-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="a171e-121">Ottiene l'ID del sistema operativo (OS) del processo.</span><span class="sxs-lookup"><span data-stu-id="a171e-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="a171e-122">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="a171e-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="a171e-123">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="a171e-123">Not implemented.</span></span>|  
|[<span data-ttu-id="a171e-124">Metodo GetThread</span><span class="sxs-lookup"><span data-stu-id="a171e-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="a171e-125">Ottiene l'istanza di ICorDebugThread con l'ID del thread del sistema operativo specificato.</span><span class="sxs-lookup"><span data-stu-id="a171e-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="a171e-126">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="a171e-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="a171e-127">Ottiene il contesto per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="a171e-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="a171e-128">Metodo IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="a171e-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="a171e-129">Determina se il thread è stato sospeso a causa dell'arresto del processo da parte del debugger.</span><span class="sxs-lookup"><span data-stu-id="a171e-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="a171e-130">Metodo IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="a171e-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="a171e-131">Determina se un indirizzo si trova all'interno di uno stub che provocherà una transizione al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a171e-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="a171e-132">Metodo ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="a171e-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="a171e-133">Imposta il livello di gravità dell'opzione di log specificata.</span><span class="sxs-lookup"><span data-stu-id="a171e-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="a171e-134">Metodo ReadMemory</span><span class="sxs-lookup"><span data-stu-id="a171e-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="a171e-135">Legge la memoria dal processo.</span><span class="sxs-lookup"><span data-stu-id="a171e-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="a171e-136">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="a171e-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="a171e-137">Imposta il contesto per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="a171e-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="a171e-138">Metodo ThreadForFiberCookie</span><span class="sxs-lookup"><span data-stu-id="a171e-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="a171e-139">Operazione deprecata.</span><span class="sxs-lookup"><span data-stu-id="a171e-139">Deprecated.</span></span>|  
|[<span data-ttu-id="a171e-140">Metodo WriteMemory</span><span class="sxs-lookup"><span data-stu-id="a171e-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="a171e-141">Scrive i dati in un'area di memoria nel processo.</span><span class="sxs-lookup"><span data-stu-id="a171e-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a171e-142">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a171e-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a171e-143">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a171e-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a171e-144">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a171e-144">Requirements</span></span>  
 <span data-ttu-id="a171e-145">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a171e-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a171e-146">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a171e-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a171e-147">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a171e-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a171e-148">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a171e-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a171e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a171e-149">See also</span></span>

- [<span data-ttu-id="a171e-150">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a171e-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="a171e-151">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a171e-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
