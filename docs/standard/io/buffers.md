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
# <a name="work-with-buffers-in-net"></a><span data-ttu-id="23ae7-102">Usare i buffer in .NET</span><span class="sxs-lookup"><span data-stu-id="23ae7-102">Work with Buffers in .NET</span></span>

<span data-ttu-id="23ae7-103">Questo articolo fornisce una panoramica dei tipi che consentono di leggere i dati eseguiti su più buffer.</span><span class="sxs-lookup"><span data-stu-id="23ae7-103">This article provides an overview of types that help read data that runs across multiple buffers.</span></span> <span data-ttu-id="23ae7-104">Vengono utilizzati principalmente per supportare <xref:System.IO.Pipelines.PipeReader> gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-104">They're primarily used to support <xref:System.IO.Pipelines.PipeReader> objects.</span></span>

## <a name="ibufferwritert"></a><span data-ttu-id="23ae7-105">IBufferWriter \< T\></span><span class="sxs-lookup"><span data-stu-id="23ae7-105">IBufferWriter\<T\></span></span>

<span data-ttu-id="23ae7-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName>è un contratto per la scrittura sincrona nel buffer.</span><span class="sxs-lookup"><span data-stu-id="23ae7-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> is a contract for synchronous buffered writing.</span></span> <span data-ttu-id="23ae7-107">Al livello più basso, l'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="23ae7-107">At the lowest level, the interface:</span></span>

- <span data-ttu-id="23ae7-108">È di base e non è difficile da usare.</span><span class="sxs-lookup"><span data-stu-id="23ae7-108">Is basic and not difficult to use.</span></span>
- <span data-ttu-id="23ae7-109">Consente l'accesso a un oggetto <xref:System.Memory%601> o <xref:System.Span%601> .</span><span class="sxs-lookup"><span data-stu-id="23ae7-109">Allows access to a <xref:System.Memory%601> or <xref:System.Span%601>.</span></span> <span data-ttu-id="23ae7-110">`Memory<T>`In o `Span<T>` è possibile scrivere in ed è possibile determinare il numero di `T` elementi scritti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-110">The `Memory<T>` or `Span<T>` can be written to and you can determine how many `T` items were written.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

<span data-ttu-id="23ae7-111">Il metodo precedente:</span><span class="sxs-lookup"><span data-stu-id="23ae7-111">The preceding method:</span></span>

- <span data-ttu-id="23ae7-112">Richiede un buffer di almeno 5 byte dal `IBufferWriter<byte>` utilizzando `GetSpan(5)` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-112">Requests a buffer of at least 5 bytes from the `IBufferWriter<byte>` using `GetSpan(5)`.</span></span>
- <span data-ttu-id="23ae7-113">Scrive i byte per la stringa ASCII "Hello" nell'oggetto restituito `Span<byte>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-113">Writes bytes for the ASCII string "Hello" to the returned `Span<byte>`.</span></span>
- <span data-ttu-id="23ae7-114">Chiama <xref:System.Buffers.IBufferWriter%601> per indicare il numero di byte scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="23ae7-114">Calls  <xref:System.Buffers.IBufferWriter%601> to indicate how many bytes were written to the buffer.</span></span>

<span data-ttu-id="23ae7-115">Questo metodo di scrittura usa il `Memory<T>` / `Span<T>` buffer fornito da `IBufferWriter<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-115">This method of writing uses the `Memory<T>`/`Span<T>` buffer provided by the `IBufferWriter<T>`.</span></span> <span data-ttu-id="23ae7-116">In alternativa, <xref:System.Buffers.BuffersExtensions.Write%2A> è possibile usare il metodo di estensione per copiare un buffer esistente nell'oggetto `IBufferWriter<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-116">Alternatively, the <xref:System.Buffers.BuffersExtensions.Write%2A> extension method can be used to copy an existing buffer to the `IBufferWriter<T>`.</span></span> <span data-ttu-id="23ae7-117">`Write`esegue una chiamata nel modo `GetSpan` / `Advance` appropriato, quindi non è necessario chiamare `Advance` dopo la scrittura:</span><span class="sxs-lookup"><span data-stu-id="23ae7-117">`Write` does the work of calling `GetSpan`/`Advance` as appropriate, so there's no need to call `Advance` after writing:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<span data-ttu-id="23ae7-118"><xref:System.Buffers.ArrayBufferWriter%601>è un'implementazione di `IBufferWriter<T>` il cui archivio di backup è una singola matrice contigua.</span><span class="sxs-lookup"><span data-stu-id="23ae7-118"><xref:System.Buffers.ArrayBufferWriter%601> is an implementation of `IBufferWriter<T>` whose backing store is a single contiguous array.</span></span>

