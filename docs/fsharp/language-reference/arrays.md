---
title: Array
description: Informazioni su come creare e usare matrici nel linguaggio di F# programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 8470e01087e417635bcd5c528df9b9e089cbf59f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320496"
---
# <a name="arrays"></a><span data-ttu-id="e869e-103">Array</span><span class="sxs-lookup"><span data-stu-id="e869e-103">Arrays</span></span>

> [!NOTE]
> <span data-ttu-id="e869e-104">Il collegamento al riferimento per l'API porta a MSDN.</span><span class="sxs-lookup"><span data-stu-id="e869e-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="e869e-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="e869e-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e869e-106">Le matrici sono raccolte a dimensione fissa, in base zero e modificabili di elementi di dati consecutivi che sono tutti dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="e869e-106">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="e869e-107">Creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-107">Creating Arrays</span></span>

<span data-ttu-id="e869e-108">È possibile creare matrici in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="e869e-108">You can create arrays in several ways.</span></span> <span data-ttu-id="e869e-109">È possibile creare una matrice di piccole dimensioni elencando i valori consecutivi tra `[|` e `|]` e separati da punti e virgola, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="e869e-109">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="e869e-110">È anche possibile inserire ogni elemento su una riga distinta, nel qual caso il separatore punto e virgola è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e869e-110">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="e869e-111">Il tipo degli elementi della matrice viene dedotto dai valori letterali utilizzati e deve essere coerente.</span><span class="sxs-lookup"><span data-stu-id="e869e-111">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="e869e-112">Il codice seguente genera un errore perché 1,0 è un valore float e 2 e 3 sono numeri interi.</span><span class="sxs-lookup"><span data-stu-id="e869e-112">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="e869e-113">È anche possibile usare espressioni di sequenza per creare matrici.</span><span class="sxs-lookup"><span data-stu-id="e869e-113">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="e869e-114">Di seguito è riportato un esempio in cui viene creata una matrice di quadrati di numeri interi da 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="e869e-114">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="e869e-115">Per creare una matrice in cui tutti gli elementi vengono inizializzati su zero, utilizzare `Array.zeroCreate`.</span><span class="sxs-lookup"><span data-stu-id="e869e-115">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a><span data-ttu-id="e869e-116">Accesso agli elementi</span><span class="sxs-lookup"><span data-stu-id="e869e-116">Accessing Elements</span></span>

<span data-ttu-id="e869e-117">È possibile accedere agli elementi della matrice utilizzando un operatore punto (`.`) e le parentesi quadre (`[` e `]`).</span><span class="sxs-lookup"><span data-stu-id="e869e-117">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="e869e-118">Gli indici di matrice iniziano da 0.</span><span class="sxs-lookup"><span data-stu-id="e869e-118">Array indexes start at 0.</span></span>

<span data-ttu-id="e869e-119">È inoltre possibile accedere agli elementi della matrice utilizzando la notazione Slice, che consente di specificare un intervallo secondario della matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-119">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="e869e-120">Seguono esempi di notazione Slice.</span><span class="sxs-lookup"><span data-stu-id="e869e-120">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="e869e-121">Quando si usa la notazione Slice, viene creata una nuova copia della matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-121">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="e869e-122">Tipi e moduli di matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-122">Array Types and Modules</span></span>

<span data-ttu-id="e869e-123">Il tipo di tutte F# le matrici è il tipo di .NET Framework <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e869e-123">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e869e-124">Pertanto, F# le matrici supportano tutte le funzionalità disponibili in <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e869e-124">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="e869e-125">Il modulo di libreria [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supporta operazioni su matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="e869e-125">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="e869e-126">I moduli `Array2D`, `Array3D` e `Array4D` contengono funzioni che supportano rispettivamente le operazioni su matrici di due, tre e quattro dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e869e-126">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="e869e-127">È possibile creare matrici di rango maggiori di quattro usando <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e869e-127">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="e869e-128">Funzioni semplici</span><span class="sxs-lookup"><span data-stu-id="e869e-128">Simple Functions</span></span>

