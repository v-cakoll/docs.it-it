---
title: Matrici (F#)
description: 'Informazioni su come creare e usare matrici nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 27b73efc900ac2efc813fe66f81baa2e9ae1e843
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44135731"
---
# <a name="arrays"></a>Matrici

> [!NOTE]
Il collegamento al riferimento per l'API porta a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Le matrici sono raccolte di dimensioni fisse, in base zero e modificabili di elementi dati consecutivi dello stesso tipo.

## <a name="creating-arrays"></a>Creazione di matrici

È possibile creare matrici in diversi modi. È possibile creare una matrice di piccole dimensioni elencando valori consecutivi compresi tra `[|` e `|]` e separati da punti e virgola, come illustrato negli esempi seguenti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet1.fs)]

È anche possibile inserire ogni elemento in una riga separata, nel qual caso il separatore punto e virgola è facoltativo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet2.fs)]

Il tipo degli elementi della matrice viene derivato dai valori letterali utilizzati e deve essere coerenza. Il codice seguente causa un errore in quanto 1.0 è un valore float e 2 e 3 sono numeri interi.

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

È anche possibile usare espressioni di sequenza per creare matrici. Ecco un esempio che crea una matrice di quadrati di numeri interi da 1 a 10.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet3.fs)]

Per creare una matrice in cui tutti gli elementi vengono inizializzati su zero, usare `Array.zeroCreate`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a>L'accesso agli elementi

È possibile accedere gli elementi della matrice usando un operatore punto (`.`) e parentesi quadre (`[` e `]`).

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet5.fs)]

Gli indici di matrice iniziano da 0.

È possibile accedere anche gli elementi della matrice usando la notazione di sezione, che consente di specificare un intervallo secondario della matrice. Sono riportati esempi di notazione di sezione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet51.fs)]

Quando viene utilizzata la notazione di sezione, viene creata una nuova copia della matrice.

## <a name="array-types-and-modules"></a>I moduli e tipi di matrice

Il tipo di tutte le matrici F # è il tipo .NET Framework <xref:System.Array?displayProperty=nameWithType>. Pertanto, le matrici F # supportano tutte le funzionalità disponibili in <xref:System.Array?displayProperty=nameWithType>.

Il modulo di libreria [ `Microsoft.FSharp.Collections.Array` ](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supporta operazioni su matrici unidimensionali. I moduli `Array2D`, `Array3D`, e `Array4D` contengono funzioni che supportano le operazioni su matrici a due, tre e quattro dimensioni, rispettivamente. È possibile creare matrici di dimensioni maggiore di quattro usando <xref:System.Array?displayProperty=nameWithType>.

### <a name="simple-functions"></a>Funzioni semplici

[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) Ottiene un elemento. [`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) fornisce la lunghezza della matrice. [`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) imposta un elemento a un valore specificato. Esempio di codice seguente viene illustrato l'utilizzo di queste funzioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet9.fs)]

L'output è indicato di seguito.

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>Funzioni di creazione di matrici

Diverse funzioni creano matrici senza la necessità di una matrice esistente. [`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) Crea una nuova matrice che contiene elementi. [`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) Crea una matrice di una dimensione specificata e imposta tutti gli elementi sui valori forniti. [`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) Crea una matrice in base a una dimensione e una funzione per generare gli elementi. [`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) Crea una matrice in cui tutti gli elementi vengono inizializzati sul valore zero per il tipo della matrice. Il codice seguente illustra queste funzioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet91.fs)]

L'output è indicato di seguito.

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) Crea una nuova matrice che contiene gli elementi copiati dalla matrice esistente. Si noti che la copia è una copia superficiale, il che significa che, se il tipo di elemento è un tipo riferimento, viene copiato solo il riferimento, non l'oggetto sottostante. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet11.fs)]

Come indicato di seguito è riportato l'output del codice precedente:

```
[|Test1; Test2; |]
[|; Test2; |]
```

La stringa `Test1` viene visualizzato solo nella prima matrice perché l'operazione di creazione di un nuovo elemento sovrascrive il riferimento nel `firstArray` ma non influisce sul riferimento originale a una stringa vuota ancora presente in `secondArray`. La stringa `Test2` viene visualizzato in entrambe le matrici in quanto il `Insert` operazione sulle <xref:System.Text.StringBuilder?displayProperty=nameWithType> influisce sul tipo sottostante <xref:System.Text.StringBuilder?displayProperty=nameWithType> oggetto, che viene fatto riferimento in entrambe le matrici.

