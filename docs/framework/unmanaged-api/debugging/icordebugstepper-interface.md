---
title: ICorDebugStepper Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 266e8c664ac7c5efa1b199efc522f0b890e38e3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper-interface1"></a><span data-ttu-id="35a6b-102">ICorDebugStepper Interface1</span><span class="sxs-lookup"><span data-stu-id="35a6b-102">ICorDebugStepper Interface1</span></span>
<span data-ttu-id="35a6b-103">Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="35a6b-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35a6b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="35a6b-104">Methods</span></span>  
  
|<span data-ttu-id="35a6b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="35a6b-105">Method</span></span>|<span data-ttu-id="35a6b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35a6b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35a6b-107">Metodo Deactivate</span><span class="sxs-lookup"><span data-stu-id="35a6b-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="35a6b-108">Fa sì che `ICorDebugStepper` per annullare l'ultimo comando passaggio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="35a6b-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="35a6b-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="35a6b-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="35a6b-110">Ottiene un valore che indica se questo `ICorDebugStepper` è in esecuzione un passaggio.</span><span class="sxs-lookup"><span data-stu-id="35a6b-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="35a6b-111">Metodo SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="35a6b-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="35a6b-112">Imposta un valore CorDebugIntercept che specifica i tipi di codice che viene eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="35a6b-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="35a6b-113">Metodo SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="35a6b-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="35a6b-114">Imposta un valore che indica se le chiamate a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) passare i valori di argomento rispetto al codice nativo o codice di Microsoft intermediate language (MSIL) del metodo che viene eseguito il debug passo a tramite.</span><span class="sxs-lookup"><span data-stu-id="35a6b-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="35a6b-115">Metodo SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="35a6b-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="35a6b-116">Imposta un valore CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui verrà interrotta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="35a6b-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="35a6b-117">Metodo Step</span><span class="sxs-lookup"><span data-stu-id="35a6b-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="35a6b-118">Fa sì che `ICorDebugStepper` passo a passo del thread e, facoltativamente, per continuare l'esecuzione passo passo tramite le funzioni che vengono chiamate all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="35a6b-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="35a6b-119">Metodo StepOut</span><span class="sxs-lookup"><span data-stu-id="35a6b-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="35a6b-120">Fa sì che `ICorDebugStepper` passo a passo del thread e venga completato quando il frame corrente restituisce il controllo al frame chiamante.</span><span class="sxs-lookup"><span data-stu-id="35a6b-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="35a6b-121">Metodo StepRange</span><span class="sxs-lookup"><span data-stu-id="35a6b-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="35a6b-122">Fa sì che `ICorDebugStepper` passo a passo del thread e da restituire quando raggiunge il codice oltre l'ultimo degli intervalli specificati.</span><span class="sxs-lookup"><span data-stu-id="35a6b-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35a6b-123">Note</span><span class="sxs-lookup"><span data-stu-id="35a6b-123">Remarks</span></span>  
 <span data-ttu-id="35a6b-124">Il `ICorDebugStepper` interfaccia utilizza per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="35a6b-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="35a6b-125">Funge da identificatore tra un comando del passaggio che viene eseguito e il completamento del comando.</span><span class="sxs-lookup"><span data-stu-id="35a6b-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="35a6b-126">Fornisce un'interfaccia centrale per incapsulare tutti l'esecuzione di istruzioni che può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="35a6b-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="35a6b-127">Fornisce un modo per annullare in modo anomalo di un'operazione passo a passo.</span><span class="sxs-lookup"><span data-stu-id="35a6b-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="35a6b-128">Può essere presente più di un gestore di istruzioni per ogni thread.</span><span class="sxs-lookup"><span data-stu-id="35a6b-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="35a6b-129">Ad esempio, può essere raggiunto un punto di interruzione durante l'esecuzione su una funzione e l'utente potrebbe desiderare di avviare una nuova operazione passo a passo all'interno di tale funzione.</span><span class="sxs-lookup"><span data-stu-id="35a6b-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="35a6b-130">In questo caso, il debugger per determinare come gestire questa situazione.</span><span class="sxs-lookup"><span data-stu-id="35a6b-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="35a6b-131">Il debugger possibile annullare l'operazione passo a passo originale o annidare entrambe le operazioni.</span><span class="sxs-lookup"><span data-stu-id="35a6b-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="35a6b-132">Il `ICorDebugStepper` interfaccia supporta entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="35a6b-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="35a6b-133">Un gestore di istruzioni possono essere migrate tra thread se common language runtime (CLR) effettua una chiamata cross-thread sottoposta a marshalling.</span><span class="sxs-lookup"><span data-stu-id="35a6b-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35a6b-134">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="35a6b-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a6b-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35a6b-135">Requirements</span></span>  
 <span data-ttu-id="35a6b-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35a6b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a6b-137">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="35a6b-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35a6b-138">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35a6b-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35a6b-139">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a6b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a6b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35a6b-140">See Also</span></span>  
 [<span data-ttu-id="35a6b-141">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="35a6b-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