<span data-ttu-id="e869e-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) ottiene un elemento.</span><span class="sxs-lookup"><span data-stu-id="e869e-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="e869e-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) restituisce la lunghezza di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="e869e-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) imposta un elemento su un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="e869e-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="e869e-132">Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="e869e-132">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="e869e-133">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e869e-133">The output is as follows.</span></span>

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="e869e-134">Funzioni che creano matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-134">Functions That Create Arrays</span></span>

<span data-ttu-id="e869e-135">Diverse funzioni creano matrici senza richiedere una matrice esistente.</span><span class="sxs-lookup"><span data-stu-id="e869e-135">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="e869e-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) crea una nuova matrice che non contiene elementi.</span><span class="sxs-lookup"><span data-stu-id="e869e-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="e869e-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) crea una matrice di dimensioni specificate e imposta tutti gli elementi sui valori forniti.</span><span class="sxs-lookup"><span data-stu-id="e869e-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="e869e-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) crea una matrice, data una dimensione e una funzione per generare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="e869e-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="e869e-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) crea una matrice in cui tutti gli elementi vengono inizializzati sul valore zero per il tipo della matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="e869e-140">Il codice seguente illustra queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="e869e-140">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="e869e-141">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e869e-141">The output is as follows.</span></span>

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="e869e-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) crea una nuova matrice che contiene gli elementi copiati da una matrice esistente.</span><span class="sxs-lookup"><span data-stu-id="e869e-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="e869e-143">Si noti che la copia è una copia superficiale, il che significa che se il tipo di elemento è un tipo di riferimento, viene copiato solo il riferimento, non l'oggetto sottostante.</span><span class="sxs-lookup"><span data-stu-id="e869e-143">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="e869e-144">Questo aspetto è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-144">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="e869e-145">L'output del codice precedente è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e869e-145">The output of the preceding code is as follows:</span></span>

```console
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="e869e-146">La stringa `Test1` viene visualizzata solo nella prima matrice perché l'operazione di creazione di un nuovo elemento sovrascrive il riferimento in `firstArray` ma non influisce sul riferimento originale a una stringa vuota che è ancora presente in `secondArray`.</span><span class="sxs-lookup"><span data-stu-id="e869e-146">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="e869e-147">La stringa `Test2` viene visualizzata in entrambe le matrici perché l'operazione `Insert` sul tipo di <xref:System.Text.StringBuilder?displayProperty=nameWithType> influiscono sull'oggetto <xref:System.Text.StringBuilder?displayProperty=nameWithType> sottostante, a cui viene fatto riferimento in entrambe le matrici.</span><span class="sxs-lookup"><span data-stu-id="e869e-147">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="e869e-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) genera una nuova matrice da un intervallo secondario di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="e869e-149">È possibile specificare l'intervallo secondario fornendo l'indice iniziale e la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="e869e-149">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="e869e-150">Il codice seguente illustra l'uso di `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="e869e-150">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="e869e-151">L'output mostra che la sottomatrice inizia dall'elemento 5 e contiene 10 elementi.</span><span class="sxs-lookup"><span data-stu-id="e869e-151">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

<span data-ttu-id="e869e-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) crea una nuova matrice combinando due matrici esistenti.</span><span class="sxs-lookup"><span data-stu-id="e869e-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="e869e-153">Il codice seguente illustra **Array. Append**.</span><span class="sxs-lookup"><span data-stu-id="e869e-153">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="e869e-154">L'output del codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-154">The output of the preceding code is as follows.</span></span>

