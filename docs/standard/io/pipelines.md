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
ms.openlocfilehash: 9e26fb36b77e38c81273ccda370a203dd3388e5c
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291739"
---
# <a name="systemiopipelines-in-net"></a>System. IO. Pipelines in .NET

<xref:System.IO.Pipelines> è una nuova libreria progettata per semplificare l'esecuzione di operazioni di I/O a prestazioni elevate in .NET. Si tratta di una libreria destinata a .NET Standard che funziona in tutte le implementazioni di .NET.

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a>Quale problema risolve System. IO. Pipelines
<!-- corner case doesn't MT (machine translate)   -->
Le app che analizzano i dati di streaming sono costituite da codice standard con molti flussi di codice specializzati e insoliti. Il codice standard e del case speciale è complesso e difficile da gestire.

`System.IO.Pipelines` è stato progettato per:

* Analisi delle prestazioni elevate dei dati di streaming.
* Ridurre la complessità del codice.

Il codice seguente è tipico per un server TCP che riceve messaggi delimitati da righe (delimitati da `'\n'`) da un client:

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);
    
    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

Il codice precedente presenta diversi problemi:

* L'intero messaggio (fine riga) potrebbe non essere ricevuto in una singola chiamata a `ReadAsync`.
* Viene ignorato il risultato di `stream.ReadAsync`. `stream.ReadAsync` restituisce la quantità di dati letti.
* Non gestisce il caso in cui vengono lette più righe in una singola chiamata `ReadAsync`.
* Alloca una matrice `byte` a ogni lettura.

Per risolvere i problemi precedenti, sono necessarie le modifiche seguenti:

* Memorizza nel buffer i dati in arrivo fino a quando non viene trovata una nuova riga.
* Analizza tutte le righe restituite nel buffer.
* È possibile che la riga sia maggiore di 1 KB (1024 byte). Il codice deve ridimensionare il buffer di input. viene trovata una riga completa.

  * Se il buffer viene ridimensionato, vengono apportate più copie del buffer mentre le righe più lunghe vengono visualizzate nell'input.
  * Per ridurre lo spazio sprecato, compattare il buffer utilizzato per la lettura delle righe.

* Prendere in considerazione l'uso del pool di buffer per evitare di allocare ripetutamente memoria.
* Il codice seguente risolve alcuni di questi problemi:

[!code-csharp[](~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs?name=snippet)]

Il codice precedente è complesso e non risolve tutti i problemi identificati. Una rete ad alte prestazioni in genere significa scrivere codice molto complesso per ottimizzare le prestazioni. `System.IO.Pipelines` è stato progettato per semplificare la scrittura di questo tipo di codice.

## <a name="pipe"></a>Pipe

La classe <xref:System.IO.Pipelines.Pipe> può essere usata per creare una coppia `PipeWriter/PipeReader`. Tutti i dati scritti in `PipeWriter` sono disponibili nell'`PipeReader`:

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet2)]

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a>Utilizzo di base pipe

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet)]

Sono disponibili due cicli:

* `FillPipeAsync` legge dal `Socket` e scrive nel `PipeWriter`.
* `ReadPipeAsync` legge dal `PipeReader` e analizza le righe in ingresso.

Nessun buffer esplicito allocato. La gestione del buffer viene delegata alle implementazioni `PipeReader` e `PipeWriter`. La delega della gestione del buffer rende più semplice l'utilizzo del codice per concentrarsi esclusivamente sulla logica di business.

Nel primo ciclo:

* <xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> viene chiamato per ottenere la memoria dal writer sottostante.
* <xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> viene chiamato per indicare al `PipeWriter` la quantità di dati scritti nel buffer.
* viene chiamato <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> per rendere i dati disponibili per il `PipeReader`.

Nel secondo ciclo, il `PipeReader` utilizza i buffer scritti da `PipeWriter`. I buffer provengono dal socket. La chiamata a `PipeReader.ReadAsync`:

* Restituisce un <xref:System.IO.Pipelines.ReadResult> che contiene due informazioni importanti:

  * Dati letti nel formato `ReadOnlySequence<byte>`.
  * Valore booleano `IsCompleted` che indica se è stata raggiunta la fine dei dati (EOF). 

Dopo aver individuato il delimitatore di fine riga (EOL) e aver analizzato la riga:

* La logica elabora il buffer per ignorare ciò che è già stato elaborato.
* viene chiamato `PipeReader.AdvanceTo` per indicare al `PipeReader` la quantità di dati utilizzata ed esaminata.

I cicli Reader e writer terminano chiamando `Complete`. `Complete` consente alla pipe sottostante di rilasciare la memoria allocata.

### <a name="backpressure-and-flow-control"></a>Backpressure e controllo di flusso

Idealmente, la lettura e l'analisi collaborano tra loro:

* Il thread di scrittura utilizza i dati dalla rete e li inserisce nei buffer.
* Il thread di analisi è responsabile della costruzione delle strutture di dati appropriate.

In genere, l'analisi impiega più tempo rispetto alla semplice copia di blocchi di dati dalla rete:

* Il thread di lettura precede il thread di analisi.
* Il thread di lettura deve rallentare o allocare più memoria per archiviare i dati per il thread di analisi.

Per ottenere prestazioni ottimali, c'è un equilibrio tra le pause frequenti e l'allocazione di ulteriore memoria.

Per risolvere il problema precedente, il `Pipe` ha due impostazioni per controllare il flusso di dati:

* <xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determina la quantità di dati che devono essere memorizzati nel buffer prima della sospensione delle chiamate a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.
* <xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determina la quantità di dati che il lettore deve osservare prima che le chiamate a `PipeWriter.FlushAsync` riprendano.

![Diagramma con ResumeWriterThreshold e PauseWriterThreshold](./media/pipelines/resume-pause.png)

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:

* Restituisce un `ValueTask<FlushResult>` incompleto quando la quantità di dati nell'`Pipe` incrocia `PauseWriterThreshold`.
* Completa `ValueTask<FlushResult>` quando diventa inferiore `ResumeWriterThreshold`.

Vengono usati due valori per impedire il ciclo rapido, che può verificarsi se si usa un valore.

### <a name="examples"></a>Esempi

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a>PipeScheduler

In genere, quando si usa `async` e `await`, il codice asincrono riprende in un <xref:System.Threading.Tasks.TaskScheduler> o nel <xref:System.Threading.SynchronizationContext> corrente.

Quando si eseguono operazioni di I/O, è importante avere un controllo accurato sulla posizione in cui viene eseguito l'i/O. Questo controllo consente di sfruttare le cache della CPU in modo efficace. Una memorizzazione nella cache efficiente è essenziale per app ad alte prestazioni, come i server Web. <xref:System.IO.Pipelines.PipeScheduler> fornisce il controllo su dove vengono eseguiti i callback asincroni. Per impostazione predefinita:

* Viene utilizzato il <xref:System.Threading.SynchronizationContext> corrente.
* Se non è presente `SynchronizationContext`, usa il pool di thread per eseguire i callback.

[!code-csharp[](~/samples/snippets/csharp/pipelines/Program.cs?name=snippet)]

[PipeScheduler. ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) è l'implementazione <xref:System.IO.Pipelines.PipeScheduler> che accoda i callback al pool di thread. `PipeScheduler.ThreadPool` è il valore predefinito e generalmente la scelta migliore. [PipeScheduler. inline](xref:System.IO.Pipelines.PipeScheduler.Inline) può causare conseguenze impreviste, ad esempio i deadlock.

### <a name="pipe-reset"></a>Reimpostazione pipe

Spesso è efficace riutilizzare l'oggetto `Pipe`. Per reimpostare la pipe, chiamare <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> in caso di completamento di entrambe le `PipeReader` e `PipeWriter`.

## <a name="pipereader"></a>PipeReader

