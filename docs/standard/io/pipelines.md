---
title: Pipeline di I/O - .NET
description: Informazioni su come usare in modo efficiente le pipeline di I/O in .NET ed evitare problemi nel codice.
ms.date: 10/01/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: b18b2bf31787fa58e614cd4f057fba9037fe8ad8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77627552"
---
# <a name="systemiopipelines-in-net"></a><span data-ttu-id="b96f4-103">System.IO.Pipelines in .NET</span><span class="sxs-lookup"><span data-stu-id="b96f4-103">System.IO.Pipelines in .NET</span></span>

<span data-ttu-id="b96f4-104"><xref:System.IO.Pipelines>è una nuova libreria progettata per semplificare l'esecuzione di I/O ad alte prestazioni in .NET.</span><span class="sxs-lookup"><span data-stu-id="b96f4-104"><xref:System.IO.Pipelines> is a new library that is designed to make it easier to do high-performance I/O in .NET.</span></span> <span data-ttu-id="b96f4-105">Si tratta di una libreria destinata a .NET Standard che funziona su tutte le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="b96f4-105">It’s a library targeting .NET Standard that works on all .NET implementations.</span></span>

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a><span data-ttu-id="b96f4-106">Quale problema risolve System.IO.Pipelines</span><span class="sxs-lookup"><span data-stu-id="b96f4-106">What problem does System.IO.Pipelines solve</span></span>

<!-- corner case doesn't MT (machine translate)   -->
<span data-ttu-id="b96f4-107">Le app che analizzano i dati di streaming sono composte da codice boilerplate con molti flussi di codice specializzati e insoliti.</span><span class="sxs-lookup"><span data-stu-id="b96f4-107">Apps that parse streaming data are composed of boilerplate code having many specialized and unusual code flows.</span></span> <span data-ttu-id="b96f4-108">Il boilerplate e il codice speciale del caso sono complessi e difficili da mantenere.</span><span class="sxs-lookup"><span data-stu-id="b96f4-108">The boilerplate and special case code is complex and difficult to maintain.</span></span>

<span data-ttu-id="b96f4-109">`System.IO.Pipelines`è stato progettato per:</span><span class="sxs-lookup"><span data-stu-id="b96f4-109">`System.IO.Pipelines` was architected to:</span></span>

* <span data-ttu-id="b96f4-110">Disporre di dati di streaming di analisi ad alte prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b96f4-110">Have high performance parsing streaming data.</span></span>
* <span data-ttu-id="b96f4-111">Ridurre la complessità del codice.</span><span class="sxs-lookup"><span data-stu-id="b96f4-111">Reduce code complexity.</span></span>

<span data-ttu-id="b96f4-112">Il codice seguente è tipico per un server TCP che riceve `'\n'`messaggi delimitati da riga (delimitati da ) da un client:The following code is typical for a TCP server that receives line-delimited messages (delimited by ) from a client:</span><span class="sxs-lookup"><span data-stu-id="b96f4-112">The following code is typical for a TCP server that receives line-delimited messages (delimited by `'\n'`) from a client:</span></span>

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

<span data-ttu-id="b96f4-113">Il codice precedente presenta diversi problemi:The preceding code has several problems:</span><span class="sxs-lookup"><span data-stu-id="b96f4-113">The preceding code has several problems:</span></span>