[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) Genera una nuova matrice da un intervallo secondario di una matrice. Per specificare l'intervallo secondario, fornendo l'indice iniziale e la lunghezza. Il codice seguente illustra l'uso di `Array.sub`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet12.fs)]

L'output mostra che la sottomatrice inizia con l'elemento 5 e contiene 10 elementi.

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```
[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) Crea una nuova matrice combinando due matrici esistenti.

Il codice seguente illustra **Array. Append**.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet13.fs)]

L'output del codice precedente è come indicato di seguito.

```
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) Seleziona gli elementi della matrice da includere in una nuova matrice. Il codice seguente illustra `Array.choose`. Si noti che il tipo di elemento della matrice non deve corrispondere al tipo del valore restituito nel tipo di opzione. In questo esempio, è il tipo di elemento `int` e l'opzione è il risultato di una funzione polinomiale, `elem*elem - 1`, come mobile numero a virgola.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet14.fs)]

L'output del codice precedente è come indicato di seguito.

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) esegue una funzione specificata su ogni elemento della matrice di una matrice esistente e quindi raccoglie gli elementi generati dalla funzione e li combina in una nuova matrice. Il codice seguente illustra `Array.collect`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet15.fs)]

L'output del codice precedente è come indicato di seguito.

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) accetta una sequenza di matrici e li combina in un'unica matrice. Il codice seguente illustra `Array.concat`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet16.fs)]

L'output del codice precedente è come indicato di seguito.

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) accetta una funzione di condizione booleana e genera una nuova matrice che contiene solo gli elementi della matrice di input per il quale la condizione è true. Il codice seguente illustra `Array.filter`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet17.fs)]

L'output del codice precedente è come indicato di seguito.

```
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) Genera una nuova matrice invertendo l'ordine di una matrice esistente. Il codice seguente illustra `Array.rev`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet18.fs)]  

L'output del codice precedente è come indicato di seguito.

```
"Hello world!"
```

È possibile combinare agevolmente funzioni nel modulo della matrice che trasformano matrici tramite l'operatore pipeline (`|>`), come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet19.fs)]

L'output è

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a>Matrici multidimensionali

È possibile creare una matrice multidimensionale, ma non è disponibile alcuna sintassi per la scrittura di un valore letterale di matrice multidimensionale. Usare l'operatore [ `array2D` ](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) per creare una matrice da una sequenza di sequenze di elementi della matrice. Le sequenze possono essere valori letterali di matrice o elenco. Ad esempio, il codice seguente crea una matrice bidimensionale.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet20.fs)]

È anche possibile usare la funzione [ `Array2D.init` ](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) funzioni sono disponibili per le matrici a tre e quattro dimensioni a inizializzare matrici a due dimensioni e così via. Queste funzioni accettano una funzione che viene usata per creare gli elementi. Per creare una matrice bidimensionale contenente elementi impostati su un valore iniziale anziché specificare una funzione, usare il [ `Array2D.create` ](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) funzione, che è disponibile anche per le matrici fino a quattro dimensioni. Esempio di codice seguente viene innanzitutto illustrato come creare una matrice di matrici che contengono gli elementi desiderati e quindi Usa `Array2D.init` per generare la matrice bidimensionale desiderata.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet21.fs)]

Indicizzazione della matrice e sintassi di sezionamento è supportata per le matrici fino a 4 dimensioni. Quando si specifica un indice in più dimensioni, utilizzare virgole per separare gli indici, come illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet22.fs)]

Il tipo di una matrice bidimensionale viene scritto come `<type>[,]` (ad esempio `int[,]`, `double[,]`), e il tipo di una matrice tridimensionale viene scritto come `<type>[,,]`, e così via per le matrici di dimensioni superiori.

Solo un subset delle funzioni disponibili per le matrici unidimensionali è disponibile anche per le matrici multidimensionali. Per altre informazioni, vedere [ `Collections.Array Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [ `Collections.Array2D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [ `Collections.Array3D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), e [ `Collections.Array4D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).

### <a name="array-slicing-and-multidimensional-arrays"></a>Sezionamento di matrice e le matrici multidimensionali

In una matrice bidimensionale (matrice), è possibile estrarre una matrice secondaria specificando gli intervalli e utilizzando un carattere jolly (`*`) carattere per specificare intere righe o colonne.

```fsharp
/ Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

A partire da F # 3.1, è possibile scomporre una matrice multidimensionale in sottomatrici della dimensione uguale o inferiore. Ad esempio, è possibile ottenere un vettore da una matrice, specificando una singola riga o colonna.

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

È possibile utilizzare questa sintassi di sezionamento per i tipi che implementano gli operatori di accesso di elemento e sottoposti a overload `GetSlice` metodi. Ad esempio, il codice seguente crea un tipo Matrix che esegue il wrapping della matrice 2D F #, implementa una proprietà dell'elemento per fornire supporto per l'indicizzazione della matrice e implementa tre versioni di `GetSlice`. Se è possibile utilizzare questo codice come modello per i tipi di matrice, è possibile usare tutte le operazioni di sezionamento descritte in questa sezione.

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

### <a name="boolean-functions-on-arrays"></a>Funzioni booleane nelle matrici

Le funzioni [ `Array.exists` ](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) e [ `Array.exists2` ](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) testano gli elementi in uno o due matrici, rispettivamente. Queste funzioni accettano una funzione di test e restituiscono `true` se non esiste un elemento (o coppia di elementi per `Array.exists2`) che soddisfa la condizione.

Il codice seguente illustra l'uso di `Array.exists` e `Array.exists2`. In questi esempi, nuove funzioni vengono create applicando solo uno degli argomenti, in questi casi, l'argomento della funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet23.fs)]

