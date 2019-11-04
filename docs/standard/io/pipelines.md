---
title: Pipeline di I/O-.NET
description: Informazioni su come usare in modo efficiente le pipeline di I/O in .NET ed evitare problemi nel codice.
ms.date: 10/01/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: 54b5f97aca131f52b9b5d9f54d7fa5ec00ba3d5b
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423668"
---
# <a name="systemiopipelines-in-net"></a><span data-ttu-id="04459-103">System. IO. Pipelines in .NET</span><span class="sxs-lookup"><span data-stu-id="04459-103">System.IO.Pipelines in .NET</span></span>

<span data-ttu-id="04459-104"><xref:System.IO.Pipelines> è una nuova libreria progettata per semplificare l'esecuzione di operazioni di I/O a prestazioni elevate in .NET.</span><span class="sxs-lookup"><span data-stu-id="04459-104"><xref:System.IO.Pipelines> is a new library that is designed to make it easier to do high-performance I/O in .NET.</span></span> <span data-ttu-id="04459-105">Si tratta di una libreria destinata a .NET Standard che funziona in tutte le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="04459-105">It’s a library targeting .NET Standard that works on all .NET implementations.</span></span>

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a><span data-ttu-id="04459-106">Quale problema risolve System. IO. Pipelines</span><span class="sxs-lookup"><span data-stu-id="04459-106">What problem does System.IO.Pipelines solve</span></span>

<!-- corner case doesn't MT (machine translate)   -->
<span data-ttu-id="04459-107">Le app che analizzano i dati di streaming sono costituite da codice standard con molti flussi di codice specializzati e insoliti.</span><span class="sxs-lookup"><span data-stu-id="04459-107">Apps that parse streaming data are composed of boilerplate code having many specialized and unusual code flows.</span></span> <span data-ttu-id="04459-108">Il codice standard e del case speciale è complesso e difficile da gestire.</span><span class="sxs-lookup"><span data-stu-id="04459-108">The boilerplate and special case code is complex and difficult to maintain.</span></span>

<span data-ttu-id="04459-109">`System.IO.Pipelines` è stato progettato per:</span><span class="sxs-lookup"><span data-stu-id="04459-109">`System.IO.Pipelines` was architected to:</span></span>

* <span data-ttu-id="04459-110">Analisi delle prestazioni elevate dei dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="04459-110">Have high performance parsing streaming data.</span></span>
* <span data-ttu-id="04459-111">Ridurre la complessità del codice.</span><span class="sxs-lookup"><span data-stu-id="04459-111">Reduce code complexity.</span></span>

<span data-ttu-id="04459-112">Il codice seguente è tipico per un server TCP che riceve messaggi delimitati da righe (delimitati da `'\n'`) da un client:</span><span class="sxs-lookup"><span data-stu-id="04459-112">The following code is typical for a TCP server that receives line-delimited messages (delimited by `'\n'`) from a client:</span></span>

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

<span data-ttu-id="04459-113">Il codice precedente presenta diversi problemi:</span><span class="sxs-lookup"><span data-stu-id="04459-113">The preceding code has several problems:</span></span>

* <span data-ttu-id="04459-114">L'intero messaggio (fine riga) potrebbe non essere ricevuto in una singola chiamata a `ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="04459-114">The entire message (end of line) might not be received in a single call to `ReadAsync`.</span></span>
* <span data-ttu-id="04459-115">Viene ignorato il risultato di `stream.ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="04459-115">It's ignoring the result of `stream.ReadAsync`.</span></span> <span data-ttu-id="04459-116">`stream.ReadAsync` restituisce la quantità di dati letti.</span><span class="sxs-lookup"><span data-stu-id="04459-116">`stream.ReadAsync` returns how much data was read.</span></span>
* <span data-ttu-id="04459-117">Non gestisce il caso in cui vengono lette più righe in una singola chiamata `ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="04459-117">It doesn't handle the case where multiple lines are read in a single `ReadAsync` call.</span></span>
* <span data-ttu-id="04459-118">Alloca una matrice `byte` a ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="04459-118">It allocates a `byte` array with each read.</span></span>

<span data-ttu-id="04459-119">Per risolvere i problemi precedenti, sono necessarie le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="04459-119">To fix the preceding problems, the following changes are required:</span></span>

* <span data-ttu-id="04459-120">Memorizza nel buffer i dati in arrivo fino a quando non viene trovata una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="04459-120">Buffer the incoming data until a new line is found.</span></span>
* <span data-ttu-id="04459-121">Analizza tutte le righe restituite nel buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-121">Parse all the lines returned in the buffer.</span></span>
* <span data-ttu-id="04459-122">È possibile che la riga sia maggiore di 1 KB (1024 byte).</span><span class="sxs-lookup"><span data-stu-id="04459-122">It's possible that the line is bigger than 1 KB (1024 bytes).</span></span> <span data-ttu-id="04459-123">Il codice deve ridimensionare il buffer di input fino a quando non viene trovato il delimitatore per adattarsi alla riga completa all'interno del buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-123">The code needs to resize the input buffer until the delimiter is found in order to fit the complete line inside the buffer.</span></span>

  * <span data-ttu-id="04459-124">Se il buffer viene ridimensionato, vengono apportate più copie del buffer mentre le righe più lunghe vengono visualizzate nell'input.</span><span class="sxs-lookup"><span data-stu-id="04459-124">If the buffer is resized, more buffer copies are made as longer lines appear in the input.</span></span>
  * <span data-ttu-id="04459-125">Per ridurre lo spazio sprecato, compattare il buffer utilizzato per la lettura delle righe.</span><span class="sxs-lookup"><span data-stu-id="04459-125">To reduce wasted space, compact the buffer used for reading lines.</span></span>

* <span data-ttu-id="04459-126">Prendere in considerazione l'uso del pool di buffer per evitare di allocare ripetutamente memoria.</span><span class="sxs-lookup"><span data-stu-id="04459-126">Consider using buffer pooling to avoid allocating memory repeatedly.</span></span>
* <span data-ttu-id="04459-127">Il codice seguente risolve alcuni di questi problemi:</span><span class="sxs-lookup"><span data-stu-id="04459-127">The following code addresses some of these problems:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs?name=snippet)]