* <span data-ttu-id="b96f4-114">L'intero messaggio (fine riga) potrebbe non essere `ReadAsync`ricevuto in una singola chiamata a .</span><span class="sxs-lookup"><span data-stu-id="b96f4-114">The entire message (end of line) might not be received in a single call to `ReadAsync`.</span></span>
* <span data-ttu-id="b96f4-115">Ignora il risultato di `stream.ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="b96f4-115">It's ignoring the result of `stream.ReadAsync`.</span></span> <span data-ttu-id="b96f4-116">`stream.ReadAsync`restituisce la quantità di dati letti.</span><span class="sxs-lookup"><span data-stu-id="b96f4-116">`stream.ReadAsync` returns how much data was read.</span></span>
* <span data-ttu-id="b96f4-117">Non gestisce il caso in cui più `ReadAsync` righe vengono lette in una singola chiamata.</span><span class="sxs-lookup"><span data-stu-id="b96f4-117">It doesn't handle the case where multiple lines are read in a single `ReadAsync` call.</span></span>
* <span data-ttu-id="b96f4-118">Alloca una `byte` matrice con ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="b96f4-118">It allocates a `byte` array with each read.</span></span>

<span data-ttu-id="b96f4-119">Per risolvere i problemi precedenti, sono necessarie le seguenti modifiche:</span><span class="sxs-lookup"><span data-stu-id="b96f4-119">To fix the preceding problems, the following changes are required:</span></span>

* <span data-ttu-id="b96f4-120">Memorizzare i dati in ingresso nel buffer fino a quando non viene trovata una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="b96f4-120">Buffer the incoming data until a new line is found.</span></span>
* <span data-ttu-id="b96f4-121">Analizzare tutte le righe restituite nel buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-121">Parse all the lines returned in the buffer.</span></span>
* <span data-ttu-id="b96f4-122">È possibile che la riga sia maggiore di 1 KB (1024 byte).</span><span class="sxs-lookup"><span data-stu-id="b96f4-122">It's possible that the line is bigger than 1 KB (1024 bytes).</span></span> <span data-ttu-id="b96f4-123">Il codice deve ridimensionare il buffer di input fino a quando non viene trovato il delimitatore per adattarsi alla riga completa all'interno del buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-123">The code needs to resize the input buffer until the delimiter is found in order to fit the complete line inside the buffer.</span></span>

  * <span data-ttu-id="b96f4-124">Se il buffer viene ridimensionato, vengono eseguite più copie del buffer man mano che nell'input vengono visualizzate righe più lunghe.</span><span class="sxs-lookup"><span data-stu-id="b96f4-124">If the buffer is resized, more buffer copies are made as longer lines appear in the input.</span></span>
  * <span data-ttu-id="b96f4-125">Per ridurre lo spazio sprecato, compattare il buffer utilizzato per le righe di lettura.</span><span class="sxs-lookup"><span data-stu-id="b96f4-125">To reduce wasted space, compact the buffer used for reading lines.</span></span>

* <span data-ttu-id="b96f4-126">Prendere in considerazione l'utilizzo del pool di buffer per evitare di allocare ripetutamente memoria.</span><span class="sxs-lookup"><span data-stu-id="b96f4-126">Consider using buffer pooling to avoid allocating memory repeatedly.</span></span>
* <span data-ttu-id="b96f4-127">Il codice seguente risolve alcuni di questi problemi:The following code addresses some of these problems:</span><span class="sxs-lookup"><span data-stu-id="b96f4-127">The following code addresses some of these problems:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs?name=snippet)]

<span data-ttu-id="b96f4-128">Il codice precedente è complesso e non risolve tutti i problemi identificati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-128">The previous code is complex and doesn't address all the problems identified.</span></span> <span data-ttu-id="b96f4-129">La rete ad alte prestazioni di solito significa scrivere codice molto complesso per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b96f4-129">High-performance networking usually means writing very complex code to maximize performance.</span></span> <span data-ttu-id="b96f4-130">`System.IO.Pipelines`è stato progettato per semplificare la scrittura di questo tipo di codice.</span><span class="sxs-lookup"><span data-stu-id="b96f4-130">`System.IO.Pipelines` was designed to make writing this type of code easier.</span></span>

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a><span data-ttu-id="b96f4-131">Pipe</span><span class="sxs-lookup"><span data-stu-id="b96f4-131">Pipe</span></span>

<span data-ttu-id="b96f4-132">La <xref:System.IO.Pipelines.Pipe> classe può essere `PipeWriter/PipeReader` utilizzata per creare una coppia.</span><span class="sxs-lookup"><span data-stu-id="b96f4-132">The <xref:System.IO.Pipelines.Pipe> class can be used to create a `PipeWriter/PipeReader` pair.</span></span> <span data-ttu-id="b96f4-133">Tutti i dati `PipeWriter` scritti nel `PipeReader`è disponibile nel:</span><span class="sxs-lookup"><span data-stu-id="b96f4-133">All data written into the `PipeWriter` is available in the `PipeReader`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet2)]

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a><span data-ttu-id="b96f4-134">Utilizzo di base delle tubazioni</span><span class="sxs-lookup"><span data-stu-id="b96f4-134">Pipe basic usage</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet)]

<span data-ttu-id="b96f4-135">Ci sono due loop:</span><span class="sxs-lookup"><span data-stu-id="b96f4-135">There are two loops:</span></span>

* <span data-ttu-id="b96f4-136">`FillPipeAsync`legge da `Socket` e scrive `PipeWriter`al .</span><span class="sxs-lookup"><span data-stu-id="b96f4-136">`FillPipeAsync` reads from the `Socket` and writes to the `PipeWriter`.</span></span>
* <span data-ttu-id="b96f4-137">`ReadPipeAsync`legge dalle `PipeReader` righe in entrata e analizza.</span><span class="sxs-lookup"><span data-stu-id="b96f4-137">`ReadPipeAsync` reads from the `PipeReader` and parses incoming lines.</span></span>

<span data-ttu-id="b96f4-138">Non sono presenti buffer espliciti allocati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-138">There are no explicit buffers allocated.</span></span> <span data-ttu-id="b96f4-139">Tutta la `PipeReader` gestione del buffer `PipeWriter` è delegata alle implementazioni e .</span><span class="sxs-lookup"><span data-stu-id="b96f4-139">All buffer management is delegated to the `PipeReader` and `PipeWriter` implementations.</span></span> <span data-ttu-id="b96f4-140">La delega della gestione del buffer rende più semplice per l'utilizzo del codice concentrarsi esclusivamente sulla logica di business.</span><span class="sxs-lookup"><span data-stu-id="b96f4-140">Delegating buffer management makes it easier for consuming code to focus solely on the business logic.</span></span>

<span data-ttu-id="b96f4-141">Nel primo ciclo:</span><span class="sxs-lookup"><span data-stu-id="b96f4-141">In the first loop:</span></span>

* <span data-ttu-id="b96f4-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType>viene chiamato per ottenere memoria dal writer sottostante.</span><span class="sxs-lookup"><span data-stu-id="b96f4-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> is called to get memory from the underlying writer.</span></span>
* <span data-ttu-id="b96f4-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType>viene chiamato per `PipeWriter` indicare la quantità di dati scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> is called to tell the `PipeWriter` how much data was written to the buffer.</span></span>
* <span data-ttu-id="b96f4-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>viene chiamato per rendere i `PipeReader`dati disponibili per il file .</span><span class="sxs-lookup"><span data-stu-id="b96f4-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> is called to make the data available to the `PipeReader`.</span></span>

<span data-ttu-id="b96f4-145">Nel secondo ciclo, `PipeReader` l'oggetto consumes `PipeWriter`utilizza i buffer scritti da .</span><span class="sxs-lookup"><span data-stu-id="b96f4-145">In the second loop, the `PipeReader` consumes the buffers written by `PipeWriter`.</span></span> <span data-ttu-id="b96f4-146">I buffer provengono dal socket.</span><span class="sxs-lookup"><span data-stu-id="b96f4-146">The buffers come from the socket.</span></span> <span data-ttu-id="b96f4-147">La chiamata `PipeReader.ReadAsync`a :</span><span class="sxs-lookup"><span data-stu-id="b96f4-147">The call to `PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="b96f4-148">Restituisce <xref:System.IO.Pipelines.ReadResult> un che contiene due informazioni importanti:</span><span class="sxs-lookup"><span data-stu-id="b96f4-148">Returns a <xref:System.IO.Pipelines.ReadResult> that contains two important pieces of information:</span></span>

  * <span data-ttu-id="b96f4-149">I dati che sono stati `ReadOnlySequence<byte>`letti sotto forma di .</span><span class="sxs-lookup"><span data-stu-id="b96f4-149">The data that was read in the form of `ReadOnlySequence<byte>`.</span></span>
  * <span data-ttu-id="b96f4-150">Valore `IsCompleted` booleano che indica se è stata raggiunta la fine dei dati (EOF).</span><span class="sxs-lookup"><span data-stu-id="b96f4-150">A boolean `IsCompleted` that indicates if the end of data (EOF) has been reached.</span></span>

<span data-ttu-id="b96f4-151">Dopo aver individuato il delimitatore di fine riga (EOL) e analizzato la riga:</span><span class="sxs-lookup"><span data-stu-id="b96f4-151">After finding the end of line (EOL) delimiter and parsing the line:</span></span>

* <span data-ttu-id="b96f4-152">La logica elabora il buffer per ignorare ciò che è già stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="b96f4-152">The logic processes the buffer to skip what's already processed.</span></span>
* <span data-ttu-id="b96f4-153">`PipeReader.AdvanceTo`viene chiamato per `PipeReader` indicare la quantità di dati sono stati utilizzati ed esaminati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-153">`PipeReader.AdvanceTo` is called to tell the `PipeReader` how much data has been consumed and examined.</span></span>