```console
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="e869e-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) seleziona gli elementi di una matrice da includere in una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="e869e-156">Il codice seguente illustra `Array.choose`.</span><span class="sxs-lookup"><span data-stu-id="e869e-156">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="e869e-157">Si noti che il tipo di elemento della matrice non deve corrispondere al tipo del valore restituito nel tipo di opzione.</span><span class="sxs-lookup"><span data-stu-id="e869e-157">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="e869e-158">In questo esempio, il tipo di elemento è `int` e l'opzione è il risultato di una funzione polinomiale, `elem*elem - 1`, come numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="e869e-158">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="e869e-159">L'output del codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-159">The output of the preceding code is as follows.</span></span>

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="e869e-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) esegue una funzione specificata su ogni elemento di matrice di una matrice esistente e quindi raccoglie gli elementi generati dalla funzione e li combina in una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="e869e-161">Il codice seguente illustra `Array.collect`.</span><span class="sxs-lookup"><span data-stu-id="e869e-161">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="e869e-162">L'output del codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-162">The output of the preceding code is as follows.</span></span>

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="e869e-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) accetta una sequenza di matrici e le combina in un'unica matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="e869e-164">Il codice seguente illustra `Array.concat`.</span><span class="sxs-lookup"><span data-stu-id="e869e-164">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="e869e-165">L'output del codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-165">The output of the preceding code is as follows.</span></span>

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="e869e-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) accetta una funzione di condizione booleana e genera una nuova matrice che contiene solo gli elementi della matrice di input per i quali la condizione è true.</span><span class="sxs-lookup"><span data-stu-id="e869e-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="e869e-167">Il codice seguente illustra `Array.filter`.</span><span class="sxs-lookup"><span data-stu-id="e869e-167">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="e869e-168">L'output del codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-168">The output of the preceding code is as follows.</span></span>

```console
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="e869e-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) genera una nuova matrice invertendo l'ordine di una matrice esistente.</span><span class="sxs-lookup"><span data-stu-id="e869e-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="e869e-170">Il codice seguente illustra `Array.rev`.</span><span class="sxs-lookup"><span data-stu-id="e869e-170">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

<span data-ttu-id="e869e-171">L'output del codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-171">The output of the preceding code is as follows.</span></span>

```console
"Hello world!"
```

<span data-ttu-id="e869e-172">È possibile combinare facilmente le funzioni nel modulo di matrice per trasformare le matrici usando l'operatore pipeline (`|>`), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-172">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="e869e-173">L'output è</span><span class="sxs-lookup"><span data-stu-id="e869e-173">The output is</span></span>

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="e869e-174">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="e869e-174">Multidimensional Arrays</span></span>

