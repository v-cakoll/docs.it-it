---
title: System. buffers-.NET
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
# <a name="work-with-buffers-in-net"></a>Usare i buffer in .NET

Questo articolo fornisce una panoramica dei tipi che consentono di leggere i dati eseguiti su più buffer. Vengono utilizzati principalmente per supportare <xref:System.IO.Pipelines.PipeReader> gli oggetti.

## <a name="ibufferwritert"></a>IBufferWriter \< T\>

<xref:System.Buffers.IBufferWriter%601?displayProperty=fullName>è un contratto per la scrittura sincrona nel buffer. Al livello più basso, l'interfaccia:

- È di base e non è difficile da usare.
- Consente l'accesso a un oggetto <xref:System.Memory%601> o <xref:System.Span%601> . `Memory<T>`In o `Span<T>` è possibile scrivere in ed è possibile determinare il numero di `T` elementi scritti.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

Il metodo precedente:

- Richiede un buffer di almeno 5 byte dal `IBufferWriter<byte>` utilizzando `GetSpan(5)` .
- Scrive i byte per la stringa ASCII "Hello" nell'oggetto restituito `Span<byte>` .
- Chiama <xref:System.Buffers.IBufferWriter%601> per indicare il numero di byte scritti nel buffer.

Questo metodo di scrittura usa il `Memory<T>` / `Span<T>` buffer fornito da `IBufferWriter<T>` . In alternativa, <xref:System.Buffers.BuffersExtensions.Write%2A> è possibile usare il metodo di estensione per copiare un buffer esistente nell'oggetto `IBufferWriter<T>` . `Write`esegue una chiamata nel modo `GetSpan` / `Advance` appropriato, quindi non è necessario chiamare `Advance` dopo la scrittura:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<xref:System.Buffers.ArrayBufferWriter%601>è un'implementazione di `IBufferWriter<T>` il cui archivio di backup è una singola matrice contigua.

### <a name="ibufferwriter-common-problems"></a>Problemi comuni di IBufferWriter

- `GetSpan`e `GetMemory` restituiscono un buffer con almeno la quantità di memoria richiesta. Non presupporre che le dimensioni del buffer siano esatte.
- Non vi è alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer di dimensioni.
- È necessario richiedere un nuovo buffer dopo la chiamata `Advance` a per continuare a scrivere più dati. Non è possibile scrivere in un buffer precedentemente acquisito dopo che `Advance` è stato chiamato.

## <a name="readonlysequencet"></a>ReadOnlySequence \< T\>

![ReadOnlySequence che mostra la memoria nella pipe e sotto tale posizione della sequenza della memoria di sola lettura](media/buffers/ro-sequence.png)

<xref:System.Buffers.ReadOnlySequence%601>è uno struct che può rappresentare una sequenza contigua o non contigua di `T` . Può essere creato da:

1. Come `T[]`
1. Come `ReadOnlyMemory<T>`
1. Coppia di nodo elenco collegato <xref:System.Buffers.ReadOnlySequenceSegment%601> e indice per rappresentare la posizione iniziale e finale della sequenza.

La terza rappresentazione è la più interessante perché presenta implicazioni sulle prestazioni per varie operazioni in `ReadOnlySequence<T>` :

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

A causa di questa rappresentazione mista, `ReadOnlySequence<T>` espone indici come `SequencePosition` anziché come Integer. R `SequencePosition` :

- È un valore opaco che rappresenta un indice nell'oggetto da `ReadOnlySequence<T>` cui ha avuto origine.
- È costituito da due parti, un numero intero e un oggetto. Gli elementi rappresentati da questi due valori sono legati all'implementazione di `ReadOnlySequence<T>` .

### <a name="access-data"></a>Accedere ai dati

`ReadOnlySequence<T>`Espone i dati come enumerabile di `ReadOnlyMemory<T>` . L'enumerazione di ogni segmento può essere eseguita usando un'istruzione foreach di base:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

