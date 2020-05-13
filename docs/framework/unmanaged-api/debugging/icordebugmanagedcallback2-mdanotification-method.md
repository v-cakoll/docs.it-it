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
ms.openlocfilehash: f850b3cd35fda8bd554b99e14553100008cb4eca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208525"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="82771-102">Metodo ICorDebugManagedCallback2::MDANotification</span><span class="sxs-lookup"><span data-stu-id="82771-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="82771-103">Fornisce la notifica che l'esecuzione del codice ha rilevato un assistente al debug gestito (MDA) nell'applicazione di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="82771-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82771-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82771-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82771-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82771-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="82771-106">in Puntatore a un'interfaccia ICorDebugController che espone il processo o il dominio dell'applicazione in cui si è verificato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="82771-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="82771-107">Un debugger non deve prevedere se il controller è un processo o un dominio dell'applicazione, anche se può sempre eseguire una query sull'interfaccia per eseguire una determinazione.</span><span class="sxs-lookup"><span data-stu-id="82771-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="82771-108">in Puntatore a un'interfaccia ICorDebugThread che espone il thread gestito in cui si è verificato l'evento di debug.</span><span class="sxs-lookup"><span data-stu-id="82771-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="82771-109">Se l'assistente al debug gestito è stato eseguito in un thread non gestito, il valore di `pThread` sarà null.</span><span class="sxs-lookup"><span data-stu-id="82771-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="82771-110">È necessario ottenere l'ID del thread del sistema operativo dall'oggetto MDA stesso.</span><span class="sxs-lookup"><span data-stu-id="82771-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="82771-111">in Puntatore a un'interfaccia [ICorDebugMDA](icordebugmda-interface.md) che espone le informazioni dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="82771-111">[in] A pointer to an [ICorDebugMDA](icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82771-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="82771-112">Remarks</span></span>  
 <span data-ttu-id="82771-113">Un assistente al debug gestito è un avviso euristico e non richiede alcuna azione esplicita del debugger ad eccezione della chiamata a [ICorDebugController:: continue](icordebugcontroller-continue-method.md) per riprendere l'esecuzione dell'applicazione di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="82771-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="82771-114">Il Common Language Runtime (CLR) può determinare quali MDA vengono attivati e quali dati si trovano in un determinato MDA in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="82771-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="82771-115">Pertanto, i debugger non devono compilare funzionalità che richiedono modelli di assistente al debug gestito specifici.</span><span class="sxs-lookup"><span data-stu-id="82771-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="82771-116">MDA può essere accodato e generato poco dopo che è stato rilevato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="82771-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="82771-117">Questo problema può verificarsi se il runtime deve attendere fino a quando non raggiunge un punto sicuro per l'attivazione dell'assistente al debug gestito, anziché eseguire l'assistente al debug gestito quando lo rileva.</span><span class="sxs-lookup"><span data-stu-id="82771-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="82771-118">Significa anche che il runtime può generare un certo numero di MDA in un unico set di callback in coda (analogamente a un'operazione di "associazione").</span><span class="sxs-lookup"><span data-stu-id="82771-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="82771-119">Un debugger deve rilasciare il riferimento a un' `ICorDebugMDA` istanza immediatamente dopo la restituzione dal `MDANotification` callback, per consentire a CLR di riciclare la memoria utilizzata da un assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="82771-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="82771-120">Il rilascio dell'istanza può migliorare le prestazioni in caso di generazione di molti MDA.</span><span class="sxs-lookup"><span data-stu-id="82771-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82771-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82771-121">Requirements</span></span>  
 <span data-ttu-id="82771-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82771-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82771-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82771-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82771-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82771-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82771-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82771-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82771-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82771-126">See also</span></span>

- [<span data-ttu-id="82771-127">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="82771-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="82771-128">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="82771-128">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="82771-129">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="82771-129">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
