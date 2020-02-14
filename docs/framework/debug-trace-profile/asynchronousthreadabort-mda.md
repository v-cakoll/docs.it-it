---
title: MDA asynchronousThreadAbort
ms.date: 03/30/2017
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
ms.openlocfilehash: d0c78e6d52ae4a5b3a24e0bb4278b2e8a1b98751
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217584"
---
# <a name="asynchronousthreadabort-mda"></a><span data-ttu-id="bbfcc-102">MDA asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="bbfcc-102">asynchronousThreadAbort MDA</span></span>
<span data-ttu-id="bbfcc-103">L'assistente al debug gestito `asynchronousThreadAbort` viene attivato quando un thread tenta di introdurre un'interruzione asincrona in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-103">The `asynchronousThreadAbort` managed debugging assistant (MDA) is activated when a thread attempts to introduce an asynchronous abort into another thread.</span></span> <span data-ttu-id="bbfcc-104">`asynchronousThreadAbort` non viene invece attivato da interruzioni sincrone dei thread.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-104">Synchronous thread aborts do not activate the `asynchronousThreadAbort` MDA.</span></span>

## <a name="symptoms"></a><span data-ttu-id="bbfcc-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="bbfcc-105">Symptoms</span></span>
 <span data-ttu-id="bbfcc-106">Quando il thread principale di un'applicazione viene interrotto, l'applicazione si arresta in modo anomalo e viene generata un'eccezione <xref:System.Threading.ThreadAbortException> non gestita.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-106">An application crashes with an unhandled <xref:System.Threading.ThreadAbortException> when the main application thread is aborted.</span></span> <span data-ttu-id="bbfcc-107">Se l'esecuzione dell'applicazione dovesse continuare, le conseguenze potrebbero essere peggiori di un arresto anomalo. Si potrebbe infatti verificare un ulteriore danneggiamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-107">If the application were to continue to execute, the consequences might be worse than the application crashing, possibly resulting in further data corruption.</span></span>

 <span data-ttu-id="bbfcc-108">Con molta probabilità operazioni che dovevano essere atomiche sono state interrotte dopo il completamento parziale, lasciando i dati dell'applicazione in uno stato imprevedibile.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-108">Operations meant to be atomic have likely been interrupted after partial completion, leaving application data in an unpredictable state.</span></span> <span data-ttu-id="bbfcc-109">È possibile che venga generata un'eccezione <xref:System.Threading.ThreadAbortException> da punti apparentemente casuali nell'esecuzione del codice, spesso in posizioni in cui non è prevista la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-109">A <xref:System.Threading.ThreadAbortException> can be generated from seemingly random points in the execution of code, often in places from which an exception is not expected to arise.</span></span> <span data-ttu-id="bbfcc-110">Il codice può non essere in grado di gestire questo tipo di eccezioni, generando così uno stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-110">The code might not be capable of handling such an exception, resulting in a corrupt state.</span></span>

 <span data-ttu-id="bbfcc-111">I sintomi possono variare ampiamente a causa della casualità implicita nel problema.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-111">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>

## <a name="cause"></a><span data-ttu-id="bbfcc-112">Causa</span><span class="sxs-lookup"><span data-stu-id="bbfcc-112">Cause</span></span>
 <span data-ttu-id="bbfcc-113">Il codice di un thread ha chiamato il metodo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> su un thread di destinazione per introdurre un'interruzione di thread asincrona.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-113">Code in one thread called the <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method on a target thread to introduce an asynchronous thread abort.</span></span> <span data-ttu-id="bbfcc-114">L'interruzione è asincrona perché il codice che effettua la chiamata a <xref:System.Threading.Thread.Abort%2A> è in esecuzione su un thread diverso da quello di destinazione dell'operazione di interruzione.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-114">The thread abort is asynchronous because the code that makes the call to <xref:System.Threading.Thread.Abort%2A> is running on a different thread than the target of the abort operation.</span></span> <span data-ttu-id="bbfcc-115">In genere, le interruzioni sincrone dei thread non causano problemi in quanto il thread che esegue il metodo <xref:System.Threading.Thread.Abort%2A> effettua questa operazione solo in un checkpoint sicuro in cui lo stato dell'applicazione è coerente.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-115">Synchronous thread aborts should not cause a problem because the thread performing the <xref:System.Threading.Thread.Abort%2A> should have done so only at a safe checkpoint where application state is consistent.</span></span>

 <span data-ttu-id="bbfcc-116">Le interruzioni asincrone dei thread generano invece un problema poiché vengono elaborate in punti imprevisti nell'esecuzione del thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-116">Asynchronous thread aborts present a problem because they are processed at unpredictable points in the target thread's execution.</span></span> <span data-ttu-id="bbfcc-117">Per evitare questo problema, il codice scritto per essere eseguito su un thread che può essere interrotto in questo modo deve poter gestire un'eccezione <xref:System.Threading.ThreadAbortException> pressoché in corrispondenza di ogni riga di codice, prestando attenzione a ripristinare lo stato di coerenza dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-117">To avoid this, code written to run on a thread that might be aborted in this manner would need to handle a <xref:System.Threading.ThreadAbortException> at almost every line of code, taking care to put application data back into a consistent state.</span></span> <span data-ttu-id="bbfcc-118">Non è realistico, tuttavia, prevedere la scrittura di codice tenendo presente questo problema o la protezione da tutti possibili rischi.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-118">It is not realistic to expect code to be written with this problem in mind or to write code that protects against all possible circumstances.</span></span>

 <span data-ttu-id="bbfcc-119">Le chiamate a codice non gestito e a blocchi `finally` non vengono interrotte in modo asincrono, ma all'uscita da una di queste categorie.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-119">Calls into unmanaged code and `finally` blocks will not be aborted asynchronously but immediately upon exit from one of these categories.</span></span>

 <span data-ttu-id="bbfcc-120">È possibile che la causa sia difficile da determinare a causa della casualità implicita nel problema.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-120">The cause might be difficult to determine due to the randomness inherent to the problem.</span></span>

