---
title: Interfaccia ICorDebug
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug
helpviewer_keywords: ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ed0b3a8b42157f6a4fcbc6b4a05a416da736147
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebug-interface"></a><span data-ttu-id="4ad93-102">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="4ad93-102">ICorDebug Interface</span></span>
<span data-ttu-id="4ad93-103">Fornisce metodi che consentono agli sviluppatori di debug delle applicazioni nell'ambiente common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4ad93-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ad93-104">Debug in modalità mista (codice gestito e nativo) non è supportato in Windows 95, Windows 98 o Windows ME, o in piattaforme diverse da x86 (ad esempio IA64 e AMD64).</span><span class="sxs-lookup"><span data-stu-id="4ad93-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ad93-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4ad93-105">Methods</span></span>  
  
|<span data-ttu-id="4ad93-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="4ad93-106">Method</span></span>|<span data-ttu-id="4ad93-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ad93-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ad93-108">Metodo CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="4ad93-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="4ad93-109">Determina se avviare un nuovo processo o connettersi al processo specificato è possibili all'interno del contesto della configurazione del computer e di runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="4ad93-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="4ad93-110">Metodo CreateProcess</span><span class="sxs-lookup"><span data-stu-id="4ad93-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="4ad93-111">Avvia un processo e il relativo thread primario sotto il controllo del debugger.</span><span class="sxs-lookup"><span data-stu-id="4ad93-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="4ad93-112">Metodo DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="4ad93-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="4ad93-113">Collega il debugger a un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="4ad93-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="4ad93-114">Metodo EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="4ad93-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="4ad93-115">Ottiene un enumeratore per i processi sottoposti a debug.</span><span class="sxs-lookup"><span data-stu-id="4ad93-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="4ad93-116">Metodo GetProcess</span><span class="sxs-lookup"><span data-stu-id="4ad93-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="4ad93-117">Restituisce l'oggetto "ICorDebugProcess" con l'ID di processo specificato.</span><span class="sxs-lookup"><span data-stu-id="4ad93-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="4ad93-118">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="4ad93-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="4ad93-119">Inizializza il `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4ad93-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="4ad93-120">Metodo SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="4ad93-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="4ad93-121">Specifica l'oggetto di gestore eventi per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="4ad93-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="4ad93-122">Metodo SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="4ad93-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="4ad93-123">Specifica l'oggetto di gestore eventi per gli eventi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="4ad93-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="4ad93-124">Metodo Terminate</span><span class="sxs-lookup"><span data-stu-id="4ad93-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="4ad93-125">Termina il `ICorDebug` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4ad93-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ad93-126">Note</span><span class="sxs-lookup"><span data-stu-id="4ad93-126">Remarks</span></span>  
 <span data-ttu-id="4ad93-127">`ICorDebug`rappresenta un ciclo di elaborazione di eventi per un processo del debugger.</span><span class="sxs-lookup"><span data-stu-id="4ad93-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="4ad93-128">Il debugger deve attendere il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback da tutti i processi in fase di debug prima di rilasciare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4ad93-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="4ad93-129">Il `ICorDebug` oggetto è l'oggetto iniziale per controllare qualsiasi ulteriore debug gestito.</span><span class="sxs-lookup"><span data-stu-id="4ad93-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="4ad93-130">Nelle versioni di .NET Framework 1.0 e 1.1, questo oggetto è stato un `CoClass` oggetto creato da COM.</span><span class="sxs-lookup"><span data-stu-id="4ad93-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="4ad93-131">In .NET Framework versione 2.0, questo oggetto non è più un `CoClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4ad93-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="4ad93-132">Deve essere creato per il [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) funzione, che è più compatibile con versione.</span><span class="sxs-lookup"><span data-stu-id="4ad93-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="4ad93-133">Questa nuova funzione di creazione consente ai client di ottenere un'implementazione specifica di `ICorDebug`, che emula anche una versione specifica dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="4ad93-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ad93-134">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4ad93-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad93-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ad93-135">Requirements</span></span>  
 <span data-ttu-id="4ad93-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ad93-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad93-137">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4ad93-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ad93-138">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ad93-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ad93-139">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad93-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad93-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad93-140">See Also</span></span>  
 [<span data-ttu-id="4ad93-141">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4ad93-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