<xref:System.IO.Pipelines.PipeReader> gestisce la memoria per conto del chiamante. Chiamare **sempre** <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> dopo aver chiamato <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>. In questo modo, il `PipeReader` sa quando il chiamante viene eseguito con la memoria, in modo che possa essere rilevata. Il valore di `ReadOnlySequence<byte>` restituito da `PipeReader.ReadAsync` è valido solo fino alla chiamata del `PipeReader.AdvanceTo`. Non è consentito usare `ReadOnlySequence<byte>` dopo aver chiamato `PipeReader.AdvanceTo`.

`PipeReader.AdvanceTo` accetta due argomenti <xref:System.SequencePosition>:

* Il primo argomento determina la quantità di memoria utilizzata.
* Il secondo argomento determina la quantità di buffer osservata.

Contrassegnare i dati come utilizzati significa che la pipe può restituire la memoria al pool di buffer sottostante. Contrassegnare i dati come osservato controlla la chiamata successiva a `PipeReader.ReadAsync`. Contrassegnare tutto come osservato significa che la chiamata successiva a `PipeReader.ReadAsync` non verrà restituita finché non vengono scritti più dati nella pipe. Qualsiasi altro valore effettuerà la chiamata successiva a `PipeReader.ReadAsync` restituirà immediatamente i dati osservati *e* non osservati, ma i dati che sono già stati utilizzati.

### <a name="read-streaming-data-scenarios"></a>Scenari di lettura di flussi di dati

Quando si tenta di leggere i dati in streaming, è possibile che emergano due modelli tipici:

* Dato un flusso di dati, analizzare un singolo messaggio.
* Dato un flusso di dati, analizzare tutti i messaggi disponibili.

Negli esempi seguenti viene usato il metodo `TryParseMessage` per l'analisi dei messaggi da un `ReadOnlySequence<byte>`. `TryParseMessage` analizza un singolo messaggio e aggiorna il buffer di input per tagliare il messaggio analizzato dal buffer. `TryParseMessage` non fa parte di .NET, si tratta di un metodo scritto dall'utente usato nelle sezioni riportate di seguito.

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a>Leggi un singolo messaggio

Il codice seguente legge un singolo messaggio da un `PipeReader` e lo restituisce al chiamante.

[!code-csharp[ReadSingleMsg](~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs?name=snippet)]

Il codice precedente:

* Analizza un singolo messaggio.
* Aggiorna la @no__t utilizzata-0 ed esaminata `SequencePosition` in modo che punti all'inizio del buffer di input tagliato.

I due argomenti `SequencePosition` vengono aggiornati perché `TryParseMessage` rimuove il messaggio analizzato dal buffer di input. Generalmente, durante l'analisi di un singolo messaggio dal buffer, la posizione esaminata deve essere una delle seguenti:

* Fine del messaggio.
* Fine del buffer ricevuto se non è stato trovato alcun messaggio.

Il caso di un singolo messaggio può causare errori. Il passaggio di valori errati a *esaminato* può causare un'eccezione di memoria insufficiente o un ciclo infinito. Per altre informazioni, vedere la sezione [problemi comuni di PipeReader](#gotchas) in questo articolo.

### <a name="reading-multiple-messages"></a>Lettura di più messaggi

Il codice seguente legge tutti i messaggi da un `PipeReader` e chiama `ProcessMessageAsync` in ogni.

[!code-csharp[MyConnection1](~/samples/snippets/csharp/pipelines/MyConnection1.cs?name=snippet)]

### <a name="cancellation"></a>Annullamento

`PipeReader.ReadAsync`:

* Supporta il passaggio di un <xref:System.Threading.CancellationToken>.
* Genera un'eccezione <xref:System.OperationCanceledException> se il `CancellationToken` viene annullato mentre è in corso la lettura.
* Supporta un modo per annullare l'operazione di lettura corrente tramite <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, che evita la generazione di un'eccezione. La chiamata a `PipeReader.CancelPendingRead` determina la chiamata corrente o successiva a `PipeReader.ReadAsync` per restituire un <xref:System.IO.Pipelines.ReadResult> con `IsCanceled` impostato su `true`. Questo può essere utile per arrestare il ciclo di lettura esistente in modo non distruttivo e non eccezionale.

