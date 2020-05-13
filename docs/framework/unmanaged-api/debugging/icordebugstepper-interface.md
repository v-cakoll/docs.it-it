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
ms.openlocfilehash: 622fdfa37c93e406950e73941775828ae4b112fa
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379427"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="41cae-102">Interfaccia ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="41cae-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="41cae-103">Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="41cae-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41cae-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="41cae-104">Methods</span></span>  
  
|<span data-ttu-id="41cae-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="41cae-105">Method</span></span>|<span data-ttu-id="41cae-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41cae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41cae-107">Metodo Deactivate</span><span class="sxs-lookup"><span data-stu-id="41cae-107">Deactivate Method</span></span>](icordebugstepper-deactivate-method.md)|<span data-ttu-id="41cae-108">Determina `ICorDebugStepper` l'annullamento dell'ultimo comando del passaggio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="41cae-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="41cae-109">Metodo IsActive</span><span class="sxs-lookup"><span data-stu-id="41cae-109">IsActive Method</span></span>](icordebugstepper-isactive-method.md)|<span data-ttu-id="41cae-110">Ottiene un valore che indica se l' `ICorDebugStepper` oggetto corrente esegue un passaggio.</span><span class="sxs-lookup"><span data-stu-id="41cae-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="41cae-111">Metodo SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="41cae-111">SetInterceptMask Method</span></span>](icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="41cae-112">Imposta un valore CorDebugIntercept che specifica i tipi di codice sottoposti a rientri.</span><span class="sxs-lookup"><span data-stu-id="41cae-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="41cae-113">Metodo SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="41cae-113">SetRangeIL Method</span></span>](icordebugstepper-setrangeil-method.md)|<span data-ttu-id="41cae-114">Imposta un valore che indica se le chiamate a [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) passano valori di argomento relativi al codice nativo o al codice MSIL (Microsoft Intermediate Language) del metodo di cui è in corso il passaggio.</span><span class="sxs-lookup"><span data-stu-id="41cae-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="41cae-115">Metodo SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="41cae-115">SetUnmappedStopMask Method</span></span>](icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="41cae-116">Imposta un valore CorDebugUnmappedStop che specifica il tipo di codice non mappato in cui l'esecuzione si arresterà.</span><span class="sxs-lookup"><span data-stu-id="41cae-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="41cae-117">Metodo Step</span><span class="sxs-lookup"><span data-stu-id="41cae-117">Step Method</span></span>](icordebugstepper-step-method.md)|<span data-ttu-id="41cae-118">Causa l' `ICorDebugStepper` esecuzione di questa operazione in un unico passaggio tramite il thread contenitore e, facoltativamente, per continuare a eseguire le funzioni singole che vengono chiamate all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="41cae-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="41cae-119">Metodo StepOut</span><span class="sxs-lookup"><span data-stu-id="41cae-119">StepOut Method</span></span>](icordebugstepper-stepout-method.md)|<span data-ttu-id="41cae-120">Determina l'esecuzione di questa operazione `ICorDebugStepper` in un singolo passaggio tramite il thread contenitore e il completamento quando il frame corrente restituisce il controllo al frame chiamante.</span><span class="sxs-lookup"><span data-stu-id="41cae-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="41cae-121">Metodo StepRange</span><span class="sxs-lookup"><span data-stu-id="41cae-121">StepRange Method</span></span>](icordebugstepper-steprange-method.md)|<span data-ttu-id="41cae-122">Determina l'esecuzione di questa operazione `ICorDebugStepper` in un singolo passaggio tramite il thread contenitore e la restituzione quando raggiunge il codice oltre l'ultimo intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="41cae-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41cae-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="41cae-123">Remarks</span></span>  
 <span data-ttu-id="41cae-124">L' `ICorDebugStepper` interfaccia svolge gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41cae-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="41cae-125">Funge da identificatore tra un comando Step emesso e il completamento del comando.</span><span class="sxs-lookup"><span data-stu-id="41cae-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="41cae-126">Fornisce un'interfaccia centrale per incapsulare tutti gli avanzamenti che possono essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="41cae-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="41cae-127">Consente di annullare in modo anomalo un'operazione di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="41cae-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="41cae-128">Possono essere presenti più stepper per thread.</span><span class="sxs-lookup"><span data-stu-id="41cae-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="41cae-129">Ad esempio, un punto di interruzione può essere raggiunto durante l'esecuzione di un'istruzione/routine di una funzione e l'utente può voler avviare una nuova operazione di esecuzione all'interno di tale funzione.</span><span class="sxs-lookup"><span data-stu-id="41cae-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="41cae-130">Spetta al debugger determinare come gestire questa situazione.</span><span class="sxs-lookup"><span data-stu-id="41cae-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="41cae-131">È possibile che il debugger desideri annullare l'operazione di avanzamento originale o annidare le due operazioni.</span><span class="sxs-lookup"><span data-stu-id="41cae-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="41cae-132">L' `ICorDebugStepper` interfaccia supporta entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="41cae-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="41cae-133">Uno stepper può eseguire la migrazione tra thread se il Common Language Runtime (CLR) esegue una chiamata con marshalling cross-threading.</span><span class="sxs-lookup"><span data-stu-id="41cae-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41cae-134">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="41cae-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41cae-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41cae-135">Requirements</span></span>  
 <span data-ttu-id="41cae-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41cae-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41cae-137">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41cae-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41cae-138">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41cae-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41cae-139">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41cae-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41cae-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41cae-140">See also</span></span>

- [<span data-ttu-id="41cae-141">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="41cae-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
