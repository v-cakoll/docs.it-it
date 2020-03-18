---
title: System.Buffers - .NET
ms.date: 12/05/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: f939164cd56b2fb2feeeb171236b0e1171327e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160118"
---
# <a name="work-with-buffers-in-net"></a><span data-ttu-id="da3af-102">Utilizzare i buffer in .NET</span><span class="sxs-lookup"><span data-stu-id="da3af-102">Work with Buffers in .NET</span></span>

<span data-ttu-id="da3af-103">In questo articolo viene fornita una panoramica dei tipi che consentono di leggere i dati eseguiti in più buffer.</span><span class="sxs-lookup"><span data-stu-id="da3af-103">This article provides an overview of types that help read data that runs across multiple buffers.</span></span> <span data-ttu-id="da3af-104">Vengono utilizzati principalmente per <xref:System.IO.Pipelines.PipeReader> supportare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="da3af-104">They're primarily used to support <xref:System.IO.Pipelines.PipeReader> objects.</span></span>

## <a name="ibufferwritert"></a><span data-ttu-id="da3af-105">IBufferWriter\<T\></span><span class="sxs-lookup"><span data-stu-id="da3af-105">IBufferWriter\<T\></span></span>

<span data-ttu-id="da3af-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName>è un contratto per la scrittura con buffer sincrono.</span><span class="sxs-lookup"><span data-stu-id="da3af-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> is a contract for synchronous buffered writing.</span></span> <span data-ttu-id="da3af-107">Al livello più basso, l'interfaccia:</span><span class="sxs-lookup"><span data-stu-id="da3af-107">At the lowest level, the interface:</span></span>

- <span data-ttu-id="da3af-108">È essenziale e non è difficile da usare.</span><span class="sxs-lookup"><span data-stu-id="da3af-108">Is basic and not difficult to use.</span></span>
- <span data-ttu-id="da3af-109">Consente l'accesso a un <xref:System.Memory%601> o <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="da3af-109">Allows access to a <xref:System.Memory%601> or <xref:System.Span%601>.</span></span> <span data-ttu-id="da3af-110">L'oggetto `Memory<T>` o `Span<T>` può essere scritto `T` ed è possibile determinare il numero di elementi scritti.</span><span class="sxs-lookup"><span data-stu-id="da3af-110">The `Memory<T>` or `Span<T>` can be written to and you can determine how many `T` items were written.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

<span data-ttu-id="da3af-111">Il metodo precedente:</span><span class="sxs-lookup"><span data-stu-id="da3af-111">The preceding method:</span></span>

- <span data-ttu-id="da3af-112">Richiede un buffer di almeno `IBufferWriter<byte>` 5 `GetSpan(5)`byte dall'oggetto using .</span><span class="sxs-lookup"><span data-stu-id="da3af-112">Requests a buffer of at least 5 bytes from the `IBufferWriter<byte>` using `GetSpan(5)`.</span></span>
- <span data-ttu-id="da3af-113">Scrive i byte per la stringa ASCII `Span<byte>`"Hello" nella stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="da3af-113">Writes bytes for the ASCII string "Hello" to the returned `Span<byte>`.</span></span>
- <span data-ttu-id="da3af-114">Chiamate <xref:System.Buffers.IBufferWriter%601> per indicare quanti byte sono stati scritti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="da3af-114">Calls  <xref:System.Buffers.IBufferWriter%601> to indicate how many bytes were written to the buffer.</span></span>

