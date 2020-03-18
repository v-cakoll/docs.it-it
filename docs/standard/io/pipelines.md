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
# <a name="systemiopipelines-in-net"></a>System.IO.Pipelines in .NET

<xref:System.IO.Pipelines>è una nuova libreria progettata per semplificare l'esecuzione di I/O ad alte prestazioni in .NET. Si tratta di una libreria destinata a .NET Standard che funziona su tutte le implementazioni di .NET.

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a>Quale problema risolve System.IO.Pipelines

<!-- corner case doesn't MT (machine translate)   -->
Le app che analizzano i dati di streaming sono composte da codice boilerplate con molti flussi di codice specializzati e insoliti. Il boilerplate e il codice speciale del caso sono complessi e difficili da mantenere.

`System.IO.Pipelines`è stato progettato per:

* Disporre di dati di streaming di analisi ad alte prestazioni.
* Ridurre la complessità del codice.

Il codice seguente è tipico per un server TCP che riceve `'\n'`messaggi delimitati da riga (delimitati da ) da un client:The following code is typical for a TCP server that receives line-delimited messages (delimited by ) from a client:

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

Il codice precedente presenta diversi problemi:The preceding code has several problems:

* L'intero messaggio (fine riga) potrebbe non essere `ReadAsync`ricevuto in una singola chiamata a .
* Ignora il risultato di `stream.ReadAsync`. `stream.ReadAsync`restituisce la quantità di dati letti.
* Non gestisce il caso in cui più `ReadAsync` righe vengono lette in una singola chiamata.
* Alloca una `byte` matrice con ogni lettura.

Per risolvere i problemi precedenti, sono necessarie le seguenti modifiche:

* Memorizzare i dati in ingresso nel buffer fino a quando non viene trovata una nuova riga.
* Analizzare tutte le righe restituite nel buffer.
* È possibile che la riga sia maggiore di 1 KB (1024 byte). Il codice deve ridimensionare il buffer di input fino a quando non viene trovato il delimitatore per adattarsi alla riga completa all'interno del buffer.

  * Se il buffer viene ridimensionato, vengono eseguite più copie del buffer man mano che nell'input vengono visualizzate righe più lunghe.
  * Per ridurre lo spazio sprecato, compattare il buffer utilizzato per le righe di lettura.

* Prendere in considerazione l'utilizzo del pool di buffer per evitare di allocare ripetutamente memoria.
* Il codice seguente risolve alcuni di questi problemi:The following code addresses some of these problems:

[!code-csharp[](~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs?name=snippet)]

Il codice precedente è complesso e non risolve tutti i problemi identificati. La rete ad alte prestazioni di solito significa scrivere codice molto complesso per ottimizzare le prestazioni. `System.IO.Pipelines`è stato progettato per semplificare la scrittura di questo tipo di codice.

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a>Pipe

La <xref:System.IO.Pipelines.Pipe> classe può essere `PipeWriter/PipeReader` utilizzata per creare una coppia. Tutti i dati `PipeWriter` scritti nel `PipeReader`è disponibile nel:

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet2)]

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a>Utilizzo di base delle tubazioni

[!code-csharp[](~/samples/snippets/csharp/pipelines/Pipe.cs?name=snippet)]

Ci sono due loop:

* `FillPipeAsync`legge da `Socket` e scrive `PipeWriter`al .
* `ReadPipeAsync`legge dalle `PipeReader` righe in entrata e analizza.

Non sono presenti buffer espliciti allocati. Tutta la `PipeReader` gestione del buffer `PipeWriter` è delegata alle implementazioni e . La delega della gestione del buffer rende più semplice per l'utilizzo del codice concentrarsi esclusivamente sulla logica di business.

Nel primo ciclo:

* <xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType>viene chiamato per ottenere memoria dal writer sottostante.
* <xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType>viene chiamato per `PipeWriter` indicare la quantità di dati scritti nel buffer.
* <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>viene chiamato per rendere i `PipeReader`dati disponibili per il file .

Nel secondo ciclo, `PipeReader` l'oggetto consumes `PipeWriter`utilizza i buffer scritti da . I buffer provengono dal socket. La chiamata `PipeReader.ReadAsync`a :