<span data-ttu-id="b96f4-154">I cicli reader e writer `Complete`terminano chiamando .</span><span class="sxs-lookup"><span data-stu-id="b96f4-154">The reader and writer loops end by calling `Complete`.</span></span> <span data-ttu-id="b96f4-155">`Complete`consente alla pipe sottostante di rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="b96f4-155">`Complete` lets the underlying Pipe release the memory it allocated.</span></span>

### <a name="backpressure-and-flow-control"></a><span data-ttu-id="b96f4-156">Pressione a ristora e controllo del flusso</span><span class="sxs-lookup"><span data-stu-id="b96f4-156">Backpressure and flow control</span></span>

<span data-ttu-id="b96f4-157">Idealmente, la lettura e l'analisi funzionano insieme:</span><span class="sxs-lookup"><span data-stu-id="b96f4-157">Ideally, reading and parsing work together:</span></span>

* <span data-ttu-id="b96f4-158">Il thread di scrittura utilizza i dati dalla rete e li inserisce nei buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-158">The writing thread consumes data from the network and puts it in buffers.</span></span>
* <span data-ttu-id="b96f4-159">Il thread di analisi è responsabile della costruzione delle strutture di dati appropriate.</span><span class="sxs-lookup"><span data-stu-id="b96f4-159">The parsing thread is responsible for constructing the appropriate data structures.</span></span>

<span data-ttu-id="b96f4-160">In genere, l'analisi richiede più tempo rispetto alla semplice copia di blocchi di dati dalla rete:</span><span class="sxs-lookup"><span data-stu-id="b96f4-160">Typically, parsing takes more time than just copying blocks of data from the network:</span></span>

* <span data-ttu-id="b96f4-161">Il thread di lettura precede il thread di analisi.</span><span class="sxs-lookup"><span data-stu-id="b96f4-161">The reading thread gets ahead of the parsing thread.</span></span>
* <span data-ttu-id="b96f4-162">Il thread di lettura deve rallentare o allocare più memoria per archiviare i dati per il thread di analisi.</span><span class="sxs-lookup"><span data-stu-id="b96f4-162">The reading thread has to either slow down or allocate more memory to store the data for the parsing thread.</span></span>

<span data-ttu-id="b96f4-163">Per prestazioni ottimali, c'è un equilibrio tra pause frequenti e allocazione di più memoria.</span><span class="sxs-lookup"><span data-stu-id="b96f4-163">For optimal performance, there's a balance between frequent pauses and allocating more memory.</span></span>

<span data-ttu-id="b96f4-164">Per risolvere il problema `Pipe` precedente, dispone di due impostazioni per controllare il flusso di dati:</span><span class="sxs-lookup"><span data-stu-id="b96f4-164">To solve the preceding problem, the `Pipe` has two settings to control the flow of data:</span></span>

* <span data-ttu-id="b96f4-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: determina la quantità di dati <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> da memorizzare nel buffer prima che le chiamate vengano sospese.</span><span class="sxs-lookup"><span data-stu-id="b96f4-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determines how much data should be buffered before calls to <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pause.</span></span>
* <span data-ttu-id="b96f4-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: determina la quantità di dati che `PipeWriter.FlushAsync` il lettore deve osservare prima che le chiamate riprendano.</span><span class="sxs-lookup"><span data-stu-id="b96f4-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determines how much data the reader has to observe before calls to `PipeWriter.FlushAsync` resume.</span></span>

![Diagramma con ResumeWriterThreshold e PauseWriterThreshold](./media/pipelines/resume-pause.png)

<span data-ttu-id="b96f4-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b96f4-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="b96f4-169">Restituisce un `ValueTask<FlushResult>` incompleto quando la `Pipe` quantità `PauseWriterThreshold`di dati nelle intercrostati .</span><span class="sxs-lookup"><span data-stu-id="b96f4-169">Returns an incomplete `ValueTask<FlushResult>` when the amount of data in the `Pipe` crosses `PauseWriterThreshold`.</span></span>
* <span data-ttu-id="b96f4-170">Completa `ValueTask<FlushResult>` quando diventa inferiore `ResumeWriterThreshold`a .</span><span class="sxs-lookup"><span data-stu-id="b96f4-170">Completes `ValueTask<FlushResult>` when it becomes lower than `ResumeWriterThreshold`.</span></span>

<span data-ttu-id="b96f4-171">Due valori vengono utilizzati per impedire il ciclo rapido, che può verificarsi se viene utilizzato un valore.</span><span class="sxs-lookup"><span data-stu-id="b96f4-171">Two values are used to prevent rapid cycling, which can occur if one value is used.</span></span>

### <a name="examples"></a><span data-ttu-id="b96f4-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="b96f4-172">Examples</span></span>

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a><span data-ttu-id="b96f4-173">PipeScheduler</span><span class="sxs-lookup"><span data-stu-id="b96f4-173">PipeScheduler</span></span>

<span data-ttu-id="b96f4-174">In `async` genere, quando si utilizza e `await` <xref:System.Threading.Tasks.TaskScheduler> , il <xref:System.Threading.SynchronizationContext>codice asincrono riprende su un o sul file corrente.</span><span class="sxs-lookup"><span data-stu-id="b96f4-174">Typically when using `async` and `await`, asynchronous code resumes on either on a <xref:System.Threading.Tasks.TaskScheduler> or on the current  <xref:System.Threading.SynchronizationContext>.</span></span>

<span data-ttu-id="b96f4-175">Quando si esegue l'I/O, è importante disporre di un controllo granulare sulla posizione in cui viene eseguito l'I/O.</span><span class="sxs-lookup"><span data-stu-id="b96f4-175">When doing I/O, it's important to have fine-grained control over where the I/O is performed.</span></span> <span data-ttu-id="b96f4-176">Questo controllo consente di sfruttare in modo efficace le cache della CPU.</span><span class="sxs-lookup"><span data-stu-id="b96f4-176">This control allows taking advantage of CPU caches effectively.</span></span> <span data-ttu-id="b96f4-177">La memorizzazione efficiente nella cache è fondamentale per le app ad alte prestazioni come i server Web.</span><span class="sxs-lookup"><span data-stu-id="b96f4-177">Efficient caching is critical for high-performance apps like web servers.</span></span> <span data-ttu-id="b96f4-178"><xref:System.IO.Pipelines.PipeScheduler>fornisce il controllo sulla posizione di callback asincroni.</span><span class="sxs-lookup"><span data-stu-id="b96f4-178"><xref:System.IO.Pipelines.PipeScheduler> provides control over where asynchronous callbacks run.</span></span> <span data-ttu-id="b96f4-179">Per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="b96f4-179">By default:</span></span>

