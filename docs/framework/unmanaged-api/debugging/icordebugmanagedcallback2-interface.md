---
title: Interfaccia ICorDebugManagedCallback2
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca33436d98edf5844a5ca27c9ac89648f10ec0c5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909975"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="4d15d-102">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="4d15d-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="4d15d-103">Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="4d15d-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="4d15d-104">`ICorDebugManagedCallback2`è un'estensione logica dell'interfaccia [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4d15d-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d15d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4d15d-105">Methods</span></span>  
  
|<span data-ttu-id="4d15d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="4d15d-106">Method</span></span>|<span data-ttu-id="4d15d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d15d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d15d-108">Metodo ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="4d15d-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="4d15d-109">Notifica al debugger che è stato modificato il set di attività associato alla connessione specificata.</span><span class="sxs-lookup"><span data-stu-id="4d15d-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="4d15d-110">Metodo CreateConnection</span><span class="sxs-lookup"><span data-stu-id="4d15d-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="4d15d-111">Notifica al debugger che è stata creata una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="4d15d-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="4d15d-112">Metodo DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="4d15d-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="4d15d-113">Notifica al debugger che la connessione specificata è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="4d15d-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="4d15d-114">Metodo Exception</span><span class="sxs-lookup"><span data-stu-id="4d15d-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="4d15d-115">Notifica al debugger che è stata avviata una ricerca di un gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4d15d-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="4d15d-116">Metodo ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="4d15d-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="4d15d-117">Fornisce una notifica di stato durante il processo di rimozione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d15d-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="4d15d-118">Metodo FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="4d15d-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="4d15d-119">Notifica al debugger che l'esecuzione del codice è cambiata a una nuova versione di una funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="4d15d-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="4d15d-120">Metodo FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="4d15d-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="4d15d-121">Notifica al debugger che l'esecuzione del codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.</span><span class="sxs-lookup"><span data-stu-id="4d15d-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="4d15d-122">Metodo MDANotification</span><span class="sxs-lookup"><span data-stu-id="4d15d-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="4d15d-123">Fornisce la notifica che l'esecuzione del codice ha rilevato un messaggio assistente al debug gestito (MDA).</span><span class="sxs-lookup"><span data-stu-id="4d15d-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d15d-124">Note</span><span class="sxs-lookup"><span data-stu-id="4d15d-124">Remarks</span></span>  
 <span data-ttu-id="4d15d-125">L' `ICorDebugManagedCallback2` interfaccia estende l' `ICorDebugManagedCallback` interfaccia per gestire i nuovi eventi di debug introdotti nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4d15d-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="4d15d-126">Un debugger deve implementare `ICorDebugManagedCallback2` se esegue il debug di applicazioni .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4d15d-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="4d15d-127">Un'istanza di `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` viene passata come oggetto callback a [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="4d15d-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d15d-128">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4d15d-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d15d-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d15d-129">Requirements</span></span>  
 <span data-ttu-id="4d15d-130">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d15d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d15d-131">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4d15d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d15d-132">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d15d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d15d-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d15d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d15d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d15d-134">See also</span></span>

- [<span data-ttu-id="4d15d-135">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="4d15d-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4d15d-136">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4d15d-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4d15d-137">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="4d15d-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