<span data-ttu-id="da3af-115">Questo metodo di `Memory<T>` / `Span<T>` scrittura utilizza `IBufferWriter<T>`il buffer fornito dall'oggetto .</span><span class="sxs-lookup"><span data-stu-id="da3af-115">This method of writing uses the `Memory<T>`/`Span<T>` buffer provided by the `IBufferWriter<T>`.</span></span> <span data-ttu-id="da3af-116">In alternativa, <xref:System.Buffers.BuffersExtensions.Write%2A> il metodo di estensione può essere `IBufferWriter<T>`utilizzato per copiare un buffer esistente nell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="da3af-116">Alternatively, the <xref:System.Buffers.BuffersExtensions.Write%2A> extension method can be used to copy an existing buffer to the `IBufferWriter<T>`.</span></span> <span data-ttu-id="da3af-117">`Write`fa il lavoro `GetSpan` / `Advance` di chiamata a seconda dei `Advance` casi, quindi non c'è bisogno di chiamare dopo la scrittura:</span><span class="sxs-lookup"><span data-stu-id="da3af-117">`Write` does the work of calling `GetSpan`/`Advance` as appropriate, so there's no need to call `Advance` after writing:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<span data-ttu-id="da3af-118"><xref:System.Buffers.ArrayBufferWriter%601>è un'implementazione del `IBufferWriter<T>` cui archivio di backup è una singola matrice contigua.</span><span class="sxs-lookup"><span data-stu-id="da3af-118"><xref:System.Buffers.ArrayBufferWriter%601> is an implementation of `IBufferWriter<T>` whose backing store is a single contiguous array.</span></span>

### <a name="ibufferwriter-common-problems"></a><span data-ttu-id="da3af-119">Problemi comuni di IBufferWriter</span><span class="sxs-lookup"><span data-stu-id="da3af-119">IBufferWriter common problems</span></span>

- <span data-ttu-id="da3af-120">`GetSpan`e `GetMemory` restituire un buffer con almeno la quantità di memoria richiesta.</span><span class="sxs-lookup"><span data-stu-id="da3af-120">`GetSpan` and `GetMemory` return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="da3af-121">Non presupporre che le dimensioni esatte del buffer.</span><span class="sxs-lookup"><span data-stu-id="da3af-121">Don't assume exact buffer sizes.</span></span>
- <span data-ttu-id="da3af-122">Non esiste alcuna garanzia che le chiamate successive restituiscano lo stesso buffer o lo stesso buffer delle stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da3af-122">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
- <span data-ttu-id="da3af-123">È necessario richiedere un `Advance` nuovo buffer dopo la chiamata per continuare a scrivere altri dati.</span><span class="sxs-lookup"><span data-stu-id="da3af-123">A new buffer must be requested after calling `Advance` to continue writing more data.</span></span> <span data-ttu-id="da3af-124">Un buffer acquisito in precedenza non può essere scritto dopo `Advance` che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="da3af-124">A previously acquired buffer cannot be written to after `Advance` has been called.</span></span>

## <a name="readonlysequencet"></a><span data-ttu-id="da3af-125">ReadOnlySequence\<T\></span><span class="sxs-lookup"><span data-stu-id="da3af-125">ReadOnlySequence\<T\></span></span>

![ReadOnlySequence che mostra la memoria nella pipe e al di sotto della posizione della sequenza della memoria di sola lettura](media/buffers/ro-sequence.png)

<span data-ttu-id="da3af-127"><xref:System.Buffers.ReadOnlySequence%601>è una struttura che può rappresentare una sequenza contigua o non contigua di `T`.</span><span class="sxs-lookup"><span data-stu-id="da3af-127"><xref:System.Buffers.ReadOnlySequence%601> is a struct that can represent a contiguous or noncontiguous sequence of `T`.</span></span> <span data-ttu-id="da3af-128">Può essere costruito da:</span><span class="sxs-lookup"><span data-stu-id="da3af-128">It can be constructed from:</span></span>

1. <span data-ttu-id="da3af-129">Come `T[]`</span><span class="sxs-lookup"><span data-stu-id="da3af-129">A `T[]`</span></span>
1. <span data-ttu-id="da3af-130">Come `ReadOnlyMemory<T>`</span><span class="sxs-lookup"><span data-stu-id="da3af-130">A `ReadOnlyMemory<T>`</span></span>
1. <span data-ttu-id="da3af-131">Coppia di nodo <xref:System.Buffers.ReadOnlySequenceSegment%601> e indice dell'elenco collegato per rappresentare la posizione iniziale e finale della sequenza.</span><span class="sxs-lookup"><span data-stu-id="da3af-131">A pair of linked list node <xref:System.Buffers.ReadOnlySequenceSegment%601> and index to represent the start and end position of the sequence.</span></span>