## <a name="resolution"></a><span data-ttu-id="bbfcc-121">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bbfcc-121">Resolution</span></span>
 <span data-ttu-id="bbfcc-122">Evitare la progettazione di codice che richieda l'utilizzo di interruzioni asincrone dei thread.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-122">Avoid code design that requires the use of asynchronous thread aborts.</span></span> <span data-ttu-id="bbfcc-123">Per l'interruzione di un thread di destinazione esistono vari approcci più appropriati che non richiedono una chiamata al metodo <xref:System.Threading.Thread.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-123">There are several approaches more appropriate for interruption of a target thread that do not require a call to <xref:System.Threading.Thread.Abort%2A>.</span></span> <span data-ttu-id="bbfcc-124">L'approccio più sicuro prevede l'introduzione di un meccanismo, ad esempio una proprietà comune, che segnali al thread di destinazione di richiedere un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-124">The safest is to introduce a mechanism, such as a common property, that signals the target thread to request an interrupt.</span></span> <span data-ttu-id="bbfcc-125">Il thread di destinazione verifica il segnale in determinati checkpoint sicuri e,</span><span class="sxs-lookup"><span data-stu-id="bbfcc-125">The target thread checks the signal at certain safe checkpoints.</span></span> <span data-ttu-id="bbfcc-126">se rileva una richiesta di interruzione, viene chiuso correttamente.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-126">If it notices that an interrupt has been requested, it can shut down gracefully.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="bbfcc-127">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="bbfcc-127">Effect on the Runtime</span></span>
 <span data-ttu-id="bbfcc-128">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-128">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="bbfcc-129">Si limita a generare un report dei dati relativi alle interruzioni asincrone dei thread.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-129">It only reports data about asynchronous thread aborts.</span></span>

## <a name="output"></a><span data-ttu-id="bbfcc-130">Output</span><span class="sxs-lookup"><span data-stu-id="bbfcc-130">Output</span></span>
 <span data-ttu-id="bbfcc-131">L'assistente al debug gestito segnala l'ID del thread che esegue l'interruzione e l'ID del thread di destinazione dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-131">The MDA reports the ID of the thread performing the abort and the ID of the thread that is the target of the abort.</span></span> <span data-ttu-id="bbfcc-132">I due ID non coincideranno mai perché questo tipo di output viene generato solo per le interruzioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-132">These will never be the same because this is limited to asynchronous aborts.</span></span>

## <a name="configuration"></a><span data-ttu-id="bbfcc-133">Configurazione</span><span class="sxs-lookup"><span data-stu-id="bbfcc-133">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a><span data-ttu-id="bbfcc-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbfcc-134">Example</span></span>
 <span data-ttu-id="bbfcc-135">L'attivazione dell'assistente al debug gestito `asynchronousThreadAbort` richiede solo una chiamata al metodo <xref:System.Threading.Thread.Abort%2A> su un altro thread in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-135">Activating the `asynchronousThreadAbort` MDA requires only a call to <xref:System.Threading.Thread.Abort%2A> on a separate running thread.</span></span> <span data-ttu-id="bbfcc-136">Considerare le conseguenze nel caso in cui il contenuto della funzione di avvio del thread corrispondesse a un insieme di operazioni più complesse che potrebbero essere interrotte in modo anomalo in un qualsiasi punto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="bbfcc-136">Consider the consequences if the contents of the thread start function were a set of more complex operations which might be interrupted at any arbitrary point by the abort.</span></span>

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a><span data-ttu-id="bbfcc-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbfcc-137">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="bbfcc-138">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="bbfcc-138">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