* <span data-ttu-id="b96f4-180">Viene <xref:System.Threading.SynchronizationContext> utilizzata la corrente.</span><span class="sxs-lookup"><span data-stu-id="b96f4-180">The current <xref:System.Threading.SynchronizationContext> is used.</span></span>
* <span data-ttu-id="b96f4-181">Se non è `SynchronizationContext`presente alcun , utilizza il pool di thread per eseguire i callback.</span><span class="sxs-lookup"><span data-stu-id="b96f4-181">If there's no `SynchronizationContext`, it uses the thread pool to run callbacks.</span></span>

[!code-csharp[](~/samples/snippets/csharp/pipelines/Program.cs?name=snippet)]

<span data-ttu-id="b96f4-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) è <xref:System.IO.Pipelines.PipeScheduler> l'implementazione che accoda i callback al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="b96f4-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) is the <xref:System.IO.Pipelines.PipeScheduler> implementation that queues callbacks to the thread pool.</span></span> <span data-ttu-id="b96f4-183">`PipeScheduler.ThreadPool`è l'impostazione predefinita e in genere la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="b96f4-183">`PipeScheduler.ThreadPool` is the default and generally the best choice.</span></span> <span data-ttu-id="b96f4-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) può causare conseguenze impreviste, ad esempio deadlock.</span><span class="sxs-lookup"><span data-stu-id="b96f4-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) can cause unintended consequences such as deadlocks.</span></span>

### <a name="pipe-reset"></a><span data-ttu-id="b96f4-185">Reimpostazione tubo</span><span class="sxs-lookup"><span data-stu-id="b96f4-185">Pipe reset</span></span>

<span data-ttu-id="b96f4-186">È spesso efficiente riutilizzare `Pipe` l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b96f4-186">It's frequently efficient to reuse the `Pipe` object.</span></span> <span data-ttu-id="b96f4-187">Per reimpostare la <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> pipe, `PipeReader` `PipeWriter` chiamare al termine di e .</span><span class="sxs-lookup"><span data-stu-id="b96f4-187">To reset the pipe, call <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> when both the `PipeReader` and `PipeWriter` are complete.</span></span>

## <a name="pipereader"></a><span data-ttu-id="b96f4-188">Lettore Pipe</span><span class="sxs-lookup"><span data-stu-id="b96f4-188">PipeReader</span></span>

<span data-ttu-id="b96f4-189"><xref:System.IO.Pipelines.PipeReader>gestisce la memoria per conto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b96f4-189"><xref:System.IO.Pipelines.PipeReader> manages memory on the caller's behalf.</span></span> <span data-ttu-id="b96f4-190">**Chiamare** <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> sempre <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>dopo la chiamata a .</span><span class="sxs-lookup"><span data-stu-id="b96f4-190">**Always** call <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> after calling <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b96f4-191">Ciò `PipeReader` consente di sapere quando il chiamante ha finito con la memoria in modo che possa essere monitorato.</span><span class="sxs-lookup"><span data-stu-id="b96f4-191">This lets the `PipeReader` know when the caller is done with the memory so that it can be tracked.</span></span> <span data-ttu-id="b96f4-192">Il `ReadOnlySequence<byte>` valore `PipeReader.ReadAsync` restituito da è valido `PipeReader.AdvanceTo`solo fino a quando non viene chiamata il file .</span><span class="sxs-lookup"><span data-stu-id="b96f4-192">The `ReadOnlySequence<byte>` returned from `PipeReader.ReadAsync` is only valid until the call the `PipeReader.AdvanceTo`.</span></span> <span data-ttu-id="b96f4-193">È illegale utilizzare `ReadOnlySequence<byte>` dopo `PipeReader.AdvanceTo`aver chiamato .</span><span class="sxs-lookup"><span data-stu-id="b96f4-193">It's illegal to use `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo`.</span></span>

<span data-ttu-id="b96f4-194">`PipeReader.AdvanceTo`accetta <xref:System.SequencePosition> due argomenti:</span><span class="sxs-lookup"><span data-stu-id="b96f4-194">`PipeReader.AdvanceTo` takes two <xref:System.SequencePosition> arguments:</span></span>

* <span data-ttu-id="b96f4-195">Il primo argomento determina la quantità di memoria utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b96f4-195">The first argument determines how much memory was consumed.</span></span>
* <span data-ttu-id="b96f4-196">Il secondo argomento determina la quantità di buffer osservata.</span><span class="sxs-lookup"><span data-stu-id="b96f4-196">The second argument determines how much of the buffer was observed.</span></span>

<span data-ttu-id="b96f4-197">Contrassegnare i dati come utilizzati significa che la pipe può restituire la memoria al pool di buffer sottostante.</span><span class="sxs-lookup"><span data-stu-id="b96f4-197">Marking data as consumed means that the pipe can return the memory to the underlying buffer pool.</span></span> <span data-ttu-id="b96f4-198">Il contrassegno dei dati come `PipeReader.ReadAsync` osservati controlla l'azione della chiamata successiva.</span><span class="sxs-lookup"><span data-stu-id="b96f4-198">Marking data as observed controls what the next call to `PipeReader.ReadAsync` does.</span></span> <span data-ttu-id="b96f4-199">Contrassegnare tutto come osservato significa `PipeReader.ReadAsync` che la chiamata successiva a non verrà restituita fino a quando non sono presenti più dati scritti nella pipe.</span><span class="sxs-lookup"><span data-stu-id="b96f4-199">Marking everything as observed means that the next call to `PipeReader.ReadAsync` won't return until there's more data written to the pipe.</span></span> <span data-ttu-id="b96f4-200">Qualsiasi altro valore effettuerà `PipeReader.ReadAsync` la chiamata successiva per restituire immediatamente i dati osservati *e* non osservati, ma i dati che sono già stati utilizzati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-200">Any other value will make the next call to `PipeReader.ReadAsync` return immediately with the observed *and* unobserved data, but data that has already been consumed.</span></span>

### <a name="read-streaming-data-scenarios"></a><span data-ttu-id="b96f4-201">Leggere gli scenari di streaming dei datiRead streaming data scenarios</span><span class="sxs-lookup"><span data-stu-id="b96f4-201">Read streaming data scenarios</span></span>