<span data-ttu-id="da3af-132">La terza rappresentazione è la più interessante in quanto `ReadOnlySequence<T>`ha implicazioni sulle prestazioni su varie operazioni sul :</span><span class="sxs-lookup"><span data-stu-id="da3af-132">The third representation is the most interesting one as it has performance implications on various operations on the `ReadOnlySequence<T>`:</span></span>

|<span data-ttu-id="da3af-133">Rappresentazione</span><span class="sxs-lookup"><span data-stu-id="da3af-133">Representation</span></span>|<span data-ttu-id="da3af-134">Operazione</span><span class="sxs-lookup"><span data-stu-id="da3af-134">Operation</span></span>|<span data-ttu-id="da3af-135">Complessità</span><span class="sxs-lookup"><span data-stu-id="da3af-135">Complexity</span></span>|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

<span data-ttu-id="da3af-136">A causa di questa `ReadOnlySequence<T>` rappresentazione mista, espone gli indici come `SequencePosition` anziché come integer.</span><span class="sxs-lookup"><span data-stu-id="da3af-136">Because of this mixed representation, the `ReadOnlySequence<T>` exposes indexes as `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="da3af-137">A `SequencePosition`:</span><span class="sxs-lookup"><span data-stu-id="da3af-137">A `SequencePosition`:</span></span>

- <span data-ttu-id="da3af-138">È un valore opaco che `ReadOnlySequence<T>` rappresenta un indice nel punto in cui ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="da3af-138">Is an opaque value that represents an index into the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="da3af-139">È costituito da due parti, un numero intero e un oggetto.</span><span class="sxs-lookup"><span data-stu-id="da3af-139">Consists of two parts, an integer and an object.</span></span> <span data-ttu-id="da3af-140">Ciò che questi due valori rappresentano `ReadOnlySequence<T>`sono legati all'implementazione di .</span><span class="sxs-lookup"><span data-stu-id="da3af-140">What these two values represent are tied to the implementation of `ReadOnlySequence<T>`.</span></span>

### <a name="access-data"></a><span data-ttu-id="da3af-141">Accedere ai dati</span><span class="sxs-lookup"><span data-stu-id="da3af-141">Access data</span></span>

<span data-ttu-id="da3af-142">Espone `ReadOnlySequence<T>` i dati come `ReadOnlyMemory<T>`enumerabili di .</span><span class="sxs-lookup"><span data-stu-id="da3af-142">The `ReadOnlySequence<T>` exposes data as an enumerable of `ReadOnlyMemory<T>`.</span></span> <span data-ttu-id="da3af-143">L'enumerazione di ciascuno dei segmenti può essere eseguita utilizzando un foreach di base:Enumerating each of the segments can be done using a basic foreach:</span><span class="sxs-lookup"><span data-stu-id="da3af-143">Enumerating each of the segments can be done using a basic foreach:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

<span data-ttu-id="da3af-144">Il metodo precedente cerca in ogni segmento un byte specifico.</span><span class="sxs-lookup"><span data-stu-id="da3af-144">The preceding method searches each segment for a specific byte.</span></span> <span data-ttu-id="da3af-145">Se è necessario tenere traccia di `SequencePosition` <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> ogni segmento di , è più appropriato.</span><span class="sxs-lookup"><span data-stu-id="da3af-145">If you need to keep track of each segment's `SequencePosition`, <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> is more appropriate.</span></span> <span data-ttu-id="da3af-146">L'esempio successivo modifica il codice `SequencePosition` precedente in modo che restituisca un numero intero anziché un numero intero.</span><span class="sxs-lookup"><span data-stu-id="da3af-146">The next sample changes the preceding code to return a `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="da3af-147">La restituzione di un `SequencePosition` ha il vantaggio di consentire al chiamante di evitare una seconda analisi per ottenere i dati in corrispondenza di un indice specifico.</span><span class="sxs-lookup"><span data-stu-id="da3af-147">Returning a `SequencePosition` has the benefit of allowing the caller to avoid a second scan to get the data at a specific index.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

