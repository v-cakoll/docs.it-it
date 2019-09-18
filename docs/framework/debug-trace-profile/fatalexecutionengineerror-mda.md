---
title: MDA fatalExecutionEngineError
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fd58ae8f73fd932df641ea96a44ff618dd139e2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052799"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="c5103-102">MDA fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="c5103-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="c5103-103">L'assistente al debug gestito `fatalExecutionEngineError` viene attivato quando Common Language Runtime (CLR) rileva un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="c5103-103">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="c5103-104">Il processo viene terminato.</span><span class="sxs-lookup"><span data-stu-id="c5103-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c5103-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="c5103-105">Symptoms</span></span>  
 <span data-ttu-id="c5103-106">Chiusura imprevista del processo.</span><span class="sxs-lookup"><span data-stu-id="c5103-106">Unexpected process termination.</span></span> <span data-ttu-id="c5103-107">Non è possibile identificare altri sintomi perché un errore CLR può verificarsi per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="c5103-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c5103-108">Causa</span><span class="sxs-lookup"><span data-stu-id="c5103-108">Cause</span></span>  
 <span data-ttu-id="c5103-109">CLR è stato danneggiato in modo irreversibile.</span><span class="sxs-lookup"><span data-stu-id="c5103-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="c5103-110">La causa più frequente può essere data dal danneggiamento dei dati che può derivare da diversi problemi, quali chiamate a funzioni P/Invoke dal formato non corretto e passaggio di dati non validi a CLR.</span><span class="sxs-lookup"><span data-stu-id="c5103-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c5103-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="c5103-111">Resolution</span></span>  
 <span data-ttu-id="c5103-112">L'identificazione del problema può essere agevolata dall'attivazione di altri assistenti.</span><span class="sxs-lookup"><span data-stu-id="c5103-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="c5103-113">Gli assistenti al debug gestito riportati di seguito possono essere particolarmente utili per una diagnosi del problema:</span><span class="sxs-lookup"><span data-stu-id="c5103-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="c5103-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="c5103-114">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="c5103-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="c5103-115">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="c5103-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="c5103-116">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="c5103-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="c5103-117">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="c5103-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="c5103-118">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="c5103-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="c5103-119">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="c5103-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="c5103-120">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="c5103-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="c5103-121">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="c5103-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="c5103-122">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="c5103-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="c5103-123">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="c5103-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="c5103-124">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="c5103-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="c5103-125">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c5103-126">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c5103-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="c5103-127">Questo assistente al debug gestito non produce effetti sul comportamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="c5103-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c5103-128">Output</span><span class="sxs-lookup"><span data-stu-id="c5103-128">Output</span></span>  
 <span data-ttu-id="c5103-129">L'indirizzo della funzione CLR che ha causato l'errore irreversibile, l'ID del thread in cui si è verificato l'errore e il codice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="c5103-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c5103-130">Configurazione</span><span class="sxs-lookup"><span data-stu-id="c5103-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5103-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5103-131">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="c5103-132">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="c5103-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