<span data-ttu-id="b96f4-202">Esistono un paio di modelli tipici che emergono quando si tenta di leggere i dati in streaming:There are a couple of typical patterns that emerge when trying to read streaming data:</span><span class="sxs-lookup"><span data-stu-id="b96f4-202">There are a couple of typical patterns that emerge when trying to read streaming data:</span></span>

* <span data-ttu-id="b96f4-203">Dato un flusso di dati, analizzare un singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="b96f4-203">Given a stream of data, parse a single message.</span></span>
* <span data-ttu-id="b96f4-204">Dato un flusso di dati, analizzare tutti i messaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="b96f4-204">Given a stream of data, parse all available messages.</span></span>

<span data-ttu-id="b96f4-205">Negli esempi seguenti `TryParseMessage` viene utilizzato il metodo `ReadOnlySequence<byte>`per l'analisi dei messaggi da un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b96f4-205">The following examples use the `TryParseMessage` method for parsing messages from a `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="b96f4-206">`TryParseMessage`analizza un singolo messaggio e aggiorna il buffer di input per tagliare il messaggio analizzato dal buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-206">`TryParseMessage` parses a single message and update the input buffer to trim the parsed message from the buffer.</span></span> <span data-ttu-id="b96f4-207">`TryParseMessage`non fa parte di .NET, è un metodo scritto dall'utente utilizzato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b96f4-207">`TryParseMessage` is not part of .NET, it's a user written method used in the following sections.</span></span>

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a><span data-ttu-id="b96f4-208">Leggere un singolo messaggio</span><span class="sxs-lookup"><span data-stu-id="b96f4-208">Read a single message</span></span>

<span data-ttu-id="b96f4-209">Il codice seguente legge un `PipeReader` singolo messaggio da a e lo restituisce al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b96f4-209">The following code reads a single message from a `PipeReader` and returns it to the caller.</span></span>

[!code-csharp[ReadSingleMsg](~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs?name=snippet)]

<span data-ttu-id="b96f4-210">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="b96f4-210">The preceding code:</span></span>

* <span data-ttu-id="b96f4-211">Analizza un singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="b96f4-211">Parses a single message.</span></span>
* <span data-ttu-id="b96f4-212">Aggiorna l'oggetto consumato `SequencePosition` ed esaminato `SequencePosition` in modo che punti all'inizio del buffer di input tagliato.</span><span class="sxs-lookup"><span data-stu-id="b96f4-212">Updates the consumed `SequencePosition` and examined `SequencePosition` to point to the start of the trimmed input buffer.</span></span>

<span data-ttu-id="b96f4-213">I `SequencePosition` due argomenti `TryParseMessage` vengono aggiornati perché rimuove il messaggio analizzato dal buffer di input.</span><span class="sxs-lookup"><span data-stu-id="b96f4-213">The two `SequencePosition` arguments are updated because `TryParseMessage` removes the parsed message from the input buffer.</span></span> <span data-ttu-id="b96f4-214">In genere, durante l'analisi di un singolo messaggio dal buffer, la posizione esaminata deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="b96f4-214">Generally, when parsing a single message from the buffer, the examined position should be one of the following:</span></span>

* <span data-ttu-id="b96f4-215">Fine del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b96f4-215">The end of the message.</span></span>
* <span data-ttu-id="b96f4-216">Fine del buffer ricevuto se non è stato trovato alcun messaggio.</span><span class="sxs-lookup"><span data-stu-id="b96f4-216">The end of the received buffer if no message was found.</span></span>

<span data-ttu-id="b96f4-217">Il singolo caso di messaggio ha il maggior potenziale di errori.</span><span class="sxs-lookup"><span data-stu-id="b96f4-217">The single message case has the most potential for errors.</span></span> <span data-ttu-id="b96f4-218">Il passaggio dei valori errati da *esaminare* può causare un'eccezione di memoria insufficiente o un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="b96f4-218">Passing the wrong values to *examined* can result in an out of memory exception or an infinite loop.</span></span> <span data-ttu-id="b96f4-219">Per altre informazioni, vedere la sezione [Problemi comuni di PipeReader](#gotchas) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b96f4-219">For more information, see the [PipeReader common problems](#gotchas) section in this article.</span></span>

### <a name="reading-multiple-messages"></a><span data-ttu-id="b96f4-220">Lettura di più messaggi</span><span class="sxs-lookup"><span data-stu-id="b96f4-220">Reading multiple messages</span></span>

<span data-ttu-id="b96f4-221">Il codice seguente legge tutti `PipeReader` i `ProcessMessageAsync` messaggi da a e chiama su ciascuno.</span><span class="sxs-lookup"><span data-stu-id="b96f4-221">The following code reads all messages from a `PipeReader` and calls `ProcessMessageAsync` on each.</span></span>

[!code-csharp[MyConnection1](~/samples/snippets/csharp/pipelines/MyConnection1.cs?name=snippet)]

### <a name="cancellation"></a><span data-ttu-id="b96f4-222">Annullamento</span><span class="sxs-lookup"><span data-stu-id="b96f4-222">Cancellation</span></span>

<span data-ttu-id="b96f4-223">`PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="b96f4-223">`PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="b96f4-224">Supporta il <xref:System.Threading.CancellationToken>passaggio di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b96f4-224">Supports passing a <xref:System.Threading.CancellationToken>.</span></span>
* <span data-ttu-id="b96f4-225">Genera un <xref:System.OperationCanceledException> se `CancellationToken` l'oggetto viene annullato mentre è presente una lettura in sospeso.</span><span class="sxs-lookup"><span data-stu-id="b96f4-225">Throws an <xref:System.OperationCanceledException> if the `CancellationToken` is canceled while there's a read pending.</span></span>
* <span data-ttu-id="b96f4-226">Supporta un modo per annullare <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>l'operazione di lettura corrente tramite , che evita la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b96f4-226">Supports a way to cancel the current read operation via <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, which avoids raising an exception.</span></span> <span data-ttu-id="b96f4-227">La `PipeReader.CancelPendingRead` chiamata fa sì `PipeReader.ReadAsync` che la <xref:System.IO.Pipelines.ReadResult> `IsCanceled` chiamata `true`corrente o successiva a restituisca un oggetto con impostato su .</span><span class="sxs-lookup"><span data-stu-id="b96f4-227">Calling `PipeReader.CancelPendingRead` causes the current or next call to `PipeReader.ReadAsync` to return a <xref:System.IO.Pipelines.ReadResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="b96f4-228">Ciò può essere utile per arrestare il ciclo di lettura esistente in modo non distruttivo e non eccezionale.</span><span class="sxs-lookup"><span data-stu-id="b96f4-228">This can be useful for halting the existing read loop in a non-destructive and non-exceptional way.</span></span>