<span data-ttu-id="da3af-148">La combinazione `SequencePosition` `TryGet` e agisce come un enumeratore.</span><span class="sxs-lookup"><span data-stu-id="da3af-148">The combination of `SequencePosition` and `TryGet` acts like an enumerator.</span></span> <span data-ttu-id="da3af-149">Il campo posizione viene modificato all'inizio di ogni iterazione per essere iniziale di ogni segmento all'interno di `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="da3af-149">The position field is modified at the start of each iteration to be start of each segment within the `ReadOnlySequence<T>`.</span></span>

<span data-ttu-id="da3af-150">Il metodo precedente esiste come `ReadOnlySequence<T>`metodo di estensione in .</span><span class="sxs-lookup"><span data-stu-id="da3af-150">The preceding method exists as an extension method on `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="da3af-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A>può essere utilizzato per semplificare il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="da3af-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A> can be used to simplify the preceding code:</span></span>

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a><span data-ttu-id="da3af-152">Elaborare un\<ReadOnlySequence TProcess a ReadOnlySequence T\></span><span class="sxs-lookup"><span data-stu-id="da3af-152">Process a ReadOnlySequence\<T\></span></span>

<span data-ttu-id="da3af-153">L'elaborazione di un `ReadOnlySequence<T>` oggetto può essere difficile poiché i dati possono essere suddivisi in più segmenti all'interno della sequenza.</span><span class="sxs-lookup"><span data-stu-id="da3af-153">Processing a `ReadOnlySequence<T>` can be challenging since data may be split across multiple segments within the sequence.</span></span> <span data-ttu-id="da3af-154">Per ottenere prestazioni ottimali, suddividere il codice in due percorsi:For the best performance, split code into two paths:</span><span class="sxs-lookup"><span data-stu-id="da3af-154">For the best performance, split code into two paths:</span></span>

- <span data-ttu-id="da3af-155">Un percorso veloce che si occupa della custodia per singolo segmento.</span><span class="sxs-lookup"><span data-stu-id="da3af-155">A fast path that deals with the single segment case.</span></span>
- <span data-ttu-id="da3af-156">Percorso lento che gestisce i dati suddivisi tra i segmenti.</span><span class="sxs-lookup"><span data-stu-id="da3af-156">A slow path that deals with the data split across segments.</span></span>

<span data-ttu-id="da3af-157">Esistono alcuni approcci che possono essere utilizzati per elaborare i dati in sequenze multisegmentate:There are a few approaches that can be used to process data in multi-segmented sequences:</span><span class="sxs-lookup"><span data-stu-id="da3af-157">There are a few approaches that can be used to process data in multi-segmented sequences:</span></span>