[!code-csharp[MyConnection](~/samples/snippets/csharp/pipelines/MyConnection.cs?name=snippet)]

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a>Problemi comuni di PipeReader

* Il passaggio di valori errati a `consumed` o `examined` può comportare la lettura dei dati già letti.
* Il passaggio di `buffer.End` come esaminato può causare:

  * Dati bloccati
  * È possibile che si verifichi un'eccezione di memoria insufficiente se i dati non vengono utilizzati. Ad esempio, `PipeReader.AdvanceTo(position, buffer.End)` quando si elabora un singolo messaggio alla volta dal buffer.

* Il passaggio di valori errati a `consumed` o `examined` può causare un ciclo infinito. Ad esempio, `PipeReader.AdvanceTo(buffer.Start)` se `buffer.Start` non è stato modificato, la chiamata successiva a `PipeReader.ReadAsync` verrà restituita immediatamente prima dell'arrivo di nuovi dati.
* Il passaggio di valori errati a `consumed` o `examined` può comportare un buffer infinito (eventuale memoria insufficiente).
* L'uso di `ReadOnlySequence<byte>` dopo la chiamata di `PipeReader.AdvanceTo` può comportare un danneggiamento della memoria (usare after free).
* La chiamata a `PipeReader.Complete/CompleteAsync` potrebbe causare una perdita di memoria.
* Il controllo <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> e l'uscita dalla logica di lettura prima dell'elaborazione del buffer comporta la perdita di dati. La condizione di uscita del ciclo deve essere basata su `ReadResult.Buffer.IsEmpty` e `ReadResult.IsCompleted`. Questa operazione potrebbe causare un ciclo infinito.

#### <a name="problematic-code"></a>Codice problematico

**perdita di dati** ❌

Il `ReadResult` può restituire il segmento finale dei dati quando `IsCompleted` è impostato su `true`. La mancata lettura dei dati prima di uscire dal ciclo di lettura comporterà la perdita di dati.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#1](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

**ciclo infinito** ❌

La logica seguente può comportare un ciclo infinito se il `Result.IsCompleted` è `true`, ma non esiste mai un messaggio completo nel buffer.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#2](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet2)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

Ecco un altro frammento di codice con lo stesso problema. Prima di controllare `ReadResult.IsCompleted`, viene verificata la presenza di un buffer non vuoto. Poiché si trova in un `else if`, il ciclo viene sempre completato se non esiste mai un messaggio completo nel buffer.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#3](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet3)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

**blocco imprevisto** ❌

Se si chiama in modo incondizionato `PipeReader.AdvanceTo` con `buffer.End` nella posizione `examined`, è possibile che si verifichino blocchi durante l'analisi di un singolo messaggio. La chiamata successiva a `PipeReader.AdvanceTo` non verrà restituita fino a quando:

* Sono presenti più dati scritti sulla pipe.
* E i nuovi dati non sono stati esaminati in precedenza.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#4](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet4)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

**memoria insufficiente** ❌

Con le condizioni seguenti, il codice seguente mantiene il buffering fino a quando non si verifica un <xref:System.OutOfMemoryException>:

* Nessuna dimensione massima del messaggio.
* I dati restituiti dal `PipeReader` non costituiscono un messaggio completo. Ad esempio, non viene creato un messaggio completo perché l'altro sta scrivendo un messaggio di grandi dimensioni, ad esempio un messaggio da 4 GB.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#5](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet5)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

**danneggiamento della memoria** ❌

Quando si scrivono gli helper che leggono il buffer, qualsiasi payload restituito deve essere copiato prima di chiamare `Advance`. Nell'esempio seguente viene restituita una memoria che il `Pipe` ha eliminato e può riutilizzarlo per l'operazione successiva (lettura/scrittura).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#Message](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippetMessage)]

