---
title: System.Buffers - .NET
ms.date: 12/05/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: d113def0182dc6a5bcea6c18b2d0e4b475946e31
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739614"
---
# <a name="work-with-buffers-in-net"></a>Utilizzare i buffer in .NET

In questo articolo viene fornita una panoramica dei tipi che consentono di leggere i dati eseguiti in più buffer. Vengono utilizzati principalmente per <xref:System.IO.Pipelines.PipeReader> supportare gli oggetti.

## <a name="ibufferwritert"></a>IBufferWriter\<T\>

<xref:System.Buffers.IBufferWriter%601?displayProperty=fullName>è un contratto per la scrittura con buffer sincrono. Al livello più basso, l'interfaccia:

- È essenziale e non è difficile da usare.
- Consente l'accesso a un <xref:System.Memory%601> o <xref:System.Span%601>. L'oggetto `Memory<T>` o `Span<T>` può essere scritto `T` ed è possibile determinare il numero di elementi scritti.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

Il metodo precedente:

- Richiede un buffer di almeno `IBufferWriter<byte>` 5 `GetSpan(5)`byte dall'oggetto using .
- Scrive i byte per la stringa ASCII `Span<byte>`"Hello" nella stringa restituita.
- Chiamate <xref:System.Buffers.IBufferWriter%601> per indicare quanti byte sono stati scritti nel buffer.

Questo metodo di `Memory<T>` / `Span<T>` scrittura utilizza `IBufferWriter<T>`il buffer fornito dall'oggetto . In alternativa, <xref:System.Buffers.BuffersExtensions.Write%2A> il metodo di estensione può essere `IBufferWriter<T>`utilizzato per copiare un buffer esistente nell'oggetto . `Write`fa il lavoro `GetSpan` / `Advance` di chiamata a seconda dei `Advance` casi, quindi non c'è bisogno di chiamare dopo la scrittura:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<xref:System.Buffers.ArrayBufferWriter%601>è un'implementazione del `IBufferWriter<T>` cui archivio di backup è una singola matrice contigua.

### <a name="ibufferwriter-common-problems"></a>Problemi comuni di IBufferWriter

- `GetSpan`e `GetMemory` restituire un buffer con almeno la quantità di memoria richiesta. Non presupporre che le dimensioni esatte del buffer.
- Non esiste alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer delle stesse dimensioni.
- È necessario richiedere un `Advance` nuovo buffer dopo la chiamata per continuare a scrivere altri dati. Un buffer acquisito in precedenza non può essere scritto dopo `Advance` che è stato chiamato.

## <a name="readonlysequencet"></a>ReadOnlySequence\<T\>

![ReadOnlySequence che mostra la memoria nella pipe e al di sotto della posizione della sequenza della memoria di sola lettura](media/buffers/ro-sequence.png)

<xref:System.Buffers.ReadOnlySequence%601>è una struttura che può rappresentare una sequenza contigua o non contigua di `T`. Può essere costruito da:

1. Come `T[]`
1. Come `ReadOnlyMemory<T>`
1. Coppia di nodo <xref:System.Buffers.ReadOnlySequenceSegment%601> e indice dell'elenco collegato per rappresentare la posizione iniziale e finale della sequenza.

La terza rappresentazione è la più interessante in quanto `ReadOnlySequence<T>`ha implicazioni sulle prestazioni su varie operazioni sul :

|Rappresentazione|Operazione|Complessità|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

A causa di questa `ReadOnlySequence<T>` rappresentazione mista, espone gli indici come `SequencePosition` anziché come integer. A `SequencePosition`:

- È un valore opaco che `ReadOnlySequence<T>` rappresenta un indice nel punto in cui ha avuto origine.
- È costituito da due parti, un numero intero e un oggetto. Ciò che questi due valori rappresentano `ReadOnlySequence<T>`sono legati all'implementazione di .

### <a name="access-data"></a>Accedere ai dati

Espone `ReadOnlySequence<T>` i dati come `ReadOnlyMemory<T>`enumerabili di . L'enumerazione di ciascuno dei segmenti può essere eseguita utilizzando un foreach di base:Enumerating each of the segments can be done using a basic foreach:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