L'output del codice precedente è come indicato di seguito.

```
true
false
false
true
```

Analogamente, la funzione [ `Array.forall` ](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) testa una matrice per determinare se ogni elemento soddisfa una condizione booleana. La variazione [ `Array.forall2` ](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) esegue la stessa operazione usando una funzione booleana che coinvolge gli elementi di due matrici di uguale lunghezza. Il codice seguente viene illustrato l'utilizzo di queste funzioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet24.fs)]

L'output per questi esempi è come indicato di seguito.

```
false
true
true
false
```

### <a name="searching-arrays"></a>La ricerca di matrici

[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) accetta una funzione booleana e restituisce il primo elemento per cui la funzione restituisce `true`, o genera un <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> se viene trovato alcun elemento che soddisfa la condizione. [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) è simile a `Array.find`, ad eccezione del fatto che restituisce l'indice dell'elemento anziché l'elemento stesso.

Il codice seguente usa `Array.find` e `Array.findIndex` per individuare un numero che è sia un quadrato perfetto e un cubo perfetto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet25.fs)]

L'output è indicato di seguito.

```
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) è simile a `Array.find`, ad eccezione del fatto che il risultato è un tipo di opzione e restituisce `None` se viene trovato alcun elemento. `Array.tryFind` deve essere usato al posto della `Array.find` quando non si conosce se è un elemento corrispondente nella matrice. Analogamente, [ `Array.tryFindIndex` ](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) è simile a [ `Array.findIndex` ](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) ad eccezione del fatto che il tipo di opzione è il valore restituito. Se viene trovato alcun elemento, l'opzione è `None`.

Il codice seguente illustra l'uso di `Array.tryFind`. Questo codice dipende dal codice precedente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet26.fs)]

L'output è indicato di seguito.

```
Found an element: 1
Found an element: 729
```

Uso [ `Array.tryPick` ](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) quando è necessario trasformare un elemento, oltre a rilevarlo. Il risultato è il primo elemento per cui la funzione restituisce l'elemento trasformato come valore di opzione o `None` se tale elemento non viene trovato.

Il codice seguente illustra l'uso di `Array.tryPick`. In questo caso, invece di un'espressione lambda, vengono definite diverse funzioni di supporto locale per semplificare il codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet27.fs)]

L'output è indicato di seguito.

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a>Esecuzione di calcoli sulle matrici

Il [ `Array.average` ](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) funzione restituisce la media di ogni elemento in una matrice. È limitato ai tipi di elementi che supportano l'esatta divisione per un numero intero, che include tipi a virgola mobile ma non tipi integrali. Il [ `Array.averageBy` ](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) funzione restituisce la media dei risultati della chiamata a una funzione su ogni elemento. Per una matrice di tipo integrale, è possibile usare `Array.averageBy` e avere la funzione converta ogni elemento in Mobile tipo per il calcolo del punto.

Uso [ `Array.max` ](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) oppure [ `Array.min` ](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) per ottenere l'elemento massimo o minimo, se il tipo di elemento lo supporta. Analogamente, [ `Array.maxBy` ](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) e [ `Array.minBy` ](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) consentono a una funzione da eseguire prima di tutto, ad esempio per trasformarla in un tipo che supporta il confronto.

[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) Aggiunge gli elementi della matrice, e [ `Array.sumBy` ](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) chiama una funzione su ogni elemento e aggiunge i risultati tra loro.

Per eseguire una funzione su ogni elemento in una matrice senza archiviare i valori restituiti, utilizzare [ `Array.iter` ](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516). Per una funzione che interessa due matrici di uguale lunghezza, utilizzare [ `Array.iter2` ](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc). Se è necessario anche mantenere una matrice dei risultati della funzione, usare [ `Array.map` ](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) oppure [ `Array.map2` ](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), che opera su due matrici contemporaneamente.

Le variazioni [ `Array.iteri` ](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) e [ `Array.iteri2` ](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) consentono l'indice dell'elemento da essere coinvolto nel calcolo; lo stesso vale per [ `Array.mapi` ](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) e [ `Array.mapi2` ](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).

Le funzioni [ `Array.fold` ](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [ `Array.foldBack` ](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [ `Array.reduce` ](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [ `Array.reduceBack` ](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [ `Array.scan` ](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), e [ `Array.scanBack` ](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) eseguono algoritmi che coinvolgono tutti gli elementi della matrice. Analogamente, le variazioni [ `Array.fold2` ](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) e [ `Array.foldBack2` ](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) eseguono calcoli su due matrici.

Queste funzioni per l'esecuzione di calcoli corrispondono alle funzioni con lo stesso nome nel [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788). Per esempi di utilizzo, vedere [Elenca](lists.md).

### <a name="modifying-arrays"></a>Modifica di matrici

[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) imposta un elemento a un valore specificato. [`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) imposta un intervallo di elementi in una matrice a un valore specificato. Il codice seguente viene fornito un esempio di `Array.fill`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet28.fs)]

