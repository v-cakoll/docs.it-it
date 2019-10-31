---
title: Interfaccia ICorDebug
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: ee6bcbc9f3377735ed289d52afddb6efa755b16d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134066"
---
# <a name="icordebug-interface"></a><span data-ttu-id="7432a-102">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="7432a-102">ICorDebug Interface</span></span>
<span data-ttu-id="7432a-103">Fornisce metodi che consentono agli sviluppatori di eseguire il debug di applicazioni nell'ambiente Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7432a-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7432a-104">Il debug in modalità mista (codice gestito e nativo) non è supportato in Windows 95, Windows 98 o Windows ME o su piattaforme non x86 (ad esempio IA64 e AMD64).</span><span class="sxs-lookup"><span data-stu-id="7432a-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7432a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7432a-105">Methods</span></span>  
  
|<span data-ttu-id="7432a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7432a-106">Method</span></span>|<span data-ttu-id="7432a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7432a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7432a-108">Metodo CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="7432a-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="7432a-109">Determina se è possibile avviare un nuovo processo o connettersi al processo specificato all'interno del contesto della configurazione corrente del computer e del runtime.</span><span class="sxs-lookup"><span data-stu-id="7432a-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="7432a-110">Metodo CreateProcess</span><span class="sxs-lookup"><span data-stu-id="7432a-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="7432a-111">Avvia un processo e il relativo thread primario sotto il controllo del debugger.</span><span class="sxs-lookup"><span data-stu-id="7432a-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="7432a-112">Metodo DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="7432a-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="7432a-113">Connette il debugger a un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="7432a-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="7432a-114">Metodo EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="7432a-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="7432a-115">Ottiene un enumeratore per i processi di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="7432a-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="7432a-116">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="7432a-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="7432a-117">Restituisce l'oggetto "ICorDebugProcess" con l'ID di processo specificato.</span><span class="sxs-lookup"><span data-stu-id="7432a-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="7432a-118">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="7432a-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="7432a-119">Inizializza l'oggetto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="7432a-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="7432a-120">Metodo SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="7432a-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="7432a-121">Specifica l'oggetto gestore eventi per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7432a-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="7432a-122">Metodo SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="7432a-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="7432a-123">Specifica l'oggetto gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="7432a-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="7432a-124">Metodo Terminate</span><span class="sxs-lookup"><span data-stu-id="7432a-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="7432a-125">Termina l'oggetto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="7432a-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7432a-126">Note</span><span class="sxs-lookup"><span data-stu-id="7432a-126">Remarks</span></span>  
 <span data-ttu-id="7432a-127">`ICorDebug` rappresenta un ciclo di elaborazione di eventi per un processo del debugger.</span><span class="sxs-lookup"><span data-stu-id="7432a-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="7432a-128">Il debugger deve attendere il callback di [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) da tutti i processi di cui è in corso il debug prima di rilasciare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7432a-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="7432a-129">L'oggetto `ICorDebug` è l'oggetto iniziale per controllare tutto il debug gestito ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="7432a-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="7432a-130">In .NET Framework versioni 1,0 e 1,1, questo oggetto è un oggetto `CoClass` creato da COM.</span><span class="sxs-lookup"><span data-stu-id="7432a-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="7432a-131">In .NET Framework versione 2,0, questo oggetto non è più un oggetto `CoClass`.</span><span class="sxs-lookup"><span data-stu-id="7432a-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="7432a-132">Deve essere creato dalla funzione [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , che è più compatibile con la versione.</span><span class="sxs-lookup"><span data-stu-id="7432a-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="7432a-133">Questa nuova funzione di creazione consente ai client di ottenere un'implementazione specifica di `ICorDebug`, che emula anche una versione specifica dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="7432a-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7432a-134">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="7432a-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7432a-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7432a-135">Requirements</span></span>  
 <span data-ttu-id="7432a-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7432a-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7432a-137">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7432a-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7432a-138">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7432a-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7432a-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7432a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7432a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7432a-140">See also</span></span>

- [<span data-ttu-id="7432a-141">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7432a-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