[!code-csharp[DoNotUse#6](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet6)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a>PipeWriter

Il <xref:System.IO.Pipelines.PipeWriter> gestisce i buffer per la scrittura per conto del chiamante. `PipeWriter` implementa [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter`1). `IBufferWriter<byte>` consente di ottenere l'accesso ai buffer per eseguire scritture senza copie del buffer aggiuntive.

[!code-csharp[MyPipeWriter](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet)]

Il codice precedente:

* Richiede un buffer di almeno 5 byte dal `PipeWriter` con <xref:System.IO.Pipelines.PipeWriter.GetSpan%2A>.
* Scrive i byte per la stringa ASCII `"Hello"` nell'oggetto restituito `Span<byte>`.
* Chiama <xref:System.IO.Pipelines.PipeWriter.Advance%2A> per indicare il numero di byte scritti nel buffer.
* Scarica l'`PipeWriter`, che invia i byte al dispositivo sottostante.

Il metodo di scrittura precedente usa i buffer forniti dal `PipeWriter`. In alternativa, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:

* Copia il buffer esistente nel `PipeWriter`.
* Chiama `GetSpan`, `Advance` in base alle esigenze e chiama <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.

[!code-csharp[MyPipeWriter#2](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet2)]

### <a name="cancellation"></a>Annullamento

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supporta il passaggio di un <xref:System.Threading.CancellationToken>. Il passaggio di un `CancellationToken` comporta un `OperationCanceledException` se il token viene annullato mentre è in corso lo scaricamento. `PipeWriter.FlushAsync` supporta un modo per annullare l'operazione di scaricamento corrente tramite <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> senza generare un'eccezione. La chiamata a `PipeWriter.CancelPendingFlush` determina la chiamata corrente o successiva a `PipeWriter.FlushAsync` o `PipeWriter.WriteAsync` per restituire un <xref:System.IO.Pipelines.FlushResult> con `IsCanceled` impostato su `true`. Questa operazione può essere utile per arrestare lo scaricamento che cede in modo non distruttivo e non eccezionale.

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a>Problemi comuni di PipeWriter

* <xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> e <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> restituiscono un buffer con almeno la quantità di memoria richiesta. **Non** presupporre che le dimensioni del buffer siano esatte.
* Non vi è alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer di dimensioni.
* È necessario richiedere un nuovo buffer dopo aver chiamato <xref:System.IO.Pipelines.PipeWriter.Advance%2A> per continuare a scrivere più dati. Non è possibile scrivere nel buffer acquisito in precedenza.
* Chiamando `GetMemory` o `GetSpan` mentre è presente una chiamata incompleta a `FlushAsync` non è sicura.
* La chiamata di `Complete` o `CompleteAsync` mentre i dati non scaricati possono causare un danneggiamento della memoria.

## <a name="iduplexpipe"></a>IDuplexPipe

Il <xref:System.IO.Pipelines.IDuplexPipe> è un contratto per i tipi che supportano sia la lettura che la scrittura. Una connessione di rete, ad esempio, viene rappresentata da un `IDuplexPipe`.

 Diversamente da `Pipe` che contiene un `PipeReader` e un `PipeWriter`, `IDuplexPipe` rappresenta un singolo lato di una connessione duplex completa. Ciò significa che ciò che viene scritto nel `PipeWriter` non verrà letto da `PipeReader`.

## <a name="streams"></a>Flussi

Durante la lettura o la scrittura di dati di flusso, in genere si leggono i dati utilizzando un deserializzatore e si scrivono i dati utilizzando un serializzatore. La maggior parte di queste API del flusso di lettura e scrittura ha un parametro `Stream`. Per semplificare l'integrazione con queste API esistenti, `PipeReader` e `PipeWriter` espongono un <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.  <xref:System.IO.Pipelines.PipeWriter.AsStream%2A> restituisce un'implementazione `Stream` intorno al `PipeReader` o `PipeWriter`.