Il metodo precedente cerca in ogni segmento un byte specifico. Se è necessario tenere traccia di `SequencePosition` <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> ogni segmento di , è più appropriato. L'esempio successivo modifica il codice `SequencePosition` precedente in modo che restituisca un numero intero anziché un numero intero. La restituzione di un `SequencePosition` ha il vantaggio di consentire al chiamante di evitare una seconda analisi per ottenere i dati in corrispondenza di un indice specifico.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

La combinazione `SequencePosition` `TryGet` e agisce come un enumeratore. Il campo posizione viene modificato all'inizio di ogni iterazione per essere iniziale di ogni segmento all'interno di `ReadOnlySequence<T>`.

Il metodo precedente esiste come `ReadOnlySequence<T>`metodo di estensione in . <xref:System.Buffers.BuffersExtensions.PositionOf%2A>può essere utilizzato per semplificare il codice precedente:

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a>Elaborare un\<ReadOnlySequence TProcess a ReadOnlySequence T\>

L'elaborazione di un `ReadOnlySequence<T>` oggetto può essere difficile poiché i dati possono essere suddivisi in più segmenti all'interno della sequenza. Per ottenere prestazioni ottimali, suddividere il codice in due percorsi:For the best performance, split code into two paths:

- Un percorso veloce che si occupa della custodia per singolo segmento.
- Percorso lento che gestisce i dati suddivisi tra i segmenti.

Esistono alcuni approcci che possono essere utilizzati per elaborare i dati in sequenze multisegmentate:There are a few approaches that can be used to process data in multi-segmented sequences:

- Utilizzare [`SequenceReader<T>`](#sequencereadert)il file .
- Analizzare il segmento di `SequencePosition` dati per segmento, tenendo traccia di e l'indice all'interno del segmento analizzato. In questo modo si evitano allocazioni non necessarie, ma possono essere inefficienti, in particolare per i buffer di piccole dimensioni.
- Copiare `ReadOnlySequence<T>` l'oggetto in una matrice contigua e trattarlo come un singolo buffer:Copy the to a contiguo array and treat it as a single buffer:
  - Se la dimensione `ReadOnlySequence<T>` di è piccola, può essere ragionevole copiare i dati in un buffer allocato nello stack utilizzando l'operatore [stackalloc.](../../csharp/language-reference/operators/stackalloc.md)
  - Copiare `ReadOnlySequence<T>` l'oggetto in <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>una matrice in pool utilizzando .
  - Usare [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A). Questa operazione non è consigliata nei percorsi attivi in quanto alloca un nuovo `T[]` nell'heap.

Negli esempi seguenti vengono illustrati `ReadOnlySequence<byte>`alcuni casi comuni per l'elaborazione:

##### <a name="process-binary-data"></a>Elaborare i dati binari

Nell'esempio riportato di seguito viene analizzata una lunghezza intera `ReadOnlySequence<byte>`bigendian a 4 byte dall'inizio dell'oggetto .

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a>Elaborare i dati di testo

L'esempio seguente:

- Trova la prima`\r\n`nuova riga `ReadOnlySequence<byte>` ( ) in e la restituisce tramite il parametro 'line' out.
- Taglia la riga, escludendo l'oggetto `\r\n` dal buffer di input.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a>Segmenti vuoti

È valido archiviare segmenti vuoti all'interno di un `ReadOnlySequence<T>`oggetto . Durante l'enumerazione esplicita dei segmenti possono verificarsi segmenti vuoti:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

Il codice precedente `ReadOnlySequence<byte>` crea un con segmenti vuoti e mostra come tali segmenti vuoti influiscono sulle varie API:The preceding code creates a with empty segments and shows how those empty segments affect the various APIs:

- `ReadOnlySequence<T>.Slice`con `SequencePosition` un che punta a un segmento vuoto mantiene quel segmento.
- `ReadOnlySequence<T>.Slice`con un int salta i segmenti vuoti.
- L'enumerazione dell'enumerazione `ReadOnlySequence<T>` enumera i segmenti vuoti.

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a>Potenziali problemi con\<ReadOnlySequence T> e SequencePosition

Ci sono diversi esiti insoliti quando `ReadOnlySpan<T>` / `ReadOnlyMemory<T>` / `T[]` / `int`si tratta di un `ReadOnlySequence<T>` / `SequencePosition` vs un normale :

- `SequencePosition`è un indicatore di `ReadOnlySequence<T>`posizione per una posizione specifica, non una posizione assoluta. Poiché è relativo `ReadOnlySequence<T>`a uno specifico , non ha `ReadOnlySequence<T>` significato se utilizzato al di fuori del punto di origine.
- L'aritmetica non `SequencePosition` può `ReadOnlySequence<T>`essere eseguita senza l'oggetto . Ciò significa che `position++` fare `ReadOnlySequence<T>.GetPosition(position, 1)`cose di base come è scritto .
- `GetPosition(long)`**non** supporta indici negativi. Ciò significa che è impossibile ottenere il penultimo carattere senza camminare tutti i segmenti.
- Due `SequencePosition` non possono essere confrontati, rendendo difficile:
  - Sapere se una posizione è maggiore o minore di un'altra posizione.
  - Scrivere alcuni algoritmi di analisi.
- `ReadOnlySequence<T>`è più grande di un riferimento a un oggetto e deve essere passato da [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) o [ref](../../csharp/language-reference/keywords/ref.md) dove possibile. Il `ReadOnlySequence<T>` `in` passaggio o `ref` riduce le copie della [struttura](../../csharp/language-reference/builtin-types/struct.md).
- Segmenti vuoti:
  - Sono validi `ReadOnlySequence<T>`all'interno di un file .
  - Può apparire quando si `ReadOnlySequence<T>.TryGet` scorre utilizzando il metodo .
  - Può apparire sezionare `ReadOnlySequence<T>.Slice()` la `SequencePosition` sequenza utilizzando il metodo con gli oggetti.

## <a name="sequencereadert"></a>SequenceReader\<T\>

<xref:System.Buffers.SequenceReader%601>:

- È un nuovo tipo introdotto in .NET Core 3.0 per semplificare l'elaborazione di un `ReadOnlySequence<T>`oggetto .
- Unifica le differenze `ReadOnlySequence<T>` tra un `ReadOnlySequence<T>`singolo segmento e più segmenti.
- Fornisce helper per la lettura`byte` di `char`dati binari e di testo ( e ) che possono o non possono essere suddivisi tra segmenti.

Esistono metodi incorporati per gestire l'elaborazione di dati binari e delimitati. Nella sezione seguente viene illustrato l'aspetto di questi stessi metodi con il `SequenceReader<T>`:

### <a name="access-data"></a>Accedere ai dati

`SequenceReader<T>`dispone di metodi per enumerare i dati all'interno del `ReadOnlySequence<T>` direttamente. Il codice seguente è un `ReadOnlySequence<byte>` `byte` esempio di elaborazione di un oggetto alla volta:The following code is an example of processing a at a at a at a time:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

L'oggetto `CurrentSpan` espone , `Span`ovvero quello del segmento corrente, che è simile a quello eseguito manualmente nel metodo.

### <a name="use-position"></a>Usa posizione

Il codice seguente è `FindIndexOf` un `SequenceReader<T>`esempio di implementazione dell'utilizzo di :

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a>Elaborare i dati binari

Nell'esempio riportato di seguito viene analizzata una lunghezza intera `ReadOnlySequence<byte>`bigendian a 4 byte dall'inizio dell'oggetto .

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a>Elaborare i dati di testo

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a>SequenceReader\<\> T problemi comuni

- Poiché `SequenceReader<T>` è una struttura modificabile, deve essere sempre passata per [riferimento](../../csharp/language-reference/keywords/ref.md).
- `SequenceReader<T>`è uno [struct di riferimento,](../../csharp/language-reference/builtin-types/struct.md#ref-struct) pertanto può essere utilizzato solo nei metodi sincroni e non può essere archiviato nei campi. Per ulteriori informazioni, consultate Scrivere codice [C, sicuro ed efficiente.](../../csharp/write-safe-efficient-code.md)
- `SequenceReader<T>`è ottimizzato per l'uso come lettore forward-only. `Rewind`è destinato a backup di piccole dimensioni che `Read`non `Peek`possono `IsNext` essere risolti utilizzando altre API , e , .