<span data-ttu-id="04459-128">Il codice precedente è complesso e non risolve tutti i problemi identificati.</span><span class="sxs-lookup"><span data-stu-id="04459-128">The previous code is complex and doesn't address all the problems identified.</span></span> <span data-ttu-id="04459-129">Una rete ad alte prestazioni in genere significa scrivere codice molto complesso per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="04459-129">High-performance networking usually means writing very complex code to maximize performance.</span></span> <span data-ttu-id="04459-130">`System.IO.Pipelines` è stato progettato per semplificare la scrittura di questo tipo di codice.</span><span class="sxs-lookup"><span data-stu-id="04459-130">`System.IO.Pipelines` was designed to make writing this type of code easier.</span></span>

## <a name="pipe"></a><span data-ttu-id="04459-131">Pipe</span><span class="sxs-lookup"><span data-stu-id="04459-131">Pipe</span></span>

<span data-ttu-id="04459-132">La classe <xref:System.IO.Pipelines.Pipe> può essere usata per creare una coppia `PipeWriter/PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="04459-132">The <xref:System.IO.Pipelines.Pipe> class can be used to create a `PipeWriter/PipeReader` pair.</span></span> <span data-ttu-id="04459-133">Tutti i dati scritti in `PipeWriter` sono disponibili nell'`PipeReader`:</span><span class="sxs-lookup"><span data-stu-id="04459-133">All data written into the `PipeWriter` is available in the `PipeReader`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet2)]

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a><span data-ttu-id="04459-134">Utilizzo di base pipe</span><span class="sxs-lookup"><span data-stu-id="04459-134">Pipe basic usage</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet)]

<span data-ttu-id="04459-135">Sono disponibili due cicli:</span><span class="sxs-lookup"><span data-stu-id="04459-135">There are two loops:</span></span>

* <span data-ttu-id="04459-136">`FillPipeAsync` legge dal `Socket` e scrive nel `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="04459-136">`FillPipeAsync` reads from the `Socket` and writes to the `PipeWriter`.</span></span>
* <span data-ttu-id="04459-137">`ReadPipeAsync` legge dal `PipeReader` e analizza le righe in ingresso.</span><span class="sxs-lookup"><span data-stu-id="04459-137">`ReadPipeAsync` reads from the `PipeReader` and parses incoming lines.</span></span>

<span data-ttu-id="04459-138">Nessun buffer esplicito allocato.</span><span class="sxs-lookup"><span data-stu-id="04459-138">There are no explicit buffers allocated.</span></span> <span data-ttu-id="04459-139">La gestione del buffer viene delegata alle implementazioni `PipeReader` e `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="04459-139">All buffer management is delegated to the `PipeReader` and `PipeWriter` implementations.</span></span> <span data-ttu-id="04459-140">La delega della gestione del buffer rende più semplice l'utilizzo del codice per concentrarsi esclusivamente sulla logica di business.</span><span class="sxs-lookup"><span data-stu-id="04459-140">Delegating buffer management makes it easier for consuming code to focus solely on the business logic.</span></span>

<span data-ttu-id="04459-141">Nel primo ciclo:</span><span class="sxs-lookup"><span data-stu-id="04459-141">In the first loop:</span></span>

* <span data-ttu-id="04459-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> viene chiamato per ottenere la memoria dal writer sottostante.</span><span class="sxs-lookup"><span data-stu-id="04459-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> is called to get memory from the underlying writer.</span></span>
* <span data-ttu-id="04459-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> viene chiamato per indicare al `PipeWriter` la quantità di dati scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> is called to tell the `PipeWriter` how much data was written to the buffer.</span></span>
* <span data-ttu-id="04459-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> viene chiamato per rendere i dati disponibili per l'`PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="04459-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> is called to make the data available to the `PipeReader`.</span></span>

<span data-ttu-id="04459-145">Nel secondo ciclo, il `PipeReader` utilizza i buffer scritti da `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="04459-145">In the second loop, the `PipeReader` consumes the buffers written by `PipeWriter`.</span></span> <span data-ttu-id="04459-146">I buffer provengono dal socket.</span><span class="sxs-lookup"><span data-stu-id="04459-146">The buffers come from the socket.</span></span> <span data-ttu-id="04459-147">La chiamata a `PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="04459-147">The call to `PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="04459-148">Restituisce un <xref:System.IO.Pipelines.ReadResult> che contiene due informazioni importanti:</span><span class="sxs-lookup"><span data-stu-id="04459-148">Returns a <xref:System.IO.Pipelines.ReadResult> that contains two important pieces of information:</span></span>

  * <span data-ttu-id="04459-149">Dati letti nel formato `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="04459-149">The data that was read in the form of `ReadOnlySequence<byte>`.</span></span>
  * <span data-ttu-id="04459-150">Valore booleano `IsCompleted` che indica se è stata raggiunta la fine dei dati (EOF).</span><span class="sxs-lookup"><span data-stu-id="04459-150">A boolean `IsCompleted` that indicates if the end of data (EOF) has been reached.</span></span>

<span data-ttu-id="04459-151">Dopo aver individuato il delimitatore di fine riga (EOL) e aver analizzato la riga:</span><span class="sxs-lookup"><span data-stu-id="04459-151">After finding the end of line (EOL) delimiter and parsing the line:</span></span>

* <span data-ttu-id="04459-152">La logica elabora il buffer per ignorare ciò che è già stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="04459-152">The logic processes the buffer to skip what's already processed.</span></span>
* <span data-ttu-id="04459-153">viene chiamato `PipeReader.AdvanceTo` per indicare al `PipeReader` la quantità di dati utilizzata ed esaminata.</span><span class="sxs-lookup"><span data-stu-id="04459-153">`PipeReader.AdvanceTo` is called to tell the `PipeReader` how much data has been consumed and examined.</span></span>

<span data-ttu-id="04459-154">I cicli Reader e writer terminano chiamando `Complete`.</span><span class="sxs-lookup"><span data-stu-id="04459-154">The reader and writer loops end by calling `Complete`.</span></span> <span data-ttu-id="04459-155">`Complete` consente alla pipe sottostante di rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="04459-155">`Complete` lets the underlying Pipe release the memory it allocated.</span></span>