* Restituisce <xref:System.IO.Pipelines.ReadResult> un che contiene due informazioni importanti:

  * I dati che sono stati `ReadOnlySequence<byte>`letti sotto forma di .
  * Valore `IsCompleted` booleano che indica se è stata raggiunta la fine dei dati (EOF).

Dopo aver individuato il delimitatore di fine riga (EOL) e analizzato la riga:

* La logica elabora il buffer per ignorare ciò che è già stato elaborato.
* `PipeReader.AdvanceTo`viene chiamato per `PipeReader` indicare la quantità di dati sono stati utilizzati ed esaminati.

I cicli reader e writer `Complete`terminano chiamando . `Complete`consente alla pipe sottostante di rilasciare la memoria allocata.

### <a name="backpressure-and-flow-control"></a>Pressione a ristora e controllo del flusso

Idealmente, la lettura e l'analisi funzionano insieme:

* Il thread di scrittura utilizza i dati dalla rete e li inserisce nei buffer.
* Il thread di analisi è responsabile della costruzione delle strutture di dati appropriate.

In genere, l'analisi richiede più tempo rispetto alla semplice copia di blocchi di dati dalla rete:

* Il thread di lettura precede il thread di analisi.
* Il thread di lettura deve rallentare o allocare più memoria per archiviare i dati per il thread di analisi.

Per prestazioni ottimali, c'è un equilibrio tra pause frequenti e allocazione di più memoria.

Per risolvere il problema `Pipe` precedente, dispone di due impostazioni per controllare il flusso di dati:

* <xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: determina la quantità di dati <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> da memorizzare nel buffer prima che le chiamate vengano sospese.
* <xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: determina la quantità di dati che `PipeWriter.FlushAsync` il lettore deve osservare prima che le chiamate riprendano.

![Diagramma con ResumeWriterThreshold e PauseWriterThreshold](./media/pipelines/resume-pause.png)

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:

* Restituisce un `ValueTask<FlushResult>` incompleto quando la `Pipe` quantità `PauseWriterThreshold`di dati nelle intercrostati .
* Completa `ValueTask<FlushResult>` quando diventa inferiore `ResumeWriterThreshold`a .

Due valori vengono utilizzati per impedire il ciclo rapido, che può verificarsi se viene utilizzato un valore.

### <a name="examples"></a>Esempi

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a>PipeScheduler

In `async` genere, quando si utilizza e `await` <xref:System.Threading.Tasks.TaskScheduler> , il <xref:System.Threading.SynchronizationContext>codice asincrono riprende su un o sul file corrente.

Quando si esegue l'I/O, è importante disporre di un controllo granulare sulla posizione in cui viene eseguito l'I/O. Questo controllo consente di sfruttare in modo efficace le cache della CPU. La memorizzazione efficiente nella cache è fondamentale per le app ad alte prestazioni come i server Web. <xref:System.IO.Pipelines.PipeScheduler>fornisce il controllo sulla posizione di callback asincroni. Per impostazione predefinita:

* Viene <xref:System.Threading.SynchronizationContext> utilizzata la corrente.
* Se non è `SynchronizationContext`presente alcun , utilizza il pool di thread per eseguire i callback.

[!code-csharp[](~/samples/snippets/csharp/pipelines/Program.cs?name=snippet)]

[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) è <xref:System.IO.Pipelines.PipeScheduler> l'implementazione che accoda i callback al pool di thread. `PipeScheduler.ThreadPool`è l'impostazione predefinita e in genere la scelta migliore. [PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) può causare conseguenze impreviste, ad esempio deadlock.

### <a name="pipe-reset"></a>Reimpostazione tubo

È spesso efficiente riutilizzare `Pipe` l'oggetto. Per reimpostare la <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> pipe, `PipeReader` `PipeWriter` chiamare al termine di e .

## <a name="pipereader"></a>Lettore Pipe