[!code-csharp[MyConnection](~/samples/snippets/csharp/pipelines/MyConnection.cs?name=snippet)]

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a><span data-ttu-id="b96f4-229">Problemi comuni di PipeReader</span><span class="sxs-lookup"><span data-stu-id="b96f4-229">PipeReader common problems</span></span>

* <span data-ttu-id="b96f4-230">Il passaggio `consumed` di `examined` valori errati a o può comportare la lettura dei dati già letti.</span><span class="sxs-lookup"><span data-stu-id="b96f4-230">Passing the wrong values to `consumed` or `examined` may result in reading already read data.</span></span>
* <span data-ttu-id="b96f4-231">Il `buffer.End` passaggio come esaminato può comportare:</span><span class="sxs-lookup"><span data-stu-id="b96f4-231">Passing `buffer.End` as examined may result in:</span></span>

  * <span data-ttu-id="b96f4-232">Dati in stallo</span><span class="sxs-lookup"><span data-stu-id="b96f4-232">Stalled data</span></span>
  * <span data-ttu-id="b96f4-233">Forse un'eventuale eccezione di memoria insufficiente (OOM) se i dati non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-233">Possibly an eventual Out of Memory (OOM) exception if data isn't consumed.</span></span> <span data-ttu-id="b96f4-234">Ad esempio, `PipeReader.AdvanceTo(position, buffer.End)` durante l'elaborazione di un singolo messaggio alla volta dal buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-234">For example, `PipeReader.AdvanceTo(position, buffer.End)` when processing a single message at a time from the buffer.</span></span>

* <span data-ttu-id="b96f4-235">Il passaggio `consumed` dei `examined` valori errati a o può comportare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="b96f4-235">Passing the wrong values to `consumed` or `examined` may result in an infinite loop.</span></span> <span data-ttu-id="b96f4-236">Ad `PipeReader.AdvanceTo(buffer.Start)` esempio, `buffer.Start` se non è stato modificato, la chiamata successiva a `PipeReader.ReadAsync` restituire immediatamente prima dell'arrivo di nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-236">For example, `PipeReader.AdvanceTo(buffer.Start)` if `buffer.Start` hasn't changed will cause the next call to `PipeReader.ReadAsync` to return immediately before new data arrives.</span></span>
* <span data-ttu-id="b96f4-237">Il passaggio `consumed` dei `examined` valori errati a o può causare un buffering infinito (eventuale OOM).</span><span class="sxs-lookup"><span data-stu-id="b96f4-237">Passing the wrong values to `consumed` or `examined` may result in infinite buffering (eventual OOM).</span></span>
* <span data-ttu-id="b96f4-238">L'utilizzo `ReadOnlySequence<byte>` `PipeReader.AdvanceTo` della chiamata dopo può causare il danneggiamento della memoria (utilizzare dopo libero).</span><span class="sxs-lookup"><span data-stu-id="b96f4-238">Using the `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo` may result in memory corruption (use after free).</span></span>
* <span data-ttu-id="b96f4-239">La mancata chiamata `PipeReader.Complete/CompleteAsync` può causare una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="b96f4-239">Failing to call `PipeReader.Complete/CompleteAsync` may result in a memory leak.</span></span>
* <span data-ttu-id="b96f4-240">Il <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> controllo e l'uscita dalla logica di lettura prima dell'elaborazione del buffer comportano la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-240">Checking <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> and exiting the reading logic before processing the buffer results in data loss.</span></span> <span data-ttu-id="b96f4-241">La condizione di uscita `ReadResult.Buffer.IsEmpty` del `ReadResult.IsCompleted`ciclo deve essere basata su e .</span><span class="sxs-lookup"><span data-stu-id="b96f4-241">The loop exit condition should be based on `ReadResult.Buffer.IsEmpty` and `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="b96f4-242">Questa operazione in modo non corretto potrebbe causare un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="b96f4-242">Doing this incorrectly could result in an infinite loop.</span></span>

#### <a name="problematic-code"></a><span data-ttu-id="b96f4-243">Codice problematico</span><span class="sxs-lookup"><span data-stu-id="b96f4-243">Problematic code</span></span>

<span data-ttu-id="b96f4-244">❌**Perdita di dati**</span><span class="sxs-lookup"><span data-stu-id="b96f4-244">❌ **Data loss**</span></span>

<span data-ttu-id="b96f4-245">L'oggetto `ReadResult` può restituire il `IsCompleted` segmento `true`finale di dati quando è impostato su .</span><span class="sxs-lookup"><span data-stu-id="b96f4-245">The `ReadResult` can return the final segment of data when `IsCompleted` is set to `true`.</span></span> <span data-ttu-id="b96f4-246">La non lettura dei dati prima di uscire dal ciclo di lettura comporterà la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-246">Not reading that data before exiting the read loop will result in data loss.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#1](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="b96f4-247">❌**Ciclo infinito**</span><span class="sxs-lookup"><span data-stu-id="b96f4-247">❌ **Infinite loop**</span></span>

<span data-ttu-id="b96f4-248">La logica seguente può comportare `Result.IsCompleted` un `true` ciclo infinito se l'oggetto è ma non è mai presente un messaggio completo nel buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-248">The following logic may result in an infinite loop if the `Result.IsCompleted` is `true` but there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#2](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet2)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="b96f4-249">Ecco un altro pezzo di codice con lo stesso problema.</span><span class="sxs-lookup"><span data-stu-id="b96f4-249">Here's another piece of code with the same problem.</span></span> <span data-ttu-id="b96f4-250">Sta verificando la presenza di un `ReadResult.IsCompleted`buffer non vuoto prima di controllare .</span><span class="sxs-lookup"><span data-stu-id="b96f4-250">It's checking for a non-empty buffer before checking `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="b96f4-251">Perché è in `else if`un , verrà eseguito un ciclo per sempre se non c'è mai un messaggio completo nel buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-251">Because it's in an `else if`, it will loop forever if there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#3](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet3)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="b96f4-252">❌**Inaspettato Hang**</span><span class="sxs-lookup"><span data-stu-id="b96f4-252">❌ **Unexpected Hang**</span></span>