### <a name="backpressure-and-flow-control"></a><span data-ttu-id="04459-156">Backpressure e controllo di flusso</span><span class="sxs-lookup"><span data-stu-id="04459-156">Backpressure and flow control</span></span>

<span data-ttu-id="04459-157">Idealmente, la lettura e l'analisi collaborano tra loro:</span><span class="sxs-lookup"><span data-stu-id="04459-157">Ideally, reading and parsing work together:</span></span>

* <span data-ttu-id="04459-158">Il thread di scrittura utilizza i dati dalla rete e li inserisce nei buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-158">The writing thread consumes data from the network and puts it in buffers.</span></span>
* <span data-ttu-id="04459-159">Il thread di analisi è responsabile della costruzione delle strutture di dati appropriate.</span><span class="sxs-lookup"><span data-stu-id="04459-159">The parsing thread is responsible for constructing the appropriate data structures.</span></span>

<span data-ttu-id="04459-160">In genere, l'analisi impiega più tempo rispetto alla semplice copia di blocchi di dati dalla rete:</span><span class="sxs-lookup"><span data-stu-id="04459-160">Typically, parsing takes more time than just copying blocks of data from the network:</span></span>

* <span data-ttu-id="04459-161">Il thread di lettura precede il thread di analisi.</span><span class="sxs-lookup"><span data-stu-id="04459-161">The reading thread gets ahead of the parsing thread.</span></span>
* <span data-ttu-id="04459-162">Il thread di lettura deve rallentare o allocare più memoria per archiviare i dati per il thread di analisi.</span><span class="sxs-lookup"><span data-stu-id="04459-162">The reading thread has to either slow down or allocate more memory to store the data for the parsing thread.</span></span>

<span data-ttu-id="04459-163">Per ottenere prestazioni ottimali, c'è un equilibrio tra le pause frequenti e l'allocazione di ulteriore memoria.</span><span class="sxs-lookup"><span data-stu-id="04459-163">For optimal performance, there's a balance between frequent pauses and allocating more memory.</span></span>

<span data-ttu-id="04459-164">Per risolvere il problema precedente, il `Pipe` ha due impostazioni per controllare il flusso di dati:</span><span class="sxs-lookup"><span data-stu-id="04459-164">To solve the preceding problem, the `Pipe` has two settings to control the flow of data:</span></span>

* <span data-ttu-id="04459-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: determina la quantità di dati che devono essere memorizzati nel buffer prima che le chiamate a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pausa.</span><span class="sxs-lookup"><span data-stu-id="04459-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determines how much data should be buffered before calls to <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pause.</span></span>
* <span data-ttu-id="04459-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: determina la quantità di dati che il lettore deve osservare prima che le chiamate a `PipeWriter.FlushAsync` riprendano.</span><span class="sxs-lookup"><span data-stu-id="04459-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determines how much data the reader has to observe before calls to `PipeWriter.FlushAsync` resume.</span></span>

![Diagramma con ResumeWriterThreshold e PauseWriterThreshold](./media/pipelines/resume-pause.png)

<span data-ttu-id="04459-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="04459-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="04459-169">Restituisce un `ValueTask<FlushResult>` incompleto quando la quantità di dati nell'`Pipe` incrocia `PauseWriterThreshold`.</span><span class="sxs-lookup"><span data-stu-id="04459-169">Returns an incomplete `ValueTask<FlushResult>` when the amount of data in the `Pipe` crosses `PauseWriterThreshold`.</span></span>
* <span data-ttu-id="04459-170">Completa `ValueTask<FlushResult>` quando diventa inferiore `ResumeWriterThreshold`.</span><span class="sxs-lookup"><span data-stu-id="04459-170">Completes `ValueTask<FlushResult>` when it becomes lower than `ResumeWriterThreshold`.</span></span>

<span data-ttu-id="04459-171">Vengono usati due valori per impedire il ciclo rapido, che può verificarsi se si usa un valore.</span><span class="sxs-lookup"><span data-stu-id="04459-171">Two values are used to prevent rapid cycling, which can occur if one value is used.</span></span>

### <a name="examples"></a><span data-ttu-id="04459-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="04459-172">Examples</span></span>

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a><span data-ttu-id="04459-173">PipeScheduler</span><span class="sxs-lookup"><span data-stu-id="04459-173">PipeScheduler</span></span>

<span data-ttu-id="04459-174">In genere, quando si usa `async` e `await`, il codice asincrono riprende in un <xref:System.Threading.Tasks.TaskScheduler> o nel <xref:System.Threading.SynchronizationContext> corrente.</span><span class="sxs-lookup"><span data-stu-id="04459-174">Typically when using `async` and `await`, asynchronous code resumes on either on a <xref:System.Threading.Tasks.TaskScheduler> or on the current  <xref:System.Threading.SynchronizationContext>.</span></span>

<span data-ttu-id="04459-175">Quando si eseguono operazioni di I/O, è importante avere un controllo accurato sulla posizione in cui viene eseguito l'i/O.</span><span class="sxs-lookup"><span data-stu-id="04459-175">When doing I/O, it's important to have fine-grained control over where the I/O is performed.</span></span> <span data-ttu-id="04459-176">Questo controllo consente di sfruttare le cache della CPU in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="04459-176">This control allows taking advantage of CPU caches effectively.</span></span> <span data-ttu-id="04459-177">Una memorizzazione nella cache efficiente è essenziale per app ad alte prestazioni, come i server Web.</span><span class="sxs-lookup"><span data-stu-id="04459-177">Efficient caching is critical for high-performance apps like web servers.</span></span> <span data-ttu-id="04459-178"><xref:System.IO.Pipelines.PipeScheduler> fornisce il controllo su dove vengono eseguiti i callback asincroni.</span><span class="sxs-lookup"><span data-stu-id="04459-178"><xref:System.IO.Pipelines.PipeScheduler> provides control over where asynchronous callbacks run.</span></span> <span data-ttu-id="04459-179">Per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="04459-179">By default:</span></span>