L'output è indicato di seguito.

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

È possibile usare [ `Array.blit` ](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) per copiare una sottosezione di una matrice a un'altra matrice.

### <a name="converting-to-and-from-other-types"></a>Conversione da e verso altri tipi

[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) Crea una matrice da un elenco. [`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) Crea una matrice da una sequenza. [`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) e [ `Array.toSeq` ](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convertire questi altri tipi di raccolta dal tipo di matrice.

### <a name="sorting-arrays"></a>Ordinamento di matrici

Uso [ `Array.sort` ](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) per ordinare una matrice usando la funzione di confronto generico. Uso [ `Array.sortBy` ](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) per specificare una funzione che genera un valore, definito come una *chiave*, da ordinare utilizzando la funzione di confronto generica sulla chiave. Uso [ `Array.sortWith` ](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) se si desidera fornire una funzione di confronto personalizzato. `Array.sort`, `Array.sortBy`, e `Array.sortWith` tutti restituire la matrice ordinata come nuova matrice. Le variazioni [ `Array.sortInPlace` ](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [ `Array.sortInPlaceBy` ](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), e [ `Array.sortInPlaceWith` ](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modificano la matrice esistente anziché restituirne una nuova.

### <a name="arrays-and-tuples"></a>Matrici e Tuple

Le funzioni [ `Array.zip` ](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) e [ `Array.unzip` ](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convertono matrici di coppie di tuple in tuple di matrici e viceversa. [`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) e [ `Array.unzip3` ](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) sono simili ad eccezione del fatto che funzionano con tuple di tre elementi o di tre matrici.

## <a name="parallel-computations-on-arrays"></a>Calcoli paralleli sulle matrici

Il modulo [ `Array.Parallel` ](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contiene funzioni per l'esecuzione di calcoli paralleli sulle matrici. Questo modulo non è disponibile nelle applicazioni destinate alle versioni di .NET Framework precedenti alla versione 4.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [F #; Tipi](fsharp-types.md)