<xref:System.IO.Pipelines.PipeReader>gestisce la memoria per conto del chiamante. **Chiamare** <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> sempre <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>dopo la chiamata a . Ciò `PipeReader` consente di sapere quando il chiamante ha finito con la memoria in modo che possa essere monitorato. Il `ReadOnlySequence<byte>` valore `PipeReader.ReadAsync` restituito da è valido `PipeReader.AdvanceTo`solo fino a quando non viene chiamata il file . È illegale utilizzare `ReadOnlySequence<byte>` dopo `PipeReader.AdvanceTo`aver chiamato .

`PipeReader.AdvanceTo`accetta <xref:System.SequencePosition> due argomenti:

* Il primo argomento determina la quantità di memoria utilizzata.
* Il secondo argomento determina la quantità di buffer osservata.

Contrassegnare i dati come utilizzati significa che la pipe può restituire la memoria al pool di buffer sottostante. Il contrassegno dei dati come `PipeReader.ReadAsync` osservati controlla l'azione della chiamata successiva. Contrassegnare tutto come osservato significa `PipeReader.ReadAsync` che la chiamata successiva a non verrà restituita fino a quando non sono presenti più dati scritti nella pipe. Qualsiasi altro valore effettuerà `PipeReader.ReadAsync` la chiamata successiva per restituire immediatamente i dati osservati *e* non osservati, ma i dati che sono già stati utilizzati.

### <a name="read-streaming-data-scenarios"></a>Leggere gli scenari di streaming dei datiRead streaming data scenarios

Esistono un paio di modelli tipici che emergono quando si tenta di leggere i dati in streaming:There are a couple of typical patterns that emerge when trying to read streaming data:

* Dato un flusso di dati, analizzare un singolo messaggio.
* Dato un flusso di dati, analizzare tutti i messaggi disponibili.

Negli esempi seguenti `TryParseMessage` viene utilizzato il metodo `ReadOnlySequence<byte>`per l'analisi dei messaggi da un oggetto . `TryParseMessage`analizza un singolo messaggio e aggiorna il buffer di input per tagliare il messaggio analizzato dal buffer. `TryParseMessage`non fa parte di .NET, è un metodo scritto dall'utente utilizzato nelle sezioni seguenti.

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a>Leggere un singolo messaggio

Il codice seguente legge un `PipeReader` singolo messaggio da a e lo restituisce al chiamante.

[!code-csharp[ReadSingleMsg](~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs?name=snippet)]

Il codice precedente:

* Analizza un singolo messaggio.
* Aggiorna l'oggetto consumato `SequencePosition` ed esaminato `SequencePosition` in modo che punti all'inizio del buffer di input tagliato.

I `SequencePosition` due argomenti `TryParseMessage` vengono aggiornati perché rimuove il messaggio analizzato dal buffer di input. In genere, durante l'analisi di un singolo messaggio dal buffer, la posizione esaminata deve essere uno dei seguenti:

* Fine del messaggio.
* Fine del buffer ricevuto se non è stato trovato alcun messaggio.

Il singolo caso di messaggio ha il maggior potenziale di errori. Il passaggio dei valori errati da *esaminare* può causare un'eccezione di memoria insufficiente o un ciclo infinito. Per altre informazioni, vedere la sezione [Problemi comuni di PipeReader](#gotchas) in questo articolo.

### <a name="reading-multiple-messages"></a>Lettura di più messaggi

Il codice seguente legge tutti `PipeReader` i `ProcessMessageAsync` messaggi da a e chiama su ciascuno.

[!code-csharp[MyConnection1](~/samples/snippets/csharp/pipelines/MyConnection1.cs?name=snippet)]

### <a name="cancellation"></a>Annullamento

`PipeReader.ReadAsync`:

* Supporta il <xref:System.Threading.CancellationToken>passaggio di un oggetto .
* Genera un <xref:System.OperationCanceledException> se `CancellationToken` l'oggetto viene annullato mentre è presente una lettura in sospeso.
* Supporta un modo per annullare <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>l'operazione di lettura corrente tramite , che evita la generazione di un'eccezione. La `PipeReader.CancelPendingRead` chiamata fa sì `PipeReader.ReadAsync` che la <xref:System.IO.Pipelines.ReadResult> `IsCanceled` chiamata `true`corrente o successiva a restituisca un oggetto con impostato su . Ciò può essere utile per arrestare il ciclo di lettura esistente in modo non distruttivo e non eccezionale.