* <span data-ttu-id="04459-180">Viene utilizzato il <xref:System.Threading.SynchronizationContext> corrente.</span><span class="sxs-lookup"><span data-stu-id="04459-180">The current <xref:System.Threading.SynchronizationContext> is used.</span></span>
* <span data-ttu-id="04459-181">Se non è presente `SynchronizationContext`, usa il pool di thread per eseguire i callback.</span><span class="sxs-lookup"><span data-stu-id="04459-181">If there's no `SynchronizationContext`, it uses the thread pool to run callbacks.</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Program.cs?name=snippet)]

<span data-ttu-id="04459-182">[PipeScheduler. ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) è l'implementazione <xref:System.IO.Pipelines.PipeScheduler> che accoda i callback al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="04459-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) is the <xref:System.IO.Pipelines.PipeScheduler> implementation that queues callbacks to the thread pool.</span></span> <span data-ttu-id="04459-183">`PipeScheduler.ThreadPool` è il valore predefinito e generalmente la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="04459-183">`PipeScheduler.ThreadPool` is the default and generally the best choice.</span></span> <span data-ttu-id="04459-184">[PipeScheduler. inline](xref:System.IO.Pipelines.PipeScheduler.Inline) può causare conseguenze impreviste, ad esempio i deadlock.</span><span class="sxs-lookup"><span data-stu-id="04459-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) can cause unintended consequences such as deadlocks.</span></span>

### <a name="pipe-reset"></a><span data-ttu-id="04459-185">Reimpostazione pipe</span><span class="sxs-lookup"><span data-stu-id="04459-185">Pipe reset</span></span>

<span data-ttu-id="04459-186">Spesso è efficace riutilizzare l'oggetto `Pipe`.</span><span class="sxs-lookup"><span data-stu-id="04459-186">It's frequently efficient to reuse the `Pipe` object.</span></span> <span data-ttu-id="04459-187">Per reimpostare la pipe, chiamare <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> quando sia il `PipeReader` che il `PipeWriter` sono completati.</span><span class="sxs-lookup"><span data-stu-id="04459-187">To reset the pipe, call <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> when both the `PipeReader` and `PipeWriter` are complete.</span></span>

## <a name="pipereader"></a><span data-ttu-id="04459-188">PipeReader</span><span class="sxs-lookup"><span data-stu-id="04459-188">PipeReader</span></span>

<span data-ttu-id="04459-189"><xref:System.IO.Pipelines.PipeReader> gestisce la memoria per conto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="04459-189"><xref:System.IO.Pipelines.PipeReader> manages memory on the caller's behalf.</span></span> <span data-ttu-id="04459-190">Chiamare **sempre** <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> dopo aver chiamato <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04459-190">**Always** call <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> after calling <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="04459-191">In questo modo, il `PipeReader` sa quando il chiamante viene eseguito con la memoria, in modo che possa essere rilevata.</span><span class="sxs-lookup"><span data-stu-id="04459-191">This lets the `PipeReader` know when the caller is done with the memory so that it can be tracked.</span></span> <span data-ttu-id="04459-192">Il valore di `ReadOnlySequence<byte>` restituito da `PipeReader.ReadAsync` è valido solo fino alla chiamata del `PipeReader.AdvanceTo`.</span><span class="sxs-lookup"><span data-stu-id="04459-192">The `ReadOnlySequence<byte>` returned from `PipeReader.ReadAsync` is only valid until the call the `PipeReader.AdvanceTo`.</span></span> <span data-ttu-id="04459-193">Non è consentito usare `ReadOnlySequence<byte>` dopo aver chiamato `PipeReader.AdvanceTo`.</span><span class="sxs-lookup"><span data-stu-id="04459-193">It's illegal to use `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo`.</span></span>

<span data-ttu-id="04459-194">`PipeReader.AdvanceTo` accetta due argomenti <xref:System.SequencePosition>:</span><span class="sxs-lookup"><span data-stu-id="04459-194">`PipeReader.AdvanceTo` takes two <xref:System.SequencePosition> arguments:</span></span>

* <span data-ttu-id="04459-195">Il primo argomento determina la quantità di memoria utilizzata.</span><span class="sxs-lookup"><span data-stu-id="04459-195">The first argument determines how much memory was consumed.</span></span>
* <span data-ttu-id="04459-196">Il secondo argomento determina la quantità di buffer osservata.</span><span class="sxs-lookup"><span data-stu-id="04459-196">The second argument determines how much of the buffer was observed.</span></span>