Il metodo precedente Cerca un byte specifico in ogni segmento. Se è necessario tenere traccia di ogni segmento `SequencePosition` , <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> è più appropriato. Nell'esempio seguente viene modificato il codice precedente per restituire un `SequencePosition` anziché un numero intero. La restituzione di un oggetto `SequencePosition` ha il vantaggio di consentire al chiamante di evitare una seconda analisi per ottenere i dati in corrispondenza di un indice specifico.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

La combinazione di `SequencePosition` e `TryGet` funge da enumeratore. Il campo position viene modificato all'inizio di ogni iterazione in modo che sia l'inizio di ogni segmento all'interno di `ReadOnlySequence<T>` .

Il metodo precedente esiste come metodo di estensione su `ReadOnlySequence<T>` . <xref:System.Buffers.BuffersExtensions.PositionOf%2A>può essere usato per semplificare il codice precedente:

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a>Elaborare un ReadOnlySequence \< T\>

L'elaborazione di un oggetto `ReadOnlySequence<T>` può essere complessa perché i dati possono essere suddivisi in più segmenti all'interno della sequenza. Per ottenere prestazioni ottimali, suddividere il codice in due percorsi:

- Percorso veloce che riguarda il singolo case del segmento.
- Percorso lento che riguarda la suddivisione dei dati tra i segmenti.

Esistono alcuni approcci che possono essere usati per elaborare i dati in sequenze multisegmentate:

- Usare [`SequenceReader<T>`](#sequencereadert) .
- Analizza il segmento di dati in base al segmento, tenendo traccia dell' `SequencePosition` indice e all'interno del segmento analizzato. In questo modo si evitano allocazioni non necessarie, ma possono risultare inefficienti, specialmente per i buffer di piccole dimensioni.
- Copiare l'oggetto `ReadOnlySequence<T>` in una matrice contigua e considerarlo come un singolo buffer:
  - Se la dimensione di `ReadOnlySequence<T>` è ridotta, può essere ragionevole copiare i dati in un buffer allocato nello stack usando l'operatore [stackalloc](../../csharp/language-reference/operators/stackalloc.md) .
  - Copiare `ReadOnlySequence<T>` in una matrice in pool usando <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType> .
  - Usare [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A). Questa operazione non è consigliata nei percorsi sensibili quando alloca un nuovo nell' `T[]` heap.

Gli esempi seguenti illustrano alcuni casi comuni per l'elaborazione `ReadOnlySequence<byte>` :

##### <a name="process-binary-data"></a>Elaborare dati binari

Nell'esempio seguente viene analizzata una lunghezza Integer a 4 byte big-endian dall'inizio di `ReadOnlySequence<byte>` .

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a>Elabora dati di testo

L'esempio seguente:

- Trova il primo carattere di nuova riga ( `\r\n` ) nell'oggetto `ReadOnlySequence<byte>` e lo restituisce tramite il parametro out "line".
- Taglia la riga, esclusa `\r\n` dal buffer di input.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a>Segmenti vuoti

È valido per archiviare segmenti vuoti all'interno di un oggetto `ReadOnlySequence<T>` . È possibile che si verifichino segmenti vuoti durante l'enumerazione dei segmenti in modo esplicito:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

Il codice precedente crea un oggetto `ReadOnlySequence<byte>` con segmenti vuoti e Mostra come tali segmenti vuoti influiscono sulle varie API:

- `ReadOnlySequence<T>.Slice`con un oggetto `SequencePosition` che punta a un segmento vuoto, conserva tale segmento.
- `ReadOnlySequence<T>.Slice`con un valore int ignora i segmenti vuoti.
- L'enumerazione di `ReadOnlySequence<T>` enumera i segmenti vuoti.

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a>Potenziali problemi con ReadOnlySequence \< T> e SequencePosition

Esistono diversi risultati insoliti quando si ha a che fare con un rispetto a un `ReadOnlySequence<T>` / `SequencePosition` normale `ReadOnlySpan<T>` / `ReadOnlyMemory<T>` / `T[]` / `int` :

- `SequencePosition`è un indicatore di posizione per una specifica `ReadOnlySequence<T>` , non una posizione assoluta. Poiché è relativo a un oggetto specifico `ReadOnlySequence<T>` , non ha significato se usato all'esterno dell'oggetto da `ReadOnlySequence<T>` cui ha avuto origine.
- Non è possibile eseguire operazioni aritmetiche su `SequencePosition` senza `ReadOnlySequence<T>` . Ciò significa che vengono scritti gli elementi di base, ad esempio `position++` `ReadOnlySequence<T>.GetPosition(position, 1)` .
- `GetPosition(long)`non **supporta** indici negativi. Ciò significa che non è possibile ottenere il secondo carattere finale senza scorrere tutti i segmenti.
- `SequencePosition`Non è possibile confrontare due, rendendo difficile:
  - Verificare se una posizione è maggiore o minore di un'altra posizione.
  - Scrivere alcuni algoritmi di analisi.
- `ReadOnlySequence<T>`è maggiore di un riferimento a un oggetto e deve essere passato da [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) o [ref](../../csharp/language-reference/keywords/ref.md) , ove possibile. `ReadOnlySequence<T>`Il passaggio `in` o `ref` la riduzione delle copie dello [struct](../../csharp/language-reference/builtin-types/struct.md).
- Segmenti vuoti:
  - Sono validi in un oggetto `ReadOnlySequence<T>` .
  - Può essere visualizzato quando si esegue l'iterazione usando il `ReadOnlySequence<T>.TryGet` metodo.
  - Può comparire sezionare la sequenza usando il `ReadOnlySequence<T>.Slice()` metodo con `SequencePosition` gli oggetti.

## <a name="sequencereadert"></a>SequenceReader \< T\>

<xref:System.Buffers.SequenceReader%601>:

- È un nuovo tipo introdotto in .NET Core 3,0 per semplificare l'elaborazione di un oggetto `ReadOnlySequence<T>` .
- Unifica le differenze tra un singolo segmento `ReadOnlySequence<T>` e più segmenti `ReadOnlySequence<T>` .
- Fornisce helper per la lettura di dati binari e di testo ( `byte` e `char` ) che possono o meno essere suddivisi tra segmenti.

Sono disponibili metodi predefiniti per gestire l'elaborazione di dati binari e delimitati. La sezione seguente illustra l'aspetto degli stessi metodi con `SequenceReader<T>` :

### <a name="access-data"></a>Accedere ai dati

`SequenceReader<T>`dispone di metodi per l'enumerazione diretta dei dati all'interno di `ReadOnlySequence<T>` . Il codice seguente è un esempio di elaborazione di un `ReadOnlySequence<byte>` oggetto `byte` alla volta:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

`CurrentSpan`Espone il segmento corrente `Span` , che è simile a quanto è stato fatto nel metodo manualmente.

### <a name="use-position"></a>Usa posizione

Il codice seguente è un'implementazione di esempio dell' `FindIndexOf` utilizzo di `SequenceReader<T>` :

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a>Elaborare dati binari

Nell'esempio seguente viene analizzata una lunghezza Integer a 4 byte big-endian dall'inizio di `ReadOnlySequence<byte>` .

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a>Elabora dati di testo

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a>\< \> Problemi comuni di SequenceReader

- Poiché `SequenceReader<T>` è uno struct modificabile, deve essere sempre passato per [riferimento](../../csharp/language-reference/keywords/ref.md).
- `SequenceReader<T>`è uno [struct Ref](../../csharp/language-reference/builtin-types/struct.md#ref-struct) , che può essere usato solo nei metodi sincroni e non può essere archiviato in campi. Per altre informazioni, vedere [scrivere codice C# sicuro ed efficiente](../../csharp/write-safe-efficient-code.md).
- `SequenceReader<T>`è ottimizzato per l'utilizzo come lettore di sola trasmissione. `Rewind`è destinato a backup di piccole dimensioni che non possono essere risolti utilizzando altre `Read` `Peek` API, e `IsNext` .