### <a name="ibufferwriter-common-problems"></a><span data-ttu-id="23ae7-119">Problemi comuni di IBufferWriter</span><span class="sxs-lookup"><span data-stu-id="23ae7-119">IBufferWriter common problems</span></span>

- <span data-ttu-id="23ae7-120">`GetSpan`e `GetMemory` restituiscono un buffer con almeno la quantità di memoria richiesta.</span><span class="sxs-lookup"><span data-stu-id="23ae7-120">`GetSpan` and `GetMemory` return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="23ae7-121">Non presupporre che le dimensioni del buffer siano esatte.</span><span class="sxs-lookup"><span data-stu-id="23ae7-121">Don't assume exact buffer sizes.</span></span>
- <span data-ttu-id="23ae7-122">Non vi è alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="23ae7-122">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
- <span data-ttu-id="23ae7-123">È necessario richiedere un nuovo buffer dopo la chiamata `Advance` a per continuare a scrivere più dati.</span><span class="sxs-lookup"><span data-stu-id="23ae7-123">A new buffer must be requested after calling `Advance` to continue writing more data.</span></span> <span data-ttu-id="23ae7-124">Non è possibile scrivere in un buffer precedentemente acquisito dopo che `Advance` è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="23ae7-124">A previously acquired buffer cannot be written to after `Advance` has been called.</span></span>

## <a name="readonlysequencet"></a><span data-ttu-id="23ae7-125">ReadOnlySequence \< T\></span><span class="sxs-lookup"><span data-stu-id="23ae7-125">ReadOnlySequence\<T\></span></span>

![ReadOnlySequence che mostra la memoria nella pipe e sotto tale posizione della sequenza della memoria di sola lettura](media/buffers/ro-sequence.png)

<span data-ttu-id="23ae7-127"><xref:System.Buffers.ReadOnlySequence%601>è uno struct che può rappresentare una sequenza contigua o non contigua di `T` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-127"><xref:System.Buffers.ReadOnlySequence%601> is a struct that can represent a contiguous or noncontiguous sequence of `T`.</span></span> <span data-ttu-id="23ae7-128">Può essere creato da:</span><span class="sxs-lookup"><span data-stu-id="23ae7-128">It can be constructed from:</span></span>

1. <span data-ttu-id="23ae7-129">Come `T[]`</span><span class="sxs-lookup"><span data-stu-id="23ae7-129">A `T[]`</span></span>
1. <span data-ttu-id="23ae7-130">Come `ReadOnlyMemory<T>`</span><span class="sxs-lookup"><span data-stu-id="23ae7-130">A `ReadOnlyMemory<T>`</span></span>
1. <span data-ttu-id="23ae7-131">Coppia di nodo elenco collegato <xref:System.Buffers.ReadOnlySequenceSegment%601> e indice per rappresentare la posizione iniziale e finale della sequenza.</span><span class="sxs-lookup"><span data-stu-id="23ae7-131">A pair of linked list node <xref:System.Buffers.ReadOnlySequenceSegment%601> and index to represent the start and end position of the sequence.</span></span>

<span data-ttu-id="23ae7-132">La terza rappresentazione è la più interessante perché presenta implicazioni sulle prestazioni per varie operazioni in `ReadOnlySequence<T>` :</span><span class="sxs-lookup"><span data-stu-id="23ae7-132">The third representation is the most interesting one as it has performance implications on various operations on the `ReadOnlySequence<T>`:</span></span>

|<span data-ttu-id="23ae7-133">Rappresentazione</span><span class="sxs-lookup"><span data-stu-id="23ae7-133">Representation</span></span>|<span data-ttu-id="23ae7-134">Operazione</span><span class="sxs-lookup"><span data-stu-id="23ae7-134">Operation</span></span>|<span data-ttu-id="23ae7-135">Complessità</span><span class="sxs-lookup"><span data-stu-id="23ae7-135">Complexity</span></span>|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