<span data-ttu-id="04459-197">Contrassegnare i dati come utilizzati significa che la pipe può restituire la memoria al pool di buffer sottostante.</span><span class="sxs-lookup"><span data-stu-id="04459-197">Marking data as consumed means that the pipe can return the memory to the underlying buffer pool.</span></span> <span data-ttu-id="04459-198">Contrassegnare i dati come osservato controlla la chiamata successiva a `PipeReader.ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="04459-198">Marking data as observed controls what the next call to `PipeReader.ReadAsync` does.</span></span> <span data-ttu-id="04459-199">Contrassegnare tutto come osservato significa che la chiamata successiva a `PipeReader.ReadAsync` non verrà restituita finché non vengono scritti più dati nella pipe.</span><span class="sxs-lookup"><span data-stu-id="04459-199">Marking everything as observed means that the next call to `PipeReader.ReadAsync` won't return until there's more data written to the pipe.</span></span> <span data-ttu-id="04459-200">Qualsiasi altro valore effettuerà la chiamata successiva a `PipeReader.ReadAsync` restituirà immediatamente i dati osservati *e* non osservati, ma i dati che sono già stati utilizzati.</span><span class="sxs-lookup"><span data-stu-id="04459-200">Any other value will make the next call to `PipeReader.ReadAsync` return immediately with the observed *and* unobserved data, but data that has already been consumed.</span></span>

### <a name="read-streaming-data-scenarios"></a><span data-ttu-id="04459-201">Scenari di lettura di flussi di dati</span><span class="sxs-lookup"><span data-stu-id="04459-201">Read streaming data scenarios</span></span>

<span data-ttu-id="04459-202">Quando si tenta di leggere i dati in streaming, è possibile che emergano due modelli tipici:</span><span class="sxs-lookup"><span data-stu-id="04459-202">There are a couple of typical patterns that emerge when trying to read streaming data:</span></span>

* <span data-ttu-id="04459-203">Dato un flusso di dati, analizzare un singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="04459-203">Given a stream of data, parse a single message.</span></span>
* <span data-ttu-id="04459-204">Dato un flusso di dati, analizzare tutti i messaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="04459-204">Given a stream of data, parse all available messages.</span></span>

<span data-ttu-id="04459-205">Negli esempi seguenti viene usato il metodo `TryParseMessage` per l'analisi dei messaggi da un `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="04459-205">The following examples use the `TryParseMessage` method for parsing messages from a `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="04459-206">`TryParseMessage` analizza un singolo messaggio e aggiorna il buffer di input per tagliare il messaggio analizzato dal buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-206">`TryParseMessage` parses a single message and update the input buffer to trim the parsed message from the buffer.</span></span> <span data-ttu-id="04459-207">`TryParseMessage` non fa parte di .NET, si tratta di un metodo scritto dall'utente usato nelle sezioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="04459-207">`TryParseMessage` is not part of .NET, it's a user written method used in the following sections.</span></span>

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a><span data-ttu-id="04459-208">Leggi un singolo messaggio</span><span class="sxs-lookup"><span data-stu-id="04459-208">Read a single message</span></span>

<span data-ttu-id="04459-209">Il codice seguente legge un singolo messaggio da un `PipeReader` e lo restituisce al chiamante.</span><span class="sxs-lookup"><span data-stu-id="04459-209">The following code reads a single message from a `PipeReader` and returns it to the caller.</span></span>

[!code-csharp[ReadSingleMsg](~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs?name=snippet)]

<span data-ttu-id="04459-210">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="04459-210">The preceding code:</span></span>

* <span data-ttu-id="04459-211">Analizza un singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="04459-211">Parses a single message.</span></span>
* <span data-ttu-id="04459-212">Aggiorna le `SequencePosition` utilizzate ed esaminate `SequencePosition` in modo che puntino all'inizio del buffer di input tagliato.</span><span class="sxs-lookup"><span data-stu-id="04459-212">Updates the consumed `SequencePosition` and examined `SequencePosition` to point to the start of the trimmed input buffer.</span></span>

<span data-ttu-id="04459-213">I due argomenti `SequencePosition` vengono aggiornati perché `TryParseMessage` rimuove il messaggio analizzato dal buffer di input.</span><span class="sxs-lookup"><span data-stu-id="04459-213">The two `SequencePosition` arguments are updated because `TryParseMessage` removes the parsed message from the input buffer.</span></span> <span data-ttu-id="04459-214">Generalmente, durante l'analisi di un singolo messaggio dal buffer, la posizione esaminata deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="04459-214">Generally, when parsing a single message from the buffer, the examined position should be one of the following:</span></span>

* <span data-ttu-id="04459-215">Fine del messaggio.</span><span class="sxs-lookup"><span data-stu-id="04459-215">The end of the message.</span></span>
* <span data-ttu-id="04459-216">Fine del buffer ricevuto se non è stato trovato alcun messaggio.</span><span class="sxs-lookup"><span data-stu-id="04459-216">The end of the received buffer if no message was found.</span></span>

<span data-ttu-id="04459-217">Il caso di un singolo messaggio può causare errori.</span><span class="sxs-lookup"><span data-stu-id="04459-217">The single message case has the most potential for errors.</span></span> <span data-ttu-id="04459-218">Il passaggio di valori errati a *esaminato* può causare un'eccezione di memoria insufficiente o un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="04459-218">Passing the wrong values to *examined* can result in an out of memory exception or an infinite loop.</span></span> <span data-ttu-id="04459-219">Per altre informazioni, vedere la sezione [problemi comuni di PipeReader](#gotchas) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="04459-219">For more information, see the [PipeReader common problems](#gotchas) section in this article.</span></span>

### <a name="reading-multiple-messages"></a><span data-ttu-id="04459-220">Lettura di più messaggi</span><span class="sxs-lookup"><span data-stu-id="04459-220">Reading multiple messages</span></span>

<span data-ttu-id="04459-221">Il codice seguente legge tutti i messaggi da un `PipeReader` e chiama `ProcessMessageAsync` in ogni.</span><span class="sxs-lookup"><span data-stu-id="04459-221">The following code reads all messages from a `PipeReader` and calls `ProcessMessageAsync` on each.</span></span>

[!code-csharp[MyConnection1](~/samples/snippets/csharp/pipelines/MyConnection1.cs?name=snippet)]

### <a name="cancellation"></a><span data-ttu-id="04459-222">Annullamento</span><span class="sxs-lookup"><span data-stu-id="04459-222">Cancellation</span></span>

<span data-ttu-id="04459-223">`PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="04459-223">`PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="04459-224">Supporta il passaggio di un <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="04459-224">Supports passing a <xref:System.Threading.CancellationToken>.</span></span>
* <span data-ttu-id="04459-225">Genera un'eccezione <xref:System.OperationCanceledException> se il `CancellationToken` viene annullato mentre è in corso la lettura.</span><span class="sxs-lookup"><span data-stu-id="04459-225">Throws an <xref:System.OperationCanceledException> if the `CancellationToken` is canceled while there's a read pending.</span></span>
* <span data-ttu-id="04459-226">Supporta un modo per annullare l'operazione di lettura corrente tramite <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, che evita la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="04459-226">Supports a way to cancel the current read operation via <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, which avoids raising an exception.</span></span> <span data-ttu-id="04459-227">La chiamata a `PipeReader.CancelPendingRead` determina la chiamata corrente o successiva a `PipeReader.ReadAsync` per restituire un <xref:System.IO.Pipelines.ReadResult> con `IsCanceled` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="04459-227">Calling `PipeReader.CancelPendingRead` causes the current or next call to `PipeReader.ReadAsync` to return a <xref:System.IO.Pipelines.ReadResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="04459-228">Questo può essere utile per arrestare il ciclo di lettura esistente in modo non distruttivo e non eccezionale.</span><span class="sxs-lookup"><span data-stu-id="04459-228">This can be useful for halting the existing read loop in a non-destructive and non-exceptional way.</span></span>

[!code-csharp[MyConnection](~/samples/snippets/csharp/pipelines/MyConnection.cs?name=snippet)]

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a><span data-ttu-id="04459-229">Problemi comuni di PipeReader</span><span class="sxs-lookup"><span data-stu-id="04459-229">PipeReader common problems</span></span>

* <span data-ttu-id="04459-230">Il passaggio di valori errati a `consumed` o `examined` può comportare la lettura dei dati già letti.</span><span class="sxs-lookup"><span data-stu-id="04459-230">Passing the wrong values to `consumed` or `examined` may result in reading already read data.</span></span>
* <span data-ttu-id="04459-231">Il passaggio di `buffer.End` come esaminato può causare:</span><span class="sxs-lookup"><span data-stu-id="04459-231">Passing `buffer.End` as examined may result in:</span></span>

  * <span data-ttu-id="04459-232">Dati bloccati</span><span class="sxs-lookup"><span data-stu-id="04459-232">Stalled data</span></span>
  * <span data-ttu-id="04459-233">È possibile che si verifichi un'eccezione di memoria insufficiente se i dati non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="04459-233">Possibly an eventual Out of Memory (OOM) exception if data isn't consumed.</span></span> <span data-ttu-id="04459-234">Ad esempio, `PipeReader.AdvanceTo(position, buffer.End)` quando si elabora un singolo messaggio alla volta dal buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-234">For example, `PipeReader.AdvanceTo(position, buffer.End)` when processing a single message at a time from the buffer.</span></span>

* <span data-ttu-id="04459-235">Il passaggio di valori errati a `consumed` o `examined` può causare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="04459-235">Passing the wrong values to `consumed` or `examined` may result in an infinite loop.</span></span> <span data-ttu-id="04459-236">Ad esempio, `PipeReader.AdvanceTo(buffer.Start)` se `buffer.Start` non è stato modificato, la chiamata successiva a `PipeReader.ReadAsync` verrà restituita immediatamente prima dell'arrivo di nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="04459-236">For example, `PipeReader.AdvanceTo(buffer.Start)` if `buffer.Start` hasn't changed will cause the next call to `PipeReader.ReadAsync` to return immediately before new data arrives.</span></span>
* <span data-ttu-id="04459-237">Il passaggio di valori errati a `consumed` o `examined` può comportare un buffer infinito (eventuale memoria insufficiente).</span><span class="sxs-lookup"><span data-stu-id="04459-237">Passing the wrong values to `consumed` or `examined` may result in infinite buffering (eventual OOM).</span></span>
* <span data-ttu-id="04459-238">L'uso di `ReadOnlySequence<byte>` dopo la chiamata di `PipeReader.AdvanceTo` può comportare un danneggiamento della memoria (usare after free).</span><span class="sxs-lookup"><span data-stu-id="04459-238">Using the `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo` may result in memory corruption (use after free).</span></span>
* <span data-ttu-id="04459-239">La chiamata a `PipeReader.Complete/CompleteAsync` potrebbe causare una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="04459-239">Failing to call `PipeReader.Complete/CompleteAsync` may result in a memory leak.</span></span>
* <span data-ttu-id="04459-240">Il controllo <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> e l'uscita dalla logica di lettura prima dell'elaborazione del buffer comporta la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="04459-240">Checking <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> and exiting the reading logic before processing the buffer results in data loss.</span></span> <span data-ttu-id="04459-241">La condizione di uscita del ciclo deve essere basata su `ReadResult.Buffer.IsEmpty` e `ReadResult.IsCompleted`.</span><span class="sxs-lookup"><span data-stu-id="04459-241">The loop exit condition should be based on `ReadResult.Buffer.IsEmpty` and `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="04459-242">Questa operazione potrebbe causare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="04459-242">Doing this incorrectly could result in an infinite loop.</span></span>