- <span data-ttu-id="da3af-158">Utilizzare [`SequenceReader<T>`](#sequencereadert)il file .</span><span class="sxs-lookup"><span data-stu-id="da3af-158">Use the [`SequenceReader<T>`](#sequencereadert).</span></span>
- <span data-ttu-id="da3af-159">Analizzare il segmento di `SequencePosition` dati per segmento, tenendo traccia di e l'indice all'interno del segmento analizzato.</span><span class="sxs-lookup"><span data-stu-id="da3af-159">Parse data segment by segment, keeping track of the `SequencePosition` and index within the segment parsed.</span></span> <span data-ttu-id="da3af-160">In questo modo si evitano allocazioni non necessarie, ma possono essere inefficienti, in particolare per i buffer di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da3af-160">This avoids unnecessary allocations but may be inefficient, especially for small buffers.</span></span>
- <span data-ttu-id="da3af-161">Copiare `ReadOnlySequence<T>` l'oggetto in una matrice contigua e trattarlo come un singolo buffer:Copy the to a contiguo array and treat it as a single buffer:</span><span class="sxs-lookup"><span data-stu-id="da3af-161">Copy the `ReadOnlySequence<T>` to a contiguous array and treat it like a single buffer:</span></span>
  - <span data-ttu-id="da3af-162">Se la dimensione `ReadOnlySequence<T>` di è piccola, può essere ragionevole copiare i dati in un buffer allocato nello stack utilizzando l'operatore [stackalloc.](../../csharp/language-reference/operators/stackalloc.md)</span><span class="sxs-lookup"><span data-stu-id="da3af-162">If the size of the `ReadOnlySequence<T>` is small, it may be reasonable to copy the data into a stack-allocated buffer using the [stackalloc](../../csharp/language-reference/operators/stackalloc.md) operator.</span></span>
  - <span data-ttu-id="da3af-163">Copiare `ReadOnlySequence<T>` l'oggetto in <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>una matrice in pool utilizzando .</span><span class="sxs-lookup"><span data-stu-id="da3af-163">Copy the `ReadOnlySequence<T>` into a pooled array using <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="da3af-164">Utilizzare [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span><span class="sxs-lookup"><span data-stu-id="da3af-164">Use [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span></span> <span data-ttu-id="da3af-165">Questa operazione non è consigliata nei percorsi attivi in quanto alloca un nuovo `T[]` nell'heap.</span><span class="sxs-lookup"><span data-stu-id="da3af-165">This isn't recommended in hot paths as it allocates a new `T[]` on the heap.</span></span>

<span data-ttu-id="da3af-166">Negli esempi seguenti vengono illustrati `ReadOnlySequence<byte>`alcuni casi comuni per l'elaborazione:</span><span class="sxs-lookup"><span data-stu-id="da3af-166">The following examples demonstrate some common cases for processing `ReadOnlySequence<byte>`:</span></span>

##### <a name="process-binary-data"></a><span data-ttu-id="da3af-167">Elaborare i dati binari</span><span class="sxs-lookup"><span data-stu-id="da3af-167">Process binary data</span></span>

<span data-ttu-id="da3af-168">Nell'esempio riportato di seguito viene analizzata una lunghezza intera `ReadOnlySequence<byte>`bigendian a 4 byte dall'inizio dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="da3af-168">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a><span data-ttu-id="da3af-169">Elaborare i dati di testo</span><span class="sxs-lookup"><span data-stu-id="da3af-169">Process text data</span></span>

<span data-ttu-id="da3af-170">L'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="da3af-170">The following example:</span></span>

- <span data-ttu-id="da3af-171">Trova la prima`\r\n`nuova riga `ReadOnlySequence<byte>` ( ) in e la restituisce tramite il parametro 'line' out.</span><span class="sxs-lookup"><span data-stu-id="da3af-171">Finds the first newline (`\r\n`) in the `ReadOnlySequence<byte>` and returns it via the out 'line' parameter.</span></span>
- <span data-ttu-id="da3af-172">Taglia la riga, escludendo l'oggetto `\r\n` dal buffer di input.</span><span class="sxs-lookup"><span data-stu-id="da3af-172">Trims that line, excluding the `\r\n` from the input buffer.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a><span data-ttu-id="da3af-173">Segmenti vuoti</span><span class="sxs-lookup"><span data-stu-id="da3af-173">Empty segments</span></span>

<span data-ttu-id="da3af-174">È valido archiviare segmenti vuoti all'interno di un `ReadOnlySequence<T>`oggetto .</span><span class="sxs-lookup"><span data-stu-id="da3af-174">It's valid to store empty segments inside of a `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="da3af-175">Durante l'enumerazione esplicita dei segmenti possono verificarsi segmenti vuoti:</span><span class="sxs-lookup"><span data-stu-id="da3af-175">Empty segments may occur while enumerating segments explicitly:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

<span data-ttu-id="da3af-176">Il codice precedente `ReadOnlySequence<byte>` crea un con segmenti vuoti e mostra come tali segmenti vuoti influiscono sulle varie API:The preceding code creates a with empty segments and shows how those empty segments affect the various APIs:</span><span class="sxs-lookup"><span data-stu-id="da3af-176">The preceding code creates a `ReadOnlySequence<byte>` with empty segments and shows how those empty segments affect the various APIs:</span></span>

- <span data-ttu-id="da3af-177">`ReadOnlySequence<T>.Slice`con `SequencePosition` un che punta a un segmento vuoto mantiene quel segmento.</span><span class="sxs-lookup"><span data-stu-id="da3af-177">`ReadOnlySequence<T>.Slice` with a `SequencePosition` pointing to an empty segment preserves that segment.</span></span>
- <span data-ttu-id="da3af-178">`ReadOnlySequence<T>.Slice`con un int salta i segmenti vuoti.</span><span class="sxs-lookup"><span data-stu-id="da3af-178">`ReadOnlySequence<T>.Slice` with an int skips over the empty segments.</span></span>
- <span data-ttu-id="da3af-179">L'enumerazione dell'enumerazione `ReadOnlySequence<T>` enumera i segmenti vuoti.</span><span class="sxs-lookup"><span data-stu-id="da3af-179">Enumerating the `ReadOnlySequence<T>` enumerates the empty segments.</span></span>

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a><span data-ttu-id="da3af-180">Potenziali problemi con\<ReadOnlySequence T> e SequencePosition</span><span class="sxs-lookup"><span data-stu-id="da3af-180">Potential problems with ReadOnlySequence\<T> and SequencePosition</span></span>

<span data-ttu-id="da3af-181">Ci sono diversi esiti insoliti quando `ReadOnlySpan<T>` / `ReadOnlyMemory<T>` / `T[]` / `int`si tratta di un `ReadOnlySequence<T>` / `SequencePosition` vs un normale :</span><span class="sxs-lookup"><span data-stu-id="da3af-181">There are several unusual outcomes when dealing with a `ReadOnlySequence<T>`/`SequencePosition` vs. a normal `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`:</span></span>

- <span data-ttu-id="da3af-182">`SequencePosition`è un indicatore di `ReadOnlySequence<T>`posizione per una posizione specifica, non una posizione assoluta.</span><span class="sxs-lookup"><span data-stu-id="da3af-182">`SequencePosition` is a position marker for a specific `ReadOnlySequence<T>`, not an absolute position.</span></span> <span data-ttu-id="da3af-183">Poiché è relativo `ReadOnlySequence<T>`a uno specifico , non ha `ReadOnlySequence<T>` significato se utilizzato al di fuori del punto di origine.</span><span class="sxs-lookup"><span data-stu-id="da3af-183">Because it's relative to a specific `ReadOnlySequence<T>`, it doesn't have meaning if used outside of the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="da3af-184">L'aritmetica non `SequencePosition` può `ReadOnlySequence<T>`essere eseguita senza l'oggetto .</span><span class="sxs-lookup"><span data-stu-id="da3af-184">Arithmetic can't be performed on `SequencePosition` without the `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="da3af-185">Ciò significa che `position++` fare `ReadOnlySequence<T>.GetPosition(position, 1)`cose di base come è scritto .</span><span class="sxs-lookup"><span data-stu-id="da3af-185">That means doing basic things like `position++` is written `ReadOnlySequence<T>.GetPosition(position, 1)`.</span></span>
- <span data-ttu-id="da3af-186">`GetPosition(long)`**non** supporta indici negativi.</span><span class="sxs-lookup"><span data-stu-id="da3af-186">`GetPosition(long)` does **not** support negative indexes.</span></span> <span data-ttu-id="da3af-187">Ciò significa che è impossibile ottenere il penultimo carattere senza camminare tutti i segmenti.</span><span class="sxs-lookup"><span data-stu-id="da3af-187">That means it's impossible to get the second to last character without walking all segments.</span></span>
- <span data-ttu-id="da3af-188">Due `SequencePosition` non possono essere confrontati, rendendo difficile:</span><span class="sxs-lookup"><span data-stu-id="da3af-188">Two `SequencePosition` can't be compared, making it difficult to:</span></span>
  - <span data-ttu-id="da3af-189">Sapere se una posizione è maggiore o minore di un'altra posizione.</span><span class="sxs-lookup"><span data-stu-id="da3af-189">Know if one position is greater than or less than another position.</span></span>
  - <span data-ttu-id="da3af-190">Scrivere alcuni algoritmi di analisi.</span><span class="sxs-lookup"><span data-stu-id="da3af-190">Write some parsing algorithms.</span></span>
- <span data-ttu-id="da3af-191">`ReadOnlySequence<T>`è più grande di un riferimento a un oggetto e deve essere passato da [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) o [ref](../../csharp/language-reference/keywords/ref.md) dove possibile.</span><span class="sxs-lookup"><span data-stu-id="da3af-191">`ReadOnlySequence<T>` is bigger than an object reference and should be passed by [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../csharp/language-reference/keywords/ref.md) where possible.</span></span> <span data-ttu-id="da3af-192">Il `ReadOnlySequence<T>` `in` passaggio o `ref` riduce le copie della [struttura](../../csharp/language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="da3af-192">Passing `ReadOnlySequence<T>` by `in` or `ref` reduces copies of the [struct](../../csharp/language-reference/builtin-types/struct.md).</span></span>
- <span data-ttu-id="da3af-193">Segmenti vuoti:</span><span class="sxs-lookup"><span data-stu-id="da3af-193">Empty segments:</span></span>
  - <span data-ttu-id="da3af-194">Sono validi `ReadOnlySequence<T>`all'interno di un file .</span><span class="sxs-lookup"><span data-stu-id="da3af-194">Are valid within a `ReadOnlySequence<T>`.</span></span>
  - <span data-ttu-id="da3af-195">Può apparire quando si `ReadOnlySequence<T>.TryGet` scorre utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="da3af-195">Can appear when iterating using the `ReadOnlySequence<T>.TryGet` method.</span></span>
  - <span data-ttu-id="da3af-196">Può apparire sezionare `ReadOnlySequence<T>.Slice()` la `SequencePosition` sequenza utilizzando il metodo con gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="da3af-196">Can appear slicing the sequence using the `ReadOnlySequence<T>.Slice()` method with `SequencePosition` objects.</span></span>

## <a name="sequencereadert"></a><span data-ttu-id="da3af-197">SequenceReader\<T\></span><span class="sxs-lookup"><span data-stu-id="da3af-197">SequenceReader\<T\></span></span>

<span data-ttu-id="da3af-198"><xref:System.Buffers.SequenceReader%601>:</span><span class="sxs-lookup"><span data-stu-id="da3af-198"><xref:System.Buffers.SequenceReader%601>:</span></span>

- <span data-ttu-id="da3af-199">È un nuovo tipo introdotto in .NET Core 3.0 per semplificare l'elaborazione di un `ReadOnlySequence<T>`oggetto .</span><span class="sxs-lookup"><span data-stu-id="da3af-199">Is a new type that was introduced in .NET Core 3.0 to simplify the processing of a `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="da3af-200">Unifica le differenze `ReadOnlySequence<T>` tra un `ReadOnlySequence<T>`singolo segmento e più segmenti.</span><span class="sxs-lookup"><span data-stu-id="da3af-200">Unifies the differences between a single segment `ReadOnlySequence<T>` and multi-segment `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="da3af-201">Fornisce helper per la lettura`byte` di `char`dati binari e di testo ( e ) che possono o non possono essere suddivisi tra segmenti.</span><span class="sxs-lookup"><span data-stu-id="da3af-201">Provides helpers for reading binary and text data (`byte` and `char`) that may or may not be split across segments.</span></span>

<span data-ttu-id="da3af-202">Esistono metodi incorporati per gestire l'elaborazione di dati binari e delimitati.</span><span class="sxs-lookup"><span data-stu-id="da3af-202">There are built-in methods for dealing with processing both binary and delimited data.</span></span> <span data-ttu-id="da3af-203">Nella sezione seguente viene illustrato l'aspetto di questi stessi metodi con il `SequenceReader<T>`:</span><span class="sxs-lookup"><span data-stu-id="da3af-203">The following section demonstrates what those same methods look like with the `SequenceReader<T>`:</span></span>

### <a name="access-data"></a><span data-ttu-id="da3af-204">Accedere ai dati</span><span class="sxs-lookup"><span data-stu-id="da3af-204">Access data</span></span>

<span data-ttu-id="da3af-205">`SequenceReader<T>`dispone di metodi per enumerare i dati all'interno del `ReadOnlySequence<T>` direttamente.</span><span class="sxs-lookup"><span data-stu-id="da3af-205">`SequenceReader<T>` has methods for enumerating data inside of the `ReadOnlySequence<T>` directly.</span></span> <span data-ttu-id="da3af-206">Il codice seguente è un `ReadOnlySequence<byte>` `byte` esempio di elaborazione di un oggetto alla volta:The following code is an example of processing a at a at a at a time:</span><span class="sxs-lookup"><span data-stu-id="da3af-206">The following code is an example of processing a `ReadOnlySequence<byte>` a `byte` at a time:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

<span data-ttu-id="da3af-207">L'oggetto `CurrentSpan` espone , `Span`ovvero quello del segmento corrente, che è simile a quello eseguito manualmente nel metodo.</span><span class="sxs-lookup"><span data-stu-id="da3af-207">The `CurrentSpan` exposes the current segment's `Span`, which is similar to what was done in the method manually.</span></span>

### <a name="use-position"></a><span data-ttu-id="da3af-208">Usa posizione</span><span class="sxs-lookup"><span data-stu-id="da3af-208">Use position</span></span>

<span data-ttu-id="da3af-209">Il codice seguente è `FindIndexOf` un `SequenceReader<T>`esempio di implementazione dell'utilizzo di :</span><span class="sxs-lookup"><span data-stu-id="da3af-209">The following code is an example implementation of `FindIndexOf` using the `SequenceReader<T>`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a><span data-ttu-id="da3af-210">Elaborare i dati binari</span><span class="sxs-lookup"><span data-stu-id="da3af-210">Process binary data</span></span>

<span data-ttu-id="da3af-211">Nell'esempio riportato di seguito viene analizzata una lunghezza intera `ReadOnlySequence<byte>`bigendian a 4 byte dall'inizio dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="da3af-211">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a><span data-ttu-id="da3af-212">Elaborare i dati di testo</span><span class="sxs-lookup"><span data-stu-id="da3af-212">Process text data</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a><span data-ttu-id="da3af-213">SequenceReader\<\> T problemi comuni</span><span class="sxs-lookup"><span data-stu-id="da3af-213">SequenceReader\<T\> common problems</span></span>

- <span data-ttu-id="da3af-214">Poiché `SequenceReader<T>` è una struttura modificabile, deve essere sempre passata per [riferimento](../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="da3af-214">Because `SequenceReader<T>` is a mutable struct, it should always be passed by [reference](../../csharp/language-reference/keywords/ref.md).</span></span>
- <span data-ttu-id="da3af-215">`SequenceReader<T>`è uno [struct di riferimento,](../../csharp/language-reference/keywords/ref.md#ref-struct-types) pertanto può essere utilizzato solo nei metodi sincroni e non può essere archiviato nei campi.</span><span class="sxs-lookup"><span data-stu-id="da3af-215">`SequenceReader<T>` is a [ref struct](../../csharp/language-reference/keywords/ref.md#ref-struct-types) so it can only be used in synchronous methods and can't be stored in fields.</span></span> <span data-ttu-id="da3af-216">Per ulteriori informazioni, consultate Scrivere codice [C, sicuro ed efficiente.](../../csharp/write-safe-efficient-code.md)</span><span class="sxs-lookup"><span data-stu-id="da3af-216">For more information, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>
- <span data-ttu-id="da3af-217">`SequenceReader<T>`è ottimizzato per l'uso come lettore forward-only.</span><span class="sxs-lookup"><span data-stu-id="da3af-217">`SequenceReader<T>` is optimized for use as a forward-only reader.</span></span> <span data-ttu-id="da3af-218">`Rewind`è destinato a backup di piccole dimensioni che `Read`non `Peek`possono `IsNext` essere risolti utilizzando altre API , e , .</span><span class="sxs-lookup"><span data-stu-id="da3af-218">`Rewind` is intended for small backups that can't be addressed utilizing other `Read`, `Peek`, and `IsNext` APIs.</span></span>