<span data-ttu-id="e869e-175">È possibile creare una matrice multidimensionale, ma non esiste alcuna sintassi per la scrittura di un valore letterale di matrice multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="e869e-175">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="e869e-176">Usare l'operatore [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) per creare una matrice da una sequenza di sequenze di elementi di matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-176">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="e869e-177">Le sequenze possono essere valori letterali di matrice o di elenco.</span><span class="sxs-lookup"><span data-stu-id="e869e-177">The sequences can be array or list literals.</span></span> <span data-ttu-id="e869e-178">Il codice seguente, ad esempio, consente di creare una matrice bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="e869e-178">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="e869e-179">È inoltre possibile utilizzare la funzione [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) per inizializzare matrici di due dimensioni e funzioni simili sono disponibili per matrici di tre e quattro dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e869e-179">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="e869e-180">Queste funzioni accettano una funzione utilizzata per creare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="e869e-180">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="e869e-181">Per creare una matrice bidimensionale che contiene elementi impostati su un valore iniziale anziché specificare una funzione, utilizzare la funzione [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) , disponibile anche per le matrici con un massimo di quattro dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e869e-181">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="e869e-182">Nell'esempio di codice seguente viene prima illustrato come creare una matrice di matrici che contengono gli elementi desiderati, quindi viene utilizzato `Array2D.init` per generare la matrice bidimensionale desiderata.</span><span class="sxs-lookup"><span data-stu-id="e869e-182">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="e869e-183">L'indicizzazione della matrice e la sintassi di sezionamento sono supportate per le matrici fino a Rank 4.</span><span class="sxs-lookup"><span data-stu-id="e869e-183">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="e869e-184">Quando si specifica un indice in più dimensioni, si utilizzano le virgole per separare gli indici, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-184">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="e869e-185">Il tipo di una matrice bidimensionale viene scritto come `<type>[,]` (ad esempio, `int[,]`, `double[,]`) e il tipo di una matrice tridimensionale viene scritto come `<type>[,,]` e così via per le matrici di dimensioni più elevate.</span><span class="sxs-lookup"><span data-stu-id="e869e-185">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="e869e-186">Per le matrici multidimensionali è disponibile anche solo un subset delle funzioni disponibili per le matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="e869e-186">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="e869e-187">Per ulteriori informazioni, vedere [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d)e [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="e869e-187">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="e869e-188">Sezionamento di matrici e matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="e869e-188">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="e869e-189">In una matrice bidimensionale (matrice) è possibile estrarre una sottomatrice specificando gli intervalli e usando un carattere jolly (`*`) per specificare intere righe o colonne.</span><span class="sxs-lookup"><span data-stu-id="e869e-189">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="e869e-190">A partire F# da 3,1, è possibile scomporre una matrice multidimensionale in sottomatrici della dimensione uguale o inferiore.</span><span class="sxs-lookup"><span data-stu-id="e869e-190">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="e869e-191">È ad esempio possibile ottenere un vettore da una matrice specificando una singola riga o colonna.</span><span class="sxs-lookup"><span data-stu-id="e869e-191">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="e869e-192">È possibile usare questa sintassi di sezionamento per i tipi che implementano gli operatori di accesso agli elementi e i metodi di `GetSlice` di overload.</span><span class="sxs-lookup"><span data-stu-id="e869e-192">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="e869e-193">Il codice seguente, ad esempio, consente di creare un tipo di matrice F# che esegue il wrapping della matrice 2D, implementa una proprietà Item per fornire supporto per l'indicizzazione della matrice e implementa tre versioni di `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="e869e-193">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="e869e-194">Se è possibile usare questo codice come modello per i tipi di matrice, è possibile usare tutte le operazioni di sezionamento descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e869e-194">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="e869e-195">Funzioni booleane sulle matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-195">Boolean Functions on Arrays</span></span>

<span data-ttu-id="e869e-196">Le funzioni [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) e [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) elementi di test rispettivamente in una o due matrici.</span><span class="sxs-lookup"><span data-stu-id="e869e-196">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="e869e-197">Queste funzioni accettano una funzione di test e restituiscono `true` se è presente un elemento (o coppia di elementi per `Array.exists2`) che soddisfa la condizione.</span><span class="sxs-lookup"><span data-stu-id="e869e-197">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="e869e-198">Il codice seguente illustra l'uso di `Array.exists` e `Array.exists2`.</span><span class="sxs-lookup"><span data-stu-id="e869e-198">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="e869e-199">In questi esempi, le nuove funzioni vengono create applicando solo uno degli argomenti, in questi casi, l'argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="e869e-199">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="e869e-200">L'output del codice precedente è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-200">The output of the preceding code is as follows.</span></span>

```console
true
false
false
true
```

<span data-ttu-id="e869e-201">Analogamente, la funzione [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) verifica una matrice per determinare se ogni elemento soddisfa una condizione booleana.</span><span class="sxs-lookup"><span data-stu-id="e869e-201">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="e869e-202">La variazione [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) esegue la stessa operazione utilizzando una funzione booleana che include elementi di due matrici di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="e869e-202">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="e869e-203">Il codice seguente illustra l'uso di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="e869e-203">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="e869e-204">L'output di questi esempi è il seguente.</span><span class="sxs-lookup"><span data-stu-id="e869e-204">The output for these examples is as follows.</span></span>

```console
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="e869e-205">Ricerca di matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-205">Searching Arrays</span></span>