#### <a name="problematic-code"></a><span data-ttu-id="04459-243">Codice problematico</span><span class="sxs-lookup"><span data-stu-id="04459-243">Problematic code</span></span>

<span data-ttu-id="04459-244">**perdita di dati** ❌</span><span class="sxs-lookup"><span data-stu-id="04459-244">❌ **Data loss**</span></span>

<span data-ttu-id="04459-245">Il `ReadResult` può restituire il segmento finale dei dati quando `IsCompleted` è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="04459-245">The `ReadResult` can return the final segment of data when `IsCompleted` is set to `true`.</span></span> <span data-ttu-id="04459-246">La mancata lettura dei dati prima di uscire dal ciclo di lettura comporterà la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="04459-246">Not reading that data before exiting the read loop will result in data loss.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#1](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="04459-247">**ciclo infinito** ❌</span><span class="sxs-lookup"><span data-stu-id="04459-247">❌ **Infinite loop**</span></span>

<span data-ttu-id="04459-248">La logica seguente può comportare un ciclo infinito se il `Result.IsCompleted` è `true`, ma non esiste mai un messaggio completo nel buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-248">The following logic may result in an infinite loop if the `Result.IsCompleted` is `true` but there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#2](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet2)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="04459-249">Ecco un altro frammento di codice con lo stesso problema.</span><span class="sxs-lookup"><span data-stu-id="04459-249">Here's another piece of code with the same problem.</span></span> <span data-ttu-id="04459-250">Prima di controllare `ReadResult.IsCompleted`, viene verificata la presenza di un buffer non vuoto.</span><span class="sxs-lookup"><span data-stu-id="04459-250">It's checking for a non-empty buffer before checking `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="04459-251">Poiché si trova in un `else if`, il ciclo viene sempre completato se non esiste mai un messaggio completo nel buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-251">Because it's in an `else if`, it will loop forever if there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#3](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet3)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="04459-252">**blocco imprevisto** ❌</span><span class="sxs-lookup"><span data-stu-id="04459-252">❌ **Unexpected Hang**</span></span>