<span data-ttu-id="b96f4-253">La chiamata `PipeReader.AdvanceTo` incondizionata con `buffer.End` nella `examined` posizione può causare blocchi durante l'analisi di un singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="b96f4-253">Unconditionally calling `PipeReader.AdvanceTo` with `buffer.End` in the `examined` position may result in hangs when parsing a single message.</span></span> <span data-ttu-id="b96f4-254">La prossima `PipeReader.AdvanceTo` chiamata a non tornerà fino a:</span><span class="sxs-lookup"><span data-stu-id="b96f4-254">The next call to `PipeReader.AdvanceTo` won't return until:</span></span>

* <span data-ttu-id="b96f4-255">Ci sono più dati scritti nella pipe.</span><span class="sxs-lookup"><span data-stu-id="b96f4-255">There's more data written to the pipe.</span></span>
* <span data-ttu-id="b96f4-256">E i nuovi dati non sono stati esaminati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b96f4-256">And the new data wasn't previously examined.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#4](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet4)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="b96f4-257">❌**Memoria insufficiente (OOM)**</span><span class="sxs-lookup"><span data-stu-id="b96f4-257">❌ **Out of Memory (OOM)**</span></span>

<span data-ttu-id="b96f4-258">Con le seguenti condizioni, il codice <xref:System.OutOfMemoryException> seguente mantiene il buffering fino a quando non si verifica un si verifica:With the following conditions, the following code keeps buffering until an occurs:</span><span class="sxs-lookup"><span data-stu-id="b96f4-258">With the following conditions, the following code keeps buffering until an <xref:System.OutOfMemoryException> occurs:</span></span>

* <span data-ttu-id="b96f4-259">Non esiste una dimensione massima dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b96f4-259">There's no maximum message size.</span></span>
* <span data-ttu-id="b96f4-260">I dati restituiti `PipeReader` da non costituiscono un messaggio completo.</span><span class="sxs-lookup"><span data-stu-id="b96f4-260">The data returned from the `PipeReader` doesn't make a complete message.</span></span> <span data-ttu-id="b96f4-261">Ad esempio, non crea un messaggio completo perché l'altro lato sta scrivendo un messaggio di grandi dimensioni (ad esempio, un messaggio da 4 GB).</span><span class="sxs-lookup"><span data-stu-id="b96f4-261">For example, it doesn't make a complete message because the other side is writing a large message (For example, a 4-GB message).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#5](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet5)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="b96f4-262">❌**Danneggiamento della memoria**</span><span class="sxs-lookup"><span data-stu-id="b96f4-262">❌ **Memory Corruption**</span></span>

<span data-ttu-id="b96f4-263">Quando si scrivono helper che leggono il buffer, qualsiasi payload restituito deve essere copiato prima di chiamare `Advance`.</span><span class="sxs-lookup"><span data-stu-id="b96f4-263">When writing helpers that read the buffer, any returned payload should be copied before calling `Advance`.</span></span> <span data-ttu-id="b96f4-264">L'esempio seguente restituirà `Pipe` memoria che l'oggetto ha eliminato e potrebbe riutilizzarla per l'operazione successiva (lettura/scrittura).</span><span class="sxs-lookup"><span data-stu-id="b96f4-264">The following example will return memory that the `Pipe` has discarded and may reuse it for the next operation (read/write).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#Message](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippetMessage)]