<span data-ttu-id="e869e-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) accetta una funzione booleana e restituisce il primo elemento per il quale la funzione restituisce `true` oppure genera un <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> se non viene trovato alcun elemento che soddisfi la condizione.</span><span class="sxs-lookup"><span data-stu-id="e869e-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="e869e-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) è come `Array.find`, ad eccezione del fatto che restituisce l'indice dell'elemento anziché l'elemento stesso.</span><span class="sxs-lookup"><span data-stu-id="e869e-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="e869e-208">Il codice seguente usa `Array.find` e `Array.findIndex` per individuare un numero che sia un quadrato perfetto e un cubo perfetto.</span><span class="sxs-lookup"><span data-stu-id="e869e-208">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="e869e-209">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e869e-209">The output is as follows.</span></span>

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="e869e-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) è come `Array.find`, ad eccezione del fatto che il risultato è un tipo di opzione e restituisce `None` se non viene trovato alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="e869e-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="e869e-211">Quando non si sa se un elemento corrispondente è presente nella matrice, è necessario utilizzare `Array.tryFind` anziché `Array.find`.</span><span class="sxs-lookup"><span data-stu-id="e869e-211">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="e869e-212">Analogamente, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) è come [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) ad eccezione del fatto che il tipo di opzione è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="e869e-212">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="e869e-213">Se non viene trovato alcun elemento, l'opzione viene `None`.</span><span class="sxs-lookup"><span data-stu-id="e869e-213">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="e869e-214">Il codice seguente illustra l'uso di `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="e869e-214">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="e869e-215">Questo codice dipende dal codice precedente.</span><span class="sxs-lookup"><span data-stu-id="e869e-215">This code depends on the previous code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="e869e-216">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e869e-216">The output is as follows.</span></span>

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

<span data-ttu-id="e869e-217">Usare [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) quando è necessario trasformare un elemento oltre a trovarlo.</span><span class="sxs-lookup"><span data-stu-id="e869e-217">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="e869e-218">Il risultato è il primo elemento per il quale la funzione restituisce l'elemento trasformato come valore di opzione o `None` se tale elemento non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e869e-218">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="e869e-219">Il codice seguente illustra l'uso di `Array.tryPick`.</span><span class="sxs-lookup"><span data-stu-id="e869e-219">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="e869e-220">In questo caso, anziché un'espressione lambda, sono definite diverse funzioni helper locali per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="e869e-220">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="e869e-221">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e869e-221">The output is as follows.</span></span>

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="e869e-222">Esecuzione di calcoli su matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-222">Performing Computations on Arrays</span></span>

<span data-ttu-id="e869e-223">La funzione [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) restituisce la media di ogni elemento in una matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-223">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="e869e-224">È limitata ai tipi di elemento che supportano la divisione esatta per un intero, che include tipi a virgola mobile ma non tipi integrali.</span><span class="sxs-lookup"><span data-stu-id="e869e-224">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="e869e-225">La funzione [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) restituisce la media dei risultati della chiamata a una funzione su ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="e869e-225">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="e869e-226">Per una matrice di tipo integrale, è possibile usare `Array.averageBy` e fare in modo che la funzione converta ogni elemento in un tipo a virgola mobile per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="e869e-226">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="e869e-227">Usare [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) o [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) per ottenere l'elemento massimo o minimo, se il tipo di elemento lo supporta.</span><span class="sxs-lookup"><span data-stu-id="e869e-227">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="e869e-228">Analogamente, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) e [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) consentono di eseguire una funzione per prima, forse per trasformare in un tipo che supporta il confronto.</span><span class="sxs-lookup"><span data-stu-id="e869e-228">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="e869e-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) aggiunge gli elementi di una matrice e [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) chiama una funzione su ogni elemento e aggiunge i risultati insieme.</span><span class="sxs-lookup"><span data-stu-id="e869e-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="e869e-230">Per eseguire una funzione su ogni elemento in una matrice senza archiviare i valori restituiti, usare [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span><span class="sxs-lookup"><span data-stu-id="e869e-230">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="e869e-231">Per una funzione che interessa due matrici di uguale lunghezza, utilizzare [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span><span class="sxs-lookup"><span data-stu-id="e869e-231">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="e869e-232">Se è necessario anche contenere una matrice dei risultati della funzione, usare [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) o [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), che opera su due matrici alla volta.</span><span class="sxs-lookup"><span data-stu-id="e869e-232">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="e869e-233">Le variazioni [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) e [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) consentono di partecipare all'indice dell'elemento nel calcolo; lo stesso vale per [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) e [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span><span class="sxs-lookup"><span data-stu-id="e869e-233">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="e869e-234">Le funzioni [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0)e [1](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) eseguono algoritmi che coinvolgono tutti gli elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-234">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="e869e-235">Analogamente, le variazioni [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) e [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) eseguono calcoli su due matrici.</span><span class="sxs-lookup"><span data-stu-id="e869e-235">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="e869e-236">Queste funzioni per l'esecuzione di calcoli corrispondono alle funzioni con lo stesso nome nel [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="e869e-236">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="e869e-237">Per esempi di utilizzo, vedere [elenchi](lists.md).</span><span class="sxs-lookup"><span data-stu-id="e869e-237">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="e869e-238">Modifica di matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-238">Modifying Arrays</span></span>

<span data-ttu-id="e869e-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) imposta un elemento su un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="e869e-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="e869e-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) imposta un intervallo di elementi in una matrice su un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="e869e-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="e869e-241">Il codice seguente fornisce un esempio di `Array.fill`.</span><span class="sxs-lookup"><span data-stu-id="e869e-241">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="e869e-242">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e869e-242">The output is as follows.</span></span>

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="e869e-243">È possibile usare [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) per copiare una sottosezione di una matrice in un'altra matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-243">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="e869e-244">Conversione da e verso altri tipi</span><span class="sxs-lookup"><span data-stu-id="e869e-244">Converting to and from Other Types</span></span>

<span data-ttu-id="e869e-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) crea una matrice da un elenco.</span><span class="sxs-lookup"><span data-stu-id="e869e-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="e869e-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) crea una matrice da una sequenza.</span><span class="sxs-lookup"><span data-stu-id="e869e-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="e869e-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) e [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) eseguire la conversione in questi altri tipi di raccolta dal tipo di matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="e869e-248">Ordinamento di matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-248">Sorting Arrays</span></span>

<span data-ttu-id="e869e-249">Utilizzare [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) per ordinare una matrice utilizzando la funzione di confronto generica.</span><span class="sxs-lookup"><span data-stu-id="e869e-249">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="e869e-250">Usare [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) per specificare una funzione che genera un valore, denominato *chiave*, per eseguire l'ordinamento usando la funzione di confronto generica sulla chiave.</span><span class="sxs-lookup"><span data-stu-id="e869e-250">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="e869e-251">Utilizzare [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) se si desidera fornire una funzione di confronto personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e869e-251">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="e869e-252">`Array.sort`, `Array.sortBy` e `Array.sortWith` restituiscono tutti la matrice ordinata come nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="e869e-252">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="e869e-253">Le variazioni [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f)e [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modificare la matrice esistente anziché restituirne una nuova.</span><span class="sxs-lookup"><span data-stu-id="e869e-253">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="e869e-254">Matrici e Tuple</span><span class="sxs-lookup"><span data-stu-id="e869e-254">Arrays and Tuples</span></span>

<span data-ttu-id="e869e-255">Le funzioni [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) e [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convertire matrici di coppie di tuple in tuple di matrici e viceversa.</span><span class="sxs-lookup"><span data-stu-id="e869e-255">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="e869e-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) e [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) sono simili, ad eccezione del fatto che funzionano con Tuple di tre elementi o Tuple di tre matrici.</span><span class="sxs-lookup"><span data-stu-id="e869e-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="e869e-257">Calcoli paralleli sulle matrici</span><span class="sxs-lookup"><span data-stu-id="e869e-257">Parallel Computations on Arrays</span></span>

<span data-ttu-id="e869e-258">Il modulo [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contiene funzioni per l'esecuzione di calcoli paralleli sulle matrici.</span><span class="sxs-lookup"><span data-stu-id="e869e-258">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="e869e-259">Questo modulo non è disponibile nelle applicazioni destinate alle versioni del .NET Framework precedenti alla versione 4.</span><span class="sxs-lookup"><span data-stu-id="e869e-259">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="e869e-260">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e869e-260">See also</span></span>

- [<span data-ttu-id="e869e-261">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="e869e-261">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e869e-262">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="e869e-262">F# Types</span></span>](fsharp-types.md)