<span data-ttu-id="04459-253">Se si chiama in modo incondizionato `PipeReader.AdvanceTo` con `buffer.End` nella posizione `examined`, è possibile che si verifichino blocchi durante l'analisi di un singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="04459-253">Unconditionally calling `PipeReader.AdvanceTo` with `buffer.End` in the `examined` position may result in hangs when parsing a single message.</span></span> <span data-ttu-id="04459-254">La chiamata successiva a `PipeReader.AdvanceTo` non verrà restituita fino a quando:</span><span class="sxs-lookup"><span data-stu-id="04459-254">The next call to `PipeReader.AdvanceTo` won't return until:</span></span>

* <span data-ttu-id="04459-255">Sono presenti più dati scritti sulla pipe.</span><span class="sxs-lookup"><span data-stu-id="04459-255">There's more data written to the pipe.</span></span>
* <span data-ttu-id="04459-256">E i nuovi dati non sono stati esaminati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="04459-256">And the new data wasn't previously examined.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#4](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet4)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="04459-257">**memoria insufficiente** ❌</span><span class="sxs-lookup"><span data-stu-id="04459-257">❌ **Out of Memory (OOM)**</span></span>

<span data-ttu-id="04459-258">Con le condizioni seguenti, il codice seguente mantiene il buffering fino a quando non si verifica un <xref:System.OutOfMemoryException>:</span><span class="sxs-lookup"><span data-stu-id="04459-258">With the following conditions, the following code keeps buffering until an <xref:System.OutOfMemoryException> occurs:</span></span>

* <span data-ttu-id="04459-259">Nessuna dimensione massima del messaggio.</span><span class="sxs-lookup"><span data-stu-id="04459-259">There's no maximum message size.</span></span>
* <span data-ttu-id="04459-260">I dati restituiti dal `PipeReader` non costituiscono un messaggio completo.</span><span class="sxs-lookup"><span data-stu-id="04459-260">The data returned from the `PipeReader` doesn't make a complete message.</span></span> <span data-ttu-id="04459-261">Ad esempio, non viene creato un messaggio completo perché l'altro sta scrivendo un messaggio di grandi dimensioni, ad esempio un messaggio da 4 GB.</span><span class="sxs-lookup"><span data-stu-id="04459-261">For example, it doesn't make a complete message because the other side is writing a large message (For example, a 4-GB message).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#5](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet5)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="04459-262">**danneggiamento della memoria** ❌</span><span class="sxs-lookup"><span data-stu-id="04459-262">❌ **Memory Corruption**</span></span>

<span data-ttu-id="04459-263">Quando si scrivono gli helper che leggono il buffer, qualsiasi payload restituito deve essere copiato prima di chiamare `Advance`.</span><span class="sxs-lookup"><span data-stu-id="04459-263">When writing helpers that read the buffer, any returned payload should be copied before calling `Advance`.</span></span> <span data-ttu-id="04459-264">Nell'esempio seguente viene restituita una memoria che il `Pipe` ha eliminato e può riutilizzarlo per l'operazione successiva (lettura/scrittura).</span><span class="sxs-lookup"><span data-stu-id="04459-264">The following example will return memory that the `Pipe` has discarded and may reuse it for the next operation (read/write).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#Message](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippetMessage)]

