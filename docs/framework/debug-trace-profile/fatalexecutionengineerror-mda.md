---
title: MDA fatalExecutionEngineError
description: Esaminare l'assistente al debug gestito di fatalExecutionEngineError in .NET, che può essere attivato a causa di una chiusura imprevista di un processo.
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
ms.openlocfilehash: 0806d2eaa1752c88bebd03304fbe5c8094416a48
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415927"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="01421-103">MDA fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="01421-103">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="01421-104">L'assistente al debug gestito `fatalExecutionEngineError` viene attivato quando Common Language Runtime (CLR) rileva un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="01421-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="01421-105">Il processo viene terminato.</span><span class="sxs-lookup"><span data-stu-id="01421-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="01421-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="01421-106">Symptoms</span></span>  
 <span data-ttu-id="01421-107">Chiusura imprevista del processo.</span><span class="sxs-lookup"><span data-stu-id="01421-107">Unexpected process termination.</span></span> <span data-ttu-id="01421-108">Non è possibile identificare altri sintomi perché un errore CLR può verificarsi per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="01421-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="01421-109">Causa</span><span class="sxs-lookup"><span data-stu-id="01421-109">Cause</span></span>  
 <span data-ttu-id="01421-110">CLR è stato danneggiato in modo irreversibile.</span><span class="sxs-lookup"><span data-stu-id="01421-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="01421-111">La causa più frequente può essere data dal danneggiamento dei dati che può derivare da diversi problemi, quali chiamate a funzioni P/Invoke dal formato non corretto e passaggio di dati non validi a CLR.</span><span class="sxs-lookup"><span data-stu-id="01421-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="01421-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="01421-112">Resolution</span></span>  
 <span data-ttu-id="01421-113">L'identificazione del problema può essere agevolata dall'attivazione di altri assistenti.</span><span class="sxs-lookup"><span data-stu-id="01421-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="01421-114">Gli assistenti al debug gestito riportati di seguito possono essere particolarmente utili per una diagnosi del problema:</span><span class="sxs-lookup"><span data-stu-id="01421-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="01421-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="01421-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="01421-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="01421-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="01421-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="01421-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="01421-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="01421-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="01421-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="01421-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="01421-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="01421-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="01421-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="01421-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="01421-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="01421-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="01421-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="01421-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="01421-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="01421-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="01421-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="01421-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="01421-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="01421-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="01421-127">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="01421-127">Effect on the Runtime</span></span>  
 <span data-ttu-id="01421-128">Questo assistente al debug gestito non produce effetti sul comportamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="01421-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="01421-129">Output</span><span class="sxs-lookup"><span data-stu-id="01421-129">Output</span></span>  
 <span data-ttu-id="01421-130">L'indirizzo della funzione CLR che ha causato l'errore irreversibile, l'ID del thread in cui si è verificato l'errore e il codice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="01421-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="01421-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="01421-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01421-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="01421-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="01421-133">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="01421-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