[!code-csharp[MyConnection](~/samples/snippets/csharp/pipelines/MyConnection.cs?name=snippet)]

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a>Problemi comuni di PipeReader

* Il passaggio `consumed` di `examined` valori errati a o può comportare la lettura dei dati già letti.
* Il `buffer.End` passaggio come esaminato può comportare:

  * Dati in stallo
  * Forse un'eventuale eccezione di memoria insufficiente (OOM) se i dati non vengono utilizzati. Ad esempio, `PipeReader.AdvanceTo(position, buffer.End)` durante l'elaborazione di un singolo messaggio alla volta dal buffer.

* Il passaggio `consumed` dei `examined` valori errati a o può comportare un ciclo infinito. Ad `PipeReader.AdvanceTo(buffer.Start)` esempio, `buffer.Start` se non è stato modificato, la chiamata successiva a `PipeReader.ReadAsync` restituire immediatamente prima dell'arrivo di nuovi dati.
* Il passaggio `consumed` dei `examined` valori errati a o può causare un buffering infinito (eventuale OOM).
* L'utilizzo `ReadOnlySequence<byte>` `PipeReader.AdvanceTo` della chiamata dopo può causare il danneggiamento della memoria (utilizzare dopo libero).
* La mancata chiamata `PipeReader.Complete/CompleteAsync` può causare una perdita di memoria.
* Il <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> controllo e l'uscita dalla logica di lettura prima dell'elaborazione del buffer comportano la perdita di dati. La condizione di uscita `ReadResult.Buffer.IsEmpty` del `ReadResult.IsCompleted`ciclo deve essere basata su e . Questa operazione in modo non corretto potrebbe causare un ciclo infinito.

#### <a name="problematic-code"></a>Codice problematico

❌**Perdita di dati**

L'oggetto `ReadResult` può restituire il `IsCompleted` segmento `true`finale di dati quando è impostato su . La non lettura dei dati prima di uscire dal ciclo di lettura comporterà la perdita di dati.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#1](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌**Ciclo infinito**

La logica seguente può comportare `Result.IsCompleted` un `true` ciclo infinito se l'oggetto è ma non è mai presente un messaggio completo nel buffer.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#2](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet2)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

Ecco un altro pezzo di codice con lo stesso problema. Sta verificando la presenza di un `ReadResult.IsCompleted`buffer non vuoto prima di controllare . Perché è in `else if`un , verrà eseguito un ciclo per sempre se non c'è mai un messaggio completo nel buffer.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#3](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet3)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌**Inaspettato Hang**

La chiamata `PipeReader.AdvanceTo` incondizionata con `buffer.End` nella `examined` posizione può causare blocchi durante l'analisi di un singolo messaggio. La prossima `PipeReader.AdvanceTo` chiamata a non tornerà fino a:

* Ci sono più dati scritti nella pipe.
* E i nuovi dati non sono stati esaminati in precedenza.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#4](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet4)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌**Memoria insufficiente (OOM)**

Con le seguenti condizioni, il codice <xref:System.OutOfMemoryException> seguente mantiene il buffering fino a quando non si verifica un si verifica:With the following conditions, the following code keeps buffering until an occurs:

* Non esiste una dimensione massima dei messaggi.
* I dati restituiti `PipeReader` da non costituiscono un messaggio completo. Ad esempio, non crea un messaggio completo perché l'altro lato sta scrivendo un messaggio di grandi dimensioni (ad esempio, un messaggio da 4 GB).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#5](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet5)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌**Danneggiamento della memoria**

Quando si scrivono helper che leggono il buffer, qualsiasi payload restituito deve essere copiato prima di chiamare `Advance`. L'esempio seguente restituirà `Pipe` memoria che l'oggetto ha eliminato e potrebbe riutilizzarla per l'operazione successiva (lettura/scrittura).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