[!code-csharp[DoNotUse#6](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet6)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a><span data-ttu-id="b96f4-265">PipeWriter</span><span class="sxs-lookup"><span data-stu-id="b96f4-265">PipeWriter</span></span>

<span data-ttu-id="b96f4-266">Il <xref:System.IO.Pipelines.PipeWriter> gestisce i buffer per la scrittura per conto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="b96f4-266">The <xref:System.IO.Pipelines.PipeWriter> manages buffers for writing on the caller's behalf.</span></span> <span data-ttu-id="b96f4-267">`PipeWriter`implementa [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span><span class="sxs-lookup"><span data-stu-id="b96f4-267">`PipeWriter` implements [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span></span> <span data-ttu-id="b96f4-268">`IBufferWriter<byte>`consente di ottenere l'accesso ai buffer per eseguire scritture senza copie aggiuntive del buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-268">`IBufferWriter<byte>` makes it possible to get access to buffers to perform writes without additional buffer copies.</span></span>

[!code-csharp[MyPipeWriter](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet)]

<span data-ttu-id="b96f4-269">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="b96f4-269">The previous code:</span></span>

* <span data-ttu-id="b96f4-270">Richiede un buffer di almeno `PipeWriter` 5 <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>byte dall'oggetto using .</span><span class="sxs-lookup"><span data-stu-id="b96f4-270">Requests a buffer of at least 5 bytes from the `PipeWriter` using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span></span>
* <span data-ttu-id="b96f4-271">Scrive i byte `"Hello"` per la `Memory<byte>`stringa ASCII nell'oggetto restituito.</span><span class="sxs-lookup"><span data-stu-id="b96f4-271">Writes bytes for the ASCII string `"Hello"` to the returned `Memory<byte>`.</span></span>
* <span data-ttu-id="b96f4-272">Chiamate <xref:System.IO.Pipelines.PipeWriter.Advance%2A> per indicare quanti byte sono stati scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-272">Calls <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to indicate how many bytes were written to the buffer.</span></span>
* <span data-ttu-id="b96f4-273">Scarica l'oggetto `PipeWriter`, che invia i byte al dispositivo sottostante.</span><span class="sxs-lookup"><span data-stu-id="b96f4-273">Flushes the `PipeWriter`, which sends the bytes to the underlying device.</span></span>

<span data-ttu-id="b96f4-274">Il metodo di scrittura precedente utilizza `PipeWriter`i buffer forniti dall'oggetto .</span><span class="sxs-lookup"><span data-stu-id="b96f4-274">The previous method of writing uses the buffers provided by the `PipeWriter`.</span></span> <span data-ttu-id="b96f4-275">In alternativa, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b96f4-275">Alternatively, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="b96f4-276">Copia il buffer esistente `PipeWriter`nell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="b96f4-276">Copies the existing buffer to the `PipeWriter`.</span></span>
* <span data-ttu-id="b96f4-277">Chiamate `GetSpan` `Advance` , a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>seconda dei casi e chiamate .</span><span class="sxs-lookup"><span data-stu-id="b96f4-277">Calls `GetSpan`, `Advance` as appropriate and calls <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span></span>

[!code-csharp[MyPipeWriter#2](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet2)]

### <a name="cancellation"></a><span data-ttu-id="b96f4-278">Annullamento</span><span class="sxs-lookup"><span data-stu-id="b96f4-278">Cancellation</span></span>

<span data-ttu-id="b96f4-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>supporta il <xref:System.Threading.CancellationToken>passaggio di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b96f4-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supports passing a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="b96f4-280">Il `CancellationToken` passaggio `OperationCanceledException` di un risultato genera un se il token viene annullato mentre è presente un colore in sospeso.</span><span class="sxs-lookup"><span data-stu-id="b96f4-280">Passing a `CancellationToken` results in an `OperationCanceledException` if the token is canceled while there's a flush pending.</span></span> <span data-ttu-id="b96f4-281">`PipeWriter.FlushAsync`supporta un modo per annullare <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> l'operazione di svuotamento corrente tramite senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b96f4-281">`PipeWriter.FlushAsync` supports a way to cancel the current flush operation via <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> without raising an exception.</span></span> <span data-ttu-id="b96f4-282">La `PipeWriter.CancelPendingFlush` chiamata fa sì `PipeWriter.FlushAsync` che `PipeWriter.WriteAsync` la <xref:System.IO.Pipelines.FlushResult> chiamata `IsCanceled` corrente `true`o successiva a o restituisca un oggetto con impostato su .</span><span class="sxs-lookup"><span data-stu-id="b96f4-282">Calling `PipeWriter.CancelPendingFlush` causes the current or next call to `PipeWriter.FlushAsync` or `PipeWriter.WriteAsync` to return a <xref:System.IO.Pipelines.FlushResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="b96f4-283">Questo può essere utile per arrestare il colore cedevole in modo non distruttivo e non eccezionale.</span><span class="sxs-lookup"><span data-stu-id="b96f4-283">This can be useful for halting the yielding flush in a non-destructive and non-exceptional way.</span></span>

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a><span data-ttu-id="b96f4-284">Problemi comuni di PipeWriter</span><span class="sxs-lookup"><span data-stu-id="b96f4-284">PipeWriter common problems</span></span>

* <span data-ttu-id="b96f4-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A>e <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> restituire un buffer con almeno la quantità di memoria richiesta.</span><span class="sxs-lookup"><span data-stu-id="b96f4-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> and <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="b96f4-286">**Non** presupporre che le dimensioni esatte del buffer.</span><span class="sxs-lookup"><span data-stu-id="b96f4-286">**Don't** assume exact buffer sizes.</span></span>
* <span data-ttu-id="b96f4-287">Non esiste alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer delle stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b96f4-287">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
* <span data-ttu-id="b96f4-288">È necessario richiedere un <xref:System.IO.Pipelines.PipeWriter.Advance%2A> nuovo buffer dopo la chiamata per continuare a scrivere altri dati.</span><span class="sxs-lookup"><span data-stu-id="b96f4-288">A new buffer must be requested after calling <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to continue writing more data.</span></span> <span data-ttu-id="b96f4-289">Impossibile scrivere nel buffer acquisito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b96f4-289">The previously acquired buffer can't be written to.</span></span>
* <span data-ttu-id="b96f4-290">Chiamare `GetMemory` `GetSpan` o mentre c'è una `FlushAsync` chiamata incompleta a non è sicuro.</span><span class="sxs-lookup"><span data-stu-id="b96f4-290">Calling `GetMemory` or `GetSpan` while there's an incomplete call to `FlushAsync` isn't safe.</span></span>
* <span data-ttu-id="b96f4-291">La `Complete` `CompleteAsync` chiamata o mentre sono presenti dati non scaricati può causare il danneggiamento della memoria.</span><span class="sxs-lookup"><span data-stu-id="b96f4-291">Calling `Complete` or `CompleteAsync` while there's unflushed data can result in memory corruption.</span></span>

## <a name="iduplexpipe"></a><span data-ttu-id="b96f4-292">IDuplexPipe</span><span class="sxs-lookup"><span data-stu-id="b96f4-292">IDuplexPipe</span></span>

<span data-ttu-id="b96f4-293">Il <xref:System.IO.Pipelines.IDuplexPipe> è un contratto per i tipi che supportano sia la lettura che la scrittura.</span><span class="sxs-lookup"><span data-stu-id="b96f4-293">The <xref:System.IO.Pipelines.IDuplexPipe> is a contract for types that support both reading and writing.</span></span> <span data-ttu-id="b96f4-294">Ad esempio, una connessione di `IDuplexPipe`rete sarebbe rappresentata da un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b96f4-294">For example, a network connection would be represented by an `IDuplexPipe`.</span></span>

 <span data-ttu-id="b96f4-295">A `Pipe` differenza `PipeReader` di `PipeWriter`che `IDuplexPipe` contiene a e un , rappresenta un singolo lato di una connessione duplex completa.</span><span class="sxs-lookup"><span data-stu-id="b96f4-295">Unlike `Pipe` which contains a `PipeReader` and a `PipeWriter`, `IDuplexPipe` represents a single side of a full duplex connection.</span></span> <span data-ttu-id="b96f4-296">Ciò significa che `PipeWriter` ciò che è `PipeReader`scritto per il non sarà letto dal .</span><span class="sxs-lookup"><span data-stu-id="b96f4-296">That means what is written to the `PipeWriter` will not be read from the `PipeReader`.</span></span>

## <a name="streams"></a><span data-ttu-id="b96f4-297">Flussi</span><span class="sxs-lookup"><span data-stu-id="b96f4-297">Streams</span></span>

<span data-ttu-id="b96f4-298">Quando si leggono o si scrivono dati di flusso, in genere si leggono i dati utilizzando un deserializzatore e si scrivono dati utilizzando un serializzatore.</span><span class="sxs-lookup"><span data-stu-id="b96f4-298">When reading or writing stream data, you typically read data using a de-serializer and write data using a serializer.</span></span> <span data-ttu-id="b96f4-299">La maggior parte di queste API `Stream` di flusso di lettura e scrittura hanno un parametro.</span><span class="sxs-lookup"><span data-stu-id="b96f4-299">Most of these read and write stream APIs have a `Stream` parameter.</span></span> <span data-ttu-id="b96f4-300">Per semplificare l'integrazione con queste `PipeReader` `PipeWriter` API <xref:System.IO.Pipelines.PipeReader.AsStream%2A>esistenti ed esporre un file .</span><span class="sxs-lookup"><span data-stu-id="b96f4-300">To make it easier to integrate with these existing APIs, `PipeReader` and `PipeWriter` expose an <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.</span></span>  <span data-ttu-id="b96f4-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A>restituisce `Stream` un'implementazione intorno a `PipeReader` o `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="b96f4-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> returns a `Stream` implementation around the `PipeReader` or `PipeWriter`.</span></span>
