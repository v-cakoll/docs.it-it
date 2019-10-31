---
title: Metodo ICorDebugManagedCallback2::MDANotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131453"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="ce7d9-102">Metodo ICorDebugManagedCallback2::MDANotification</span><span class="sxs-lookup"><span data-stu-id="ce7d9-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="ce7d9-103">Fornisce la notifica che l'esecuzione del codice ha rilevato un assistente al debug gestito (MDA) nell'applicazione di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce7d9-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce7d9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce7d9-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="ce7d9-106">in Puntatore a un'interfaccia ICorDebugController che espone il processo o il dominio dell'applicazione in cui si è verificato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="ce7d9-107">Un debugger non deve prevedere se il controller è un processo o un dominio dell'applicazione, anche se può sempre eseguire una query sull'interfaccia per eseguire una determinazione.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ce7d9-108">in Puntatore a un'interfaccia ICorDebugThread che espone il thread gestito in cui si è verificato l'evento di debug.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="ce7d9-109">Se l'assistente al debug gestito è stato eseguito in un thread non gestito, il valore di `pThread` sarà null.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="ce7d9-110">È necessario ottenere l'ID del thread del sistema operativo dall'oggetto MDA stesso.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="ce7d9-111">in Puntatore a un'interfaccia [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) che espone le informazioni dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce7d9-112">Note</span><span class="sxs-lookup"><span data-stu-id="ce7d9-112">Remarks</span></span>  
 <span data-ttu-id="ce7d9-113">Un assistente al debug gestito è un avviso euristico e non richiede alcuna azione esplicita del debugger ad eccezione della chiamata a [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per riprendere l'esecuzione dell'applicazione di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="ce7d9-114">Il Common Language Runtime (CLR) può determinare quali MDA vengono attivati e quali dati si trovano in un determinato MDA in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="ce7d9-115">Pertanto, i debugger non devono compilare funzionalità che richiedono modelli di assistente al debug gestito specifici.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="ce7d9-116">MDA può essere accodato e generato poco dopo che è stato rilevato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="ce7d9-117">Questo problema può verificarsi se il runtime deve attendere fino a quando non raggiunge un punto sicuro per l'attivazione dell'assistente al debug gestito, anziché eseguire l'assistente al debug gestito quando lo rileva.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="ce7d9-118">Significa anche che il runtime può generare un certo numero di MDA in un unico set di callback in coda (analogamente a un'operazione di "associazione").</span><span class="sxs-lookup"><span data-stu-id="ce7d9-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="ce7d9-119">Un debugger deve rilasciare il riferimento a un'istanza di `ICorDebugMDA` immediatamente dopo la restituzione dal callback `MDANotification`, per consentire a CLR di riciclare la memoria utilizzata da un assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="ce7d9-120">Il rilascio dell'istanza può migliorare le prestazioni in caso di generazione di molti MDA.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7d9-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce7d9-121">Requirements</span></span>  
 <span data-ttu-id="ce7d9-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce7d9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7d9-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce7d9-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce7d9-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce7d9-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce7d9-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7d9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7d9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce7d9-126">See also</span></span>

- [<span data-ttu-id="ce7d9-127">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="ce7d9-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ce7d9-128">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="ce7d9-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="ce7d9-129">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ce7d9-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