[!code-csharp[DoNotUse#Message](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippetMessage)]

[!code-csharp[DoNotUse#6](~/samples/snippets/csharp/pipelines/DoNotUse.cs?name=snippet6)]

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a>PipeWriter

Il <xref:System.IO.Pipelines.PipeWriter> gestisce i buffer per la scrittura per conto del chiamante. `PipeWriter`implementa [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601). `IBufferWriter<byte>`consente di ottenere l'accesso ai buffer per eseguire scritture senza copie aggiuntive del buffer.

[!code-csharp[MyPipeWriter](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet)]

Il codice precedente:

* Richiede un buffer di almeno `PipeWriter` 5 <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>byte dall'oggetto using .
* Scrive i byte `"Hello"` per la `Memory<byte>`stringa ASCII nell'oggetto restituito.
* Chiamate <xref:System.IO.Pipelines.PipeWriter.Advance%2A> per indicare quanti byte sono stati scritti nel buffer.
* Scarica l'oggetto `PipeWriter`, che invia i byte al dispositivo sottostante.

Il metodo di scrittura precedente utilizza `PipeWriter`i buffer forniti dall'oggetto . In alternativa, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:

* Copia il buffer esistente `PipeWriter`nell'oggetto .
* Chiamate `GetSpan` `Advance` , a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>seconda dei casi e chiamate .

[!code-csharp[MyPipeWriter#2](~/samples/snippets/csharp/pipelines/MyPipeWriter.cs?name=snippet2)]

### <a name="cancellation"></a>Annullamento

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>supporta il <xref:System.Threading.CancellationToken>passaggio di un oggetto . Il `CancellationToken` passaggio `OperationCanceledException` di un risultato genera un se il token viene annullato mentre è presente un colore in sospeso. `PipeWriter.FlushAsync`supporta un modo per annullare <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> l'operazione di svuotamento corrente tramite senza generare un'eccezione. La `PipeWriter.CancelPendingFlush` chiamata fa sì `PipeWriter.FlushAsync` che `PipeWriter.WriteAsync` la <xref:System.IO.Pipelines.FlushResult> chiamata `IsCanceled` corrente `true`o successiva a o restituisca un oggetto con impostato su . Questo può essere utile per arrestare il colore cedevole in modo non distruttivo e non eccezionale.

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a>Problemi comuni di PipeWriter

* <xref:System.IO.Pipelines.PipeWriter.GetSpan%2A>e <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> restituire un buffer con almeno la quantità di memoria richiesta. **Non** presupporre che le dimensioni esatte del buffer.
* Non esiste alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer delle stesse dimensioni.
* È necessario richiedere un <xref:System.IO.Pipelines.PipeWriter.Advance%2A> nuovo buffer dopo la chiamata per continuare a scrivere altri dati. Impossibile scrivere nel buffer acquisito in precedenza.
* Chiamare `GetMemory` `GetSpan` o mentre c'è una `FlushAsync` chiamata incompleta a non è sicuro.
* La `Complete` `CompleteAsync` chiamata o mentre sono presenti dati non scaricati può causare il danneggiamento della memoria.

## <a name="iduplexpipe"></a>IDuplexPipe

Il <xref:System.IO.Pipelines.IDuplexPipe> è un contratto per i tipi che supportano sia la lettura che la scrittura. Ad esempio, una connessione di `IDuplexPipe`rete sarebbe rappresentata da un oggetto .

 A `Pipe` differenza `PipeReader` di `PipeWriter`che `IDuplexPipe` contiene a e un , rappresenta un singolo lato di una connessione duplex completa. Ciò significa che `PipeWriter` ciò che è `PipeReader`scritto per il non sarà letto dal .

## <a name="streams"></a>Flussi

Quando si leggono o si scrivono dati di flusso, in genere si leggono i dati utilizzando un deserializzatore e si scrivono dati utilizzando un serializzatore. La maggior parte di queste API `Stream` di flusso di lettura e scrittura hanno un parametro. Per semplificare l'integrazione con queste `PipeReader` `PipeWriter` API <xref:System.IO.Pipelines.PipeReader.AsStream%2A>esistenti ed esporre un file .  <xref:System.IO.Pipelines.PipeWriter.AsStream%2A>restituisce `Stream` un'implementazione intorno a `PipeReader` o `PipeWriter`.