[!code-csharp[DoNotUse#6](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet6)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a><span data-ttu-id="04459-265">PipeWriter</span><span class="sxs-lookup"><span data-stu-id="04459-265">PipeWriter</span></span>

<span data-ttu-id="04459-266">Il <xref:System.IO.Pipelines.PipeWriter> gestisce i buffer per la scrittura per conto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="04459-266">The <xref:System.IO.Pipelines.PipeWriter> manages buffers for writing on the caller's behalf.</span></span> <span data-ttu-id="04459-267">`PipeWriter` implementa [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span><span class="sxs-lookup"><span data-stu-id="04459-267">`PipeWriter` implements [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span></span> <span data-ttu-id="04459-268">`IBufferWriter<byte>` consente di ottenere l'accesso ai buffer per eseguire scritture senza copie del buffer aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="04459-268">`IBufferWriter<byte>` makes it possible to get access to buffers to perform writes without additional buffer copies.</span></span>

[!code-csharp[MyPipeWriter](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet)]

<span data-ttu-id="04459-269">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="04459-269">The previous code:</span></span>

* <span data-ttu-id="04459-270">Richiede un buffer di almeno 5 byte dal `PipeWriter` usando <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span><span class="sxs-lookup"><span data-stu-id="04459-270">Requests a buffer of at least 5 bytes from the `PipeWriter` using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span></span>
* <span data-ttu-id="04459-271">Scrive i byte per la stringa ASCII `"Hello"` al `Memory<byte>`restituito.</span><span class="sxs-lookup"><span data-stu-id="04459-271">Writes bytes for the ASCII string `"Hello"` to the returned `Memory<byte>`.</span></span>
* <span data-ttu-id="04459-272">Chiama <xref:System.IO.Pipelines.PipeWriter.Advance%2A> per indicare il numero di byte scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="04459-272">Calls <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to indicate how many bytes were written to the buffer.</span></span>
* <span data-ttu-id="04459-273">Scarica l'`PipeWriter`, che invia i byte al dispositivo sottostante.</span><span class="sxs-lookup"><span data-stu-id="04459-273">Flushes the `PipeWriter`, which sends the bytes to the underlying device.</span></span>

<span data-ttu-id="04459-274">Il metodo di scrittura precedente usa i buffer forniti dal `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="04459-274">The previous method of writing uses the buffers provided by the `PipeWriter`.</span></span> <span data-ttu-id="04459-275">In alternativa, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="04459-275">Alternatively, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="04459-276">Copia il buffer esistente nel `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="04459-276">Copies the existing buffer to the `PipeWriter`.</span></span>
* <span data-ttu-id="04459-277">Chiama `GetSpan`, `Advance` in base alle esigenze e chiama <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="04459-277">Calls `GetSpan`, `Advance` as appropriate and calls <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span></span>

[!code-csharp[MyPipeWriter#2](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet2)]

### <a name="cancellation"></a><span data-ttu-id="04459-278">Annullamento</span><span class="sxs-lookup"><span data-stu-id="04459-278">Cancellation</span></span>

<span data-ttu-id="04459-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supporta il passaggio di un <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="04459-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supports passing a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="04459-280">Il passaggio di un `CancellationToken` comporta un `OperationCanceledException` se il token viene annullato mentre è in corso lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="04459-280">Passing a `CancellationToken` results in an `OperationCanceledException` if the token is canceled while there's a flush pending.</span></span> <span data-ttu-id="04459-281">`PipeWriter.FlushAsync` supporta un modo per annullare l'operazione di scaricamento corrente tramite <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="04459-281">`PipeWriter.FlushAsync` supports a way to cancel the current flush operation via <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> without raising an exception.</span></span> <span data-ttu-id="04459-282">La chiamata a `PipeWriter.CancelPendingFlush` determina la chiamata corrente o successiva a `PipeWriter.FlushAsync` o `PipeWriter.WriteAsync` per restituire un <xref:System.IO.Pipelines.FlushResult> con `IsCanceled` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="04459-282">Calling `PipeWriter.CancelPendingFlush` causes the current or next call to `PipeWriter.FlushAsync` or `PipeWriter.WriteAsync` to return a <xref:System.IO.Pipelines.FlushResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="04459-283">Questa operazione può essere utile per arrestare lo scaricamento che cede in modo non distruttivo e non eccezionale.</span><span class="sxs-lookup"><span data-stu-id="04459-283">This can be useful for halting the yielding flush in a non-destructive and non-exceptional way.</span></span>

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a><span data-ttu-id="04459-284">Problemi comuni di PipeWriter</span><span class="sxs-lookup"><span data-stu-id="04459-284">PipeWriter common problems</span></span>

* <span data-ttu-id="04459-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> e <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> restituiscono un buffer con almeno la quantità di memoria richiesta.</span><span class="sxs-lookup"><span data-stu-id="04459-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> and <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="04459-286">**Non** presupporre che le dimensioni del buffer siano esatte.</span><span class="sxs-lookup"><span data-stu-id="04459-286">**Don't** assume exact buffer sizes.</span></span>
* <span data-ttu-id="04459-287">Non vi è alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="04459-287">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
* <span data-ttu-id="04459-288">È necessario richiedere un nuovo buffer dopo aver chiamato <xref:System.IO.Pipelines.PipeWriter.Advance%2A> per continuare a scrivere più dati.</span><span class="sxs-lookup"><span data-stu-id="04459-288">A new buffer must be requested after calling <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to continue writing more data.</span></span> <span data-ttu-id="04459-289">Non è possibile scrivere nel buffer acquisito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="04459-289">The previously acquired buffer can't be written to.</span></span>
* <span data-ttu-id="04459-290">Chiamando `GetMemory` o `GetSpan` mentre è presente una chiamata incompleta a `FlushAsync` non è sicura.</span><span class="sxs-lookup"><span data-stu-id="04459-290">Calling `GetMemory` or `GetSpan` while there's an incomplete call to `FlushAsync` isn't safe.</span></span>
* <span data-ttu-id="04459-291">La chiamata di `Complete` o `CompleteAsync` mentre i dati non scaricati possono causare un danneggiamento della memoria.</span><span class="sxs-lookup"><span data-stu-id="04459-291">Calling `Complete` or `CompleteAsync` while there's unflushed data can result in memory corruption.</span></span>

## <a name="iduplexpipe"></a><span data-ttu-id="04459-292">IDuplexPipe</span><span class="sxs-lookup"><span data-stu-id="04459-292">IDuplexPipe</span></span>

<span data-ttu-id="04459-293">Il <xref:System.IO.Pipelines.IDuplexPipe> è un contratto per i tipi che supportano sia la lettura che la scrittura.</span><span class="sxs-lookup"><span data-stu-id="04459-293">The <xref:System.IO.Pipelines.IDuplexPipe> is a contract for types that support both reading and writing.</span></span> <span data-ttu-id="04459-294">Una connessione di rete, ad esempio, viene rappresentata da un `IDuplexPipe`.</span><span class="sxs-lookup"><span data-stu-id="04459-294">For example, a network connection would be represented by an `IDuplexPipe`.</span></span>

 <span data-ttu-id="04459-295">Diversamente da `Pipe` che contiene un `PipeReader` e un `PipeWriter`, `IDuplexPipe` rappresenta un singolo lato di una connessione duplex completa.</span><span class="sxs-lookup"><span data-stu-id="04459-295">Unlike `Pipe` which contains a `PipeReader` and a `PipeWriter`, `IDuplexPipe` represents a single side of a full duplex connection.</span></span> <span data-ttu-id="04459-296">Ciò significa che ciò che viene scritto nel `PipeWriter` non verrà letto da `PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="04459-296">That means what is written to the `PipeWriter` will not be read from the `PipeReader`.</span></span>

## <a name="streams"></a><span data-ttu-id="04459-297">Flussi</span><span class="sxs-lookup"><span data-stu-id="04459-297">Streams</span></span>

<span data-ttu-id="04459-298">Durante la lettura o la scrittura di dati di flusso, in genere si leggono i dati utilizzando un deserializzatore e si scrivono i dati utilizzando un serializzatore.</span><span class="sxs-lookup"><span data-stu-id="04459-298">When reading or writing stream data, you typically read data using a de-serializer and write data using a serializer.</span></span> <span data-ttu-id="04459-299">La maggior parte di queste API del flusso di lettura e scrittura ha un parametro `Stream`.</span><span class="sxs-lookup"><span data-stu-id="04459-299">Most of these read and write stream APIs have a `Stream` parameter.</span></span> <span data-ttu-id="04459-300">Per semplificare l'integrazione con queste API esistenti, `PipeReader` e `PipeWriter` esporre un <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="04459-300">To make it easier to integrate with these existing APIs, `PipeReader` and `PipeWriter` expose an <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.</span></span>  <span data-ttu-id="04459-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> restituisce un'implementazione di `Stream` intorno al `PipeReader` o `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="04459-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> returns a `Stream` implementation around the `PipeReader` or `PipeWriter`.</span></span>