<span data-ttu-id="23ae7-136">A causa di questa rappresentazione mista, `ReadOnlySequence<T>` espone indici come `SequencePosition` anziché come Integer.</span><span class="sxs-lookup"><span data-stu-id="23ae7-136">Because of this mixed representation, the `ReadOnlySequence<T>` exposes indexes as `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="23ae7-137">R `SequencePosition` :</span><span class="sxs-lookup"><span data-stu-id="23ae7-137">A `SequencePosition`:</span></span>

- <span data-ttu-id="23ae7-138">È un valore opaco che rappresenta un indice nell'oggetto da `ReadOnlySequence<T>` cui ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="23ae7-138">Is an opaque value that represents an index into the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="23ae7-139">È costituito da due parti, un numero intero e un oggetto.</span><span class="sxs-lookup"><span data-stu-id="23ae7-139">Consists of two parts, an integer and an object.</span></span> <span data-ttu-id="23ae7-140">Gli elementi rappresentati da questi due valori sono legati all'implementazione di `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-140">What these two values represent are tied to the implementation of `ReadOnlySequence<T>`.</span></span>

### <a name="access-data"></a><span data-ttu-id="23ae7-141">Accedere ai dati</span><span class="sxs-lookup"><span data-stu-id="23ae7-141">Access data</span></span>

<span data-ttu-id="23ae7-142">`ReadOnlySequence<T>`Espone i dati come enumerabile di `ReadOnlyMemory<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-142">The `ReadOnlySequence<T>` exposes data as an enumerable of `ReadOnlyMemory<T>`.</span></span> <span data-ttu-id="23ae7-143">L'enumerazione di ogni segmento può essere eseguita usando un'istruzione foreach di base:</span><span class="sxs-lookup"><span data-stu-id="23ae7-143">Enumerating each of the segments can be done using a basic foreach:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

<span data-ttu-id="23ae7-144">Il metodo precedente Cerca un byte specifico in ogni segmento.</span><span class="sxs-lookup"><span data-stu-id="23ae7-144">The preceding method searches each segment for a specific byte.</span></span> <span data-ttu-id="23ae7-145">Se è necessario tenere traccia di ogni segmento `SequencePosition` , <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> è più appropriato.</span><span class="sxs-lookup"><span data-stu-id="23ae7-145">If you need to keep track of each segment's `SequencePosition`, <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> is more appropriate.</span></span> <span data-ttu-id="23ae7-146">Nell'esempio seguente viene modificato il codice precedente per restituire un `SequencePosition` anziché un numero intero.</span><span class="sxs-lookup"><span data-stu-id="23ae7-146">The next sample changes the preceding code to return a `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="23ae7-147">La restituzione di un oggetto `SequencePosition` ha il vantaggio di consentire al chiamante di evitare una seconda analisi per ottenere i dati in corrispondenza di un indice specifico.</span><span class="sxs-lookup"><span data-stu-id="23ae7-147">Returning a `SequencePosition` has the benefit of allowing the caller to avoid a second scan to get the data at a specific index.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

<span data-ttu-id="23ae7-148">La combinazione di `SequencePosition` e `TryGet` funge da enumeratore.</span><span class="sxs-lookup"><span data-stu-id="23ae7-148">The combination of `SequencePosition` and `TryGet` acts like an enumerator.</span></span> <span data-ttu-id="23ae7-149">Il campo position viene modificato all'inizio di ogni iterazione in modo che sia l'inizio di ogni segmento all'interno di `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-149">The position field is modified at the start of each iteration to be start of each segment within the `ReadOnlySequence<T>`.</span></span>

<span data-ttu-id="23ae7-150">Il metodo precedente esiste come metodo di estensione su `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-150">The preceding method exists as an extension method on `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="23ae7-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A>può essere usato per semplificare il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="23ae7-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A> can be used to simplify the preceding code:</span></span>

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a><span data-ttu-id="23ae7-152">Elaborare un ReadOnlySequence \< T\></span><span class="sxs-lookup"><span data-stu-id="23ae7-152">Process a ReadOnlySequence\<T\></span></span>

<span data-ttu-id="23ae7-153">L'elaborazione di un oggetto `ReadOnlySequence<T>` può essere complessa perché i dati possono essere suddivisi in più segmenti all'interno della sequenza.</span><span class="sxs-lookup"><span data-stu-id="23ae7-153">Processing a `ReadOnlySequence<T>` can be challenging since data may be split across multiple segments within the sequence.</span></span> <span data-ttu-id="23ae7-154">Per ottenere prestazioni ottimali, suddividere il codice in due percorsi:</span><span class="sxs-lookup"><span data-stu-id="23ae7-154">For the best performance, split code into two paths:</span></span>

