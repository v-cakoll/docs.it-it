---
title: Interfaccia ICorDebugStepper
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212518"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="34587-102">Interfaccia ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="34587-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="34587-103">Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="34587-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34587-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="34587-104">Methods</span></span>  
  
|<span data-ttu-id="34587-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="34587-105">Method</span></span>|<span data-ttu-id="34587-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34587-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34587-107">Metodo Deactivate</span><span class="sxs-lookup"><span data-stu-id="34587-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="34587-108">Fa in modo che questo `ICorDebugStepper` per annullare l'ultimo comando passaggio ha ricevuto.</span><span class="sxs-lookup"><span data-stu-id="34587-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="34587-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="34587-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="34587-110">Ottiene un valore che indica se questo `ICorDebugStepper` è in esecuzione un passaggio.</span><span class="sxs-lookup"><span data-stu-id="34587-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="34587-111">Metodo SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="34587-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="34587-112">Imposta un valore CorDebugIntercept che specifica i tipi di codice che viene eseguita l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="34587-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="34587-113">Metodo SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="34587-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="34587-114">Imposta un valore che indica se le chiamate a [StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) passare i valori di argomento rispetto al codice nativo o per il codice Microsoft intermediate language (MSIL) del metodo che è in corso una alla volta.</span><span class="sxs-lookup"><span data-stu-id="34587-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="34587-115">Metodo SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="34587-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="34587-116">Imposta un valore CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui verrà interrotta l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34587-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="34587-117">Metodo Step</span><span class="sxs-lookup"><span data-stu-id="34587-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="34587-118">Fa in modo che questo `ICorDebugStepper` passo a passo del thread e, facoltativamente, per continuare il debug passo-passo tramite le funzioni che vengono chiamate all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="34587-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="34587-119">Metodo StepOut</span><span class="sxs-lookup"><span data-stu-id="34587-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="34587-120">Fa in modo che questo `ICorDebugStepper` passo a passo del thread di completata quando il frame corrente restituisce il controllo al chiama frame.</span><span class="sxs-lookup"><span data-stu-id="34587-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="34587-121">Metodo StepRange</span><span class="sxs-lookup"><span data-stu-id="34587-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="34587-122">Fa in modo che questo `ICorDebugStepper` passo a passo del thread e da restituire quando raggiunge il codice oltre l'ultimo degli intervalli specificati.</span><span class="sxs-lookup"><span data-stu-id="34587-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34587-123">Note</span><span class="sxs-lookup"><span data-stu-id="34587-123">Remarks</span></span>  
 <span data-ttu-id="34587-124">Il `ICorDebugStepper` interfaccia ha gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="34587-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="34587-125">Funge da identificatore tra un comando di passaggio che viene generato e il completamento del comando.</span><span class="sxs-lookup"><span data-stu-id="34587-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="34587-126">Fornisce un'interfaccia centrale per incapsulare tutte le istruzioni che può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="34587-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="34587-127">Fornisce un modo per annullare in modo anomalo un'operazione di debug passo a passo.</span><span class="sxs-lookup"><span data-stu-id="34587-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="34587-128">Può essere presente più di un gestore di istruzioni per ogni thread.</span><span class="sxs-lookup"><span data-stu-id="34587-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="34587-129">Ad esempio, può essere raggiunto un punto di interruzione durante l'esecuzione di istruzioni/routine di una funzione e l'utente può essere utile avviare una nuova operazione di debug passo a passo all'interno della funzione.</span><span class="sxs-lookup"><span data-stu-id="34587-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="34587-130">Spetta al debugger di determinare come gestire questa situazione.</span><span class="sxs-lookup"><span data-stu-id="34587-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="34587-131">Il debugger potrebbe voler annullare l'operazione di debug passo a passo originale o annidare le due operazioni.</span><span class="sxs-lookup"><span data-stu-id="34587-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="34587-132">Il `ICorDebugStepper` interfaccia supporta entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="34587-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="34587-133">Un gestore di istruzioni possono eseguire la migrazione tra i thread se common language runtime (CLR) effettua una chiamata di cross-thread sottoposta a marshalling.</span><span class="sxs-lookup"><span data-stu-id="34587-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34587-134">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="34587-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34587-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34587-135">Requirements</span></span>  
 <span data-ttu-id="34587-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34587-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34587-137">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34587-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34587-138">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34587-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34587-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34587-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34587-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34587-140">See also</span></span>

- [<span data-ttu-id="34587-141">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="34587-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