- <span data-ttu-id="23ae7-155">Percorso veloce che riguarda il singolo case del segmento.</span><span class="sxs-lookup"><span data-stu-id="23ae7-155">A fast path that deals with the single segment case.</span></span>
- <span data-ttu-id="23ae7-156">Percorso lento che riguarda la suddivisione dei dati tra i segmenti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-156">A slow path that deals with the data split across segments.</span></span>

<span data-ttu-id="23ae7-157">Esistono alcuni approcci che possono essere usati per elaborare i dati in sequenze multisegmentate:</span><span class="sxs-lookup"><span data-stu-id="23ae7-157">There are a few approaches that can be used to process data in multi-segmented sequences:</span></span>

- <span data-ttu-id="23ae7-158">Usare [`SequenceReader<T>`](#sequencereadert) .</span><span class="sxs-lookup"><span data-stu-id="23ae7-158">Use the [`SequenceReader<T>`](#sequencereadert).</span></span>
- <span data-ttu-id="23ae7-159">Analizza il segmento di dati in base al segmento, tenendo traccia dell' `SequencePosition` indice e all'interno del segmento analizzato.</span><span class="sxs-lookup"><span data-stu-id="23ae7-159">Parse data segment by segment, keeping track of the `SequencePosition` and index within the segment parsed.</span></span> <span data-ttu-id="23ae7-160">In questo modo si evitano allocazioni non necessarie, ma possono risultare inefficienti, specialmente per i buffer di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="23ae7-160">This avoids unnecessary allocations but may be inefficient, especially for small buffers.</span></span>
- <span data-ttu-id="23ae7-161">Copiare l'oggetto `ReadOnlySequence<T>` in una matrice contigua e considerarlo come un singolo buffer:</span><span class="sxs-lookup"><span data-stu-id="23ae7-161">Copy the `ReadOnlySequence<T>` to a contiguous array and treat it like a single buffer:</span></span>
  - <span data-ttu-id="23ae7-162">Se la dimensione di `ReadOnlySequence<T>` è ridotta, può essere ragionevole copiare i dati in un buffer allocato nello stack usando l'operatore [stackalloc](../../csharp/language-reference/operators/stackalloc.md) .</span><span class="sxs-lookup"><span data-stu-id="23ae7-162">If the size of the `ReadOnlySequence<T>` is small, it may be reasonable to copy the data into a stack-allocated buffer using the [stackalloc](../../csharp/language-reference/operators/stackalloc.md) operator.</span></span>
  - <span data-ttu-id="23ae7-163">Copiare `ReadOnlySequence<T>` in una matrice in pool usando <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="23ae7-163">Copy the `ReadOnlySequence<T>` into a pooled array using <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="23ae7-164">Usare [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span><span class="sxs-lookup"><span data-stu-id="23ae7-164">Use [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span></span> <span data-ttu-id="23ae7-165">Questa operazione non è consigliata nei percorsi sensibili quando alloca un nuovo nell' `T[]` heap.</span><span class="sxs-lookup"><span data-stu-id="23ae7-165">This isn't recommended in hot paths as it allocates a new `T[]` on the heap.</span></span>

<span data-ttu-id="23ae7-166">Gli esempi seguenti illustrano alcuni casi comuni per l'elaborazione `ReadOnlySequence<byte>` :</span><span class="sxs-lookup"><span data-stu-id="23ae7-166">The following examples demonstrate some common cases for processing `ReadOnlySequence<byte>`:</span></span>

##### <a name="process-binary-data"></a><span data-ttu-id="23ae7-167">Elaborare dati binari</span><span class="sxs-lookup"><span data-stu-id="23ae7-167">Process binary data</span></span>

<span data-ttu-id="23ae7-168">Nell'esempio seguente viene analizzata una lunghezza Integer a 4 byte big-endian dall'inizio di `ReadOnlySequence<byte>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-168">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a><span data-ttu-id="23ae7-169">Elabora dati di testo</span><span class="sxs-lookup"><span data-stu-id="23ae7-169">Process text data</span></span>

<span data-ttu-id="23ae7-170">L'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="23ae7-170">The following example:</span></span>

- <span data-ttu-id="23ae7-171">Trova il primo carattere di nuova riga ( `\r\n` ) nell'oggetto `ReadOnlySequence<byte>` e lo restituisce tramite il parametro out "line".</span><span class="sxs-lookup"><span data-stu-id="23ae7-171">Finds the first newline (`\r\n`) in the `ReadOnlySequence<byte>` and returns it via the out 'line' parameter.</span></span>
- <span data-ttu-id="23ae7-172">Taglia la riga, esclusa `\r\n` dal buffer di input.</span><span class="sxs-lookup"><span data-stu-id="23ae7-172">Trims that line, excluding the `\r\n` from the input buffer.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a><span data-ttu-id="23ae7-173">Segmenti vuoti</span><span class="sxs-lookup"><span data-stu-id="23ae7-173">Empty segments</span></span>

<span data-ttu-id="23ae7-174">È valido per archiviare segmenti vuoti all'interno di un oggetto `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-174">It's valid to store empty segments inside of a `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="23ae7-175">È possibile che si verifichino segmenti vuoti durante l'enumerazione dei segmenti in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="23ae7-175">Empty segments may occur while enumerating segments explicitly:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

<span data-ttu-id="23ae7-176">Il codice precedente crea un oggetto `ReadOnlySequence<byte>` con segmenti vuoti e Mostra come tali segmenti vuoti influiscono sulle varie API:</span><span class="sxs-lookup"><span data-stu-id="23ae7-176">The preceding code creates a `ReadOnlySequence<byte>` with empty segments and shows how those empty segments affect the various APIs:</span></span>

- <span data-ttu-id="23ae7-177">`ReadOnlySequence<T>.Slice`con un oggetto `SequencePosition` che punta a un segmento vuoto, conserva tale segmento.</span><span class="sxs-lookup"><span data-stu-id="23ae7-177">`ReadOnlySequence<T>.Slice` with a `SequencePosition` pointing to an empty segment preserves that segment.</span></span>
- <span data-ttu-id="23ae7-178">`ReadOnlySequence<T>.Slice`con un valore int ignora i segmenti vuoti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-178">`ReadOnlySequence<T>.Slice` with an int skips over the empty segments.</span></span>
- <span data-ttu-id="23ae7-179">L'enumerazione di `ReadOnlySequence<T>` enumera i segmenti vuoti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-179">Enumerating the `ReadOnlySequence<T>` enumerates the empty segments.</span></span>

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a><span data-ttu-id="23ae7-180">Potenziali problemi con ReadOnlySequence \< T> e SequencePosition</span><span class="sxs-lookup"><span data-stu-id="23ae7-180">Potential problems with ReadOnlySequence\<T> and SequencePosition</span></span>

<span data-ttu-id="23ae7-181">Esistono diversi risultati insoliti quando si ha a che fare con un rispetto a un `ReadOnlySequence<T>` / `SequencePosition` normale `ReadOnlySpan<T>` / `ReadOnlyMemory<T>` / `T[]` / `int` :</span><span class="sxs-lookup"><span data-stu-id="23ae7-181">There are several unusual outcomes when dealing with a `ReadOnlySequence<T>`/`SequencePosition` vs. a normal `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`:</span></span>

- <span data-ttu-id="23ae7-182">`SequencePosition`è un indicatore di posizione per una specifica `ReadOnlySequence<T>` , non una posizione assoluta.</span><span class="sxs-lookup"><span data-stu-id="23ae7-182">`SequencePosition` is a position marker for a specific `ReadOnlySequence<T>`, not an absolute position.</span></span> <span data-ttu-id="23ae7-183">Poiché è relativo a un oggetto specifico `ReadOnlySequence<T>` , non ha significato se usato all'esterno dell'oggetto da `ReadOnlySequence<T>` cui ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="23ae7-183">Because it's relative to a specific `ReadOnlySequence<T>`, it doesn't have meaning if used outside of the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="23ae7-184">Non è possibile eseguire operazioni aritmetiche su `SequencePosition` senza `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-184">Arithmetic can't be performed on `SequencePosition` without the `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="23ae7-185">Ciò significa che vengono scritti gli elementi di base, ad esempio `position++` `ReadOnlySequence<T>.GetPosition(position, 1)` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-185">That means doing basic things like `position++` is written `ReadOnlySequence<T>.GetPosition(position, 1)`.</span></span>
- <span data-ttu-id="23ae7-186">`GetPosition(long)`non **supporta** indici negativi.</span><span class="sxs-lookup"><span data-stu-id="23ae7-186">`GetPosition(long)` does **not** support negative indexes.</span></span> <span data-ttu-id="23ae7-187">Ciò significa che non è possibile ottenere il secondo carattere finale senza scorrere tutti i segmenti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-187">That means it's impossible to get the second to last character without walking all segments.</span></span>
- <span data-ttu-id="23ae7-188">`SequencePosition`Non è possibile confrontare due, rendendo difficile:</span><span class="sxs-lookup"><span data-stu-id="23ae7-188">Two `SequencePosition` can't be compared, making it difficult to:</span></span>
  - <span data-ttu-id="23ae7-189">Verificare se una posizione è maggiore o minore di un'altra posizione.</span><span class="sxs-lookup"><span data-stu-id="23ae7-189">Know if one position is greater than or less than another position.</span></span>
  - <span data-ttu-id="23ae7-190">Scrivere alcuni algoritmi di analisi.</span><span class="sxs-lookup"><span data-stu-id="23ae7-190">Write some parsing algorithms.</span></span>
- <span data-ttu-id="23ae7-191">`ReadOnlySequence<T>`è maggiore di un riferimento a un oggetto e deve essere passato da [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) o [ref](../../csharp/language-reference/keywords/ref.md) , ove possibile.</span><span class="sxs-lookup"><span data-stu-id="23ae7-191">`ReadOnlySequence<T>` is bigger than an object reference and should be passed by [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../csharp/language-reference/keywords/ref.md) where possible.</span></span> <span data-ttu-id="23ae7-192">`ReadOnlySequence<T>`Il passaggio `in` o `ref` la riduzione delle copie dello [struct](../../csharp/language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="23ae7-192">Passing `ReadOnlySequence<T>` by `in` or `ref` reduces copies of the [struct](../../csharp/language-reference/builtin-types/struct.md).</span></span>
- <span data-ttu-id="23ae7-193">Segmenti vuoti:</span><span class="sxs-lookup"><span data-stu-id="23ae7-193">Empty segments:</span></span>
  - <span data-ttu-id="23ae7-194">Sono validi in un oggetto `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-194">Are valid within a `ReadOnlySequence<T>`.</span></span>
  - <span data-ttu-id="23ae7-195">Può essere visualizzato quando si esegue l'iterazione usando il `ReadOnlySequence<T>.TryGet` metodo.</span><span class="sxs-lookup"><span data-stu-id="23ae7-195">Can appear when iterating using the `ReadOnlySequence<T>.TryGet` method.</span></span>
  - <span data-ttu-id="23ae7-196">Può comparire sezionare la sequenza usando il `ReadOnlySequence<T>.Slice()` metodo con `SequencePosition` gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-196">Can appear slicing the sequence using the `ReadOnlySequence<T>.Slice()` method with `SequencePosition` objects.</span></span>

## <a name="sequencereadert"></a><span data-ttu-id="23ae7-197">SequenceReader \< T\></span><span class="sxs-lookup"><span data-stu-id="23ae7-197">SequenceReader\<T\></span></span>

<span data-ttu-id="23ae7-198"><xref:System.Buffers.SequenceReader%601>:</span><span class="sxs-lookup"><span data-stu-id="23ae7-198"><xref:System.Buffers.SequenceReader%601>:</span></span>

- <span data-ttu-id="23ae7-199">È un nuovo tipo introdotto in .NET Core 3,0 per semplificare l'elaborazione di un oggetto `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-199">Is a new type that was introduced in .NET Core 3.0 to simplify the processing of a `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="23ae7-200">Unifica le differenze tra un singolo segmento `ReadOnlySequence<T>` e più segmenti `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-200">Unifies the differences between a single segment `ReadOnlySequence<T>` and multi-segment `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="23ae7-201">Fornisce helper per la lettura di dati binari e di testo ( `byte` e `char` ) che possono o meno essere suddivisi tra segmenti.</span><span class="sxs-lookup"><span data-stu-id="23ae7-201">Provides helpers for reading binary and text data (`byte` and `char`) that may or may not be split across segments.</span></span>

<span data-ttu-id="23ae7-202">Sono disponibili metodi predefiniti per gestire l'elaborazione di dati binari e delimitati.</span><span class="sxs-lookup"><span data-stu-id="23ae7-202">There are built-in methods for dealing with processing both binary and delimited data.</span></span> <span data-ttu-id="23ae7-203">La sezione seguente illustra l'aspetto degli stessi metodi con `SequenceReader<T>` :</span><span class="sxs-lookup"><span data-stu-id="23ae7-203">The following section demonstrates what those same methods look like with the `SequenceReader<T>`:</span></span>

### <a name="access-data"></a><span data-ttu-id="23ae7-204">Accedere ai dati</span><span class="sxs-lookup"><span data-stu-id="23ae7-204">Access data</span></span>

<span data-ttu-id="23ae7-205">`SequenceReader<T>`dispone di metodi per l'enumerazione diretta dei dati all'interno di `ReadOnlySequence<T>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-205">`SequenceReader<T>` has methods for enumerating data inside of the `ReadOnlySequence<T>` directly.</span></span> <span data-ttu-id="23ae7-206">Il codice seguente è un esempio di elaborazione di un `ReadOnlySequence<byte>` oggetto `byte` alla volta:</span><span class="sxs-lookup"><span data-stu-id="23ae7-206">The following code is an example of processing a `ReadOnlySequence<byte>` a `byte` at a time:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

<span data-ttu-id="23ae7-207">`CurrentSpan`Espone il segmento corrente `Span` , che è simile a quanto è stato fatto nel metodo manualmente.</span><span class="sxs-lookup"><span data-stu-id="23ae7-207">The `CurrentSpan` exposes the current segment's `Span`, which is similar to what was done in the method manually.</span></span>

### <a name="use-position"></a><span data-ttu-id="23ae7-208">Usa posizione</span><span class="sxs-lookup"><span data-stu-id="23ae7-208">Use position</span></span>

<span data-ttu-id="23ae7-209">Il codice seguente è un'implementazione di esempio dell' `FindIndexOf` utilizzo di `SequenceReader<T>` :</span><span class="sxs-lookup"><span data-stu-id="23ae7-209">The following code is an example implementation of `FindIndexOf` using the `SequenceReader<T>`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a><span data-ttu-id="23ae7-210">Elaborare dati binari</span><span class="sxs-lookup"><span data-stu-id="23ae7-210">Process binary data</span></span>

<span data-ttu-id="23ae7-211">Nell'esempio seguente viene analizzata una lunghezza Integer a 4 byte big-endian dall'inizio di `ReadOnlySequence<byte>` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-211">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a><span data-ttu-id="23ae7-212">Elabora dati di testo</span><span class="sxs-lookup"><span data-stu-id="23ae7-212">Process text data</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a><span data-ttu-id="23ae7-213">\< \> Problemi comuni di SequenceReader</span><span class="sxs-lookup"><span data-stu-id="23ae7-213">SequenceReader\<T\> common problems</span></span>

- <span data-ttu-id="23ae7-214">Poiché `SequenceReader<T>` è uno struct modificabile, deve essere sempre passato per [riferimento](../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="23ae7-214">Because `SequenceReader<T>` is a mutable struct, it should always be passed by [reference](../../csharp/language-reference/keywords/ref.md).</span></span>
- <span data-ttu-id="23ae7-215">`SequenceReader<T>`è uno [struct Ref](../../csharp/language-reference/builtin-types/struct.md#ref-struct) , che può essere usato solo nei metodi sincroni e non può essere archiviato in campi.</span><span class="sxs-lookup"><span data-stu-id="23ae7-215">`SequenceReader<T>` is a [ref struct](../../csharp/language-reference/builtin-types/struct.md#ref-struct) so it can only be used in synchronous methods and can't be stored in fields.</span></span> <span data-ttu-id="23ae7-216">Per altre informazioni, vedere [scrivere codice C# sicuro ed efficiente](../../csharp/write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="23ae7-216">For more information, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>
- <span data-ttu-id="23ae7-217">`SequenceReader<T>`è ottimizzato per l'utilizzo come lettore di sola trasmissione.</span><span class="sxs-lookup"><span data-stu-id="23ae7-217">`SequenceReader<T>` is optimized for use as a forward-only reader.</span></span> <span data-ttu-id="23ae7-218">`Rewind`è destinato a backup di piccole dimensioni che non possono essere risolti utilizzando altre `Read` `Peek` API, e `IsNext` .</span><span class="sxs-lookup"><span data-stu-id="23ae7-218">`Rewind` is intended for small backups that can't be addressed utilizing other `Read`, `Peek`, and `IsNext` APIs.</span></span>
