---
title: Sequenze
description: Informazioni su come utilizzare F# le sequenze, quando si dispone di una raccolta di dati di grandi dimensioni ordinata, ma non si prevede necessariamente di utilizzare tutti gli elementi.
ms.date: 11/04/2019
ms.openlocfilehash: 34e03f1cead0a9f678f637afcb6c8397ef7572bc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971437"
---
# <a name="sequences"></a>Sequenze

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Una *sequenza* è una serie logica di elementi di un solo tipo. Le sequenze sono particolarmente utili quando si dispone di una raccolta di dati grande e ordinata, ma non necessariamente si prevede di usare tutti gli elementi. I singoli elementi di sequenza vengono calcolati solo se necessario, pertanto una sequenza può offrire prestazioni migliori rispetto a un elenco in situazioni in cui non vengono utilizzati tutti gli elementi. Le sequenze sono rappresentate dal tipo di `seq<'T>`, che è un alias per <xref:System.Collections.Generic.IEnumerable%601>. Pertanto, qualsiasi tipo .NET che implementa <xref:System.Collections.Generic.IEnumerable%601> interfaccia può essere utilizzato come sequenza. Il [modulo Seq](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) fornisce supporto per le modifiche che coinvolgono sequenze.

## <a name="sequence-expressions"></a>Espressioni di sequenza

Un' *espressione di sequenza* è un'espressione che restituisce una sequenza. Le espressioni di sequenza possono assumere un certo numero di form. Il formato più semplice specifica un intervallo. Ad esempio, `seq { 1 .. 5 }` crea una sequenza che contiene cinque elementi, inclusi gli endpoint 1 e 5. È anche possibile specificare un incremento (o decremento) tra due punti doppi. Il codice seguente, ad esempio, crea la sequenza di multipli di 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Le espressioni di sequenza sono costituite da F# espressioni che producono valori della sequenza. È anche possibile generare valori a livello di codice:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

Nell'esempio precedente viene usato l'operatore `->`, che consente di specificare un'espressione il cui valore diventerà parte della sequenza. È possibile usare solo `->` se ogni parte del codice che segue restituisce un valore.

In alternativa, è possibile specificare la parola chiave `do` con un `yield` facoltativo che segue:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Il codice seguente genera un elenco di coppie di coordinate insieme a un indice in una matrice che rappresenta la griglia. Si noti che la prima espressione `for` richiede la specifica di un `do`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Un'espressione `if` utilizzata in una sequenza è un filtro. Ad esempio, per generare una sequenza di soli numeri primi, supponendo di avere una funzione `isprime` di tipo `int -> bool`, costruire la sequenza come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Come indicato in precedenza, `do` è necessario in questo caso, perché non esiste un ramo `else` che viene utilizzato con il `if`. Se si tenta di usare `->`, viene restituito un errore che informa che non tutti i rami restituiscono un valore.

## <a name="the-yield-keyword"></a>Parola chiave `yield!`

In alcuni casi può essere utile includere una sequenza di elementi in un'altra sequenza. Per includere una sequenza in un'altra sequenza, è necessario usare la parola chiave `yield!`:

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

Un altro modo per considerare `yield!` è che rende flat una sequenza interna e quindi lo include nella sequenza che lo contiene.

Quando si usa `yield!` in un'espressione, tutti gli altri valori singoli devono usare la parola chiave `yield`:

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

Se si specifica solo `x` nell'esempio precedente, la sequenza non genera alcun valore.

## <a name="examples"></a>Esempi

Nel primo esempio viene utilizzata un'espressione di sequenza contenente un'iterazione, un filtro e un yield per generare una matrice. Questo codice stampa una sequenza di numeri primi compresi tra 1 e 100 nella console.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

Nell'esempio seguente viene creata una tabella di moltiplicazione costituita da tuple di tre elementi, ognuno costituito da due fattori e dal prodotto:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

Nell'esempio seguente viene illustrato l'utilizzo di `yield!` per combinare singole sequenze in un'unica sequenza finale. In questo caso, le sequenze per ogni sottoalbero in un albero binario vengono concatenate in una funzione ricorsiva per produrre la sequenza finale.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>Utilizzo di sequenze

Le sequenze supportano molte delle stesse funzioni degli [elenchi](lists.md). Le sequenze supportano anche operazioni quali il raggruppamento e il conteggio tramite funzioni di generazione di chiavi. Le sequenze supportano anche funzioni più diverse per l'estrazione di sottosequenze.

Molti tipi di dati, ad esempio elenchi, matrici, set e mappe, sono sequenze implicite perché sono raccolte enumerabili. Una funzione che accetta una sequenza come argomento funziona con uno qualsiasi dei tipi di F# dati comuni, oltre a qualsiasi tipo di dati .NET che implementa `System.Collections.Generic.IEnumerable<'T>`. A differenza di una funzione che accetta un elenco come argomento, che può solo prendere elenchi. Il tipo `seq<'T>` è un'abbreviazione di tipo per `IEnumerable<'T>`. Ciò significa che qualsiasi tipo che implementa l'`System.Collections.Generic.IEnumerable<'T>`generica, che include matrici, elenchi, set e mappe in F#e anche la maggior parte dei tipi di raccolte .NET, è compatibile con il tipo di `seq` e può essere usato ovunque sia prevista una sequenza.

## <a name="module-functions"></a>Funzioni di modulo

Il [modulo Seq](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) nello [spazio dei nomi Microsoft. FSharp. Collections](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) contiene funzioni per l'utilizzo delle sequenze. Queste funzioni funzionano anche con elenchi, matrici, mappe e set, perché tutti questi tipi sono enumerabili e pertanto possono essere considerati come sequenze.

## <a name="creating-sequences"></a>Creazione di sequenze

È possibile creare sequenze usando espressioni di sequenza, come descritto in precedenza, oppure usando determinate funzioni.

È possibile creare una sequenza vuota utilizzando [Seq. Empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59)oppure è possibile creare una sequenza di un solo elemento specificato utilizzando [Seq. Singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

È possibile utilizzare [Seq. init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) per creare una sequenza per la quale gli elementi vengono creati utilizzando una funzione fornita dall'utente. È anche possibile specificare una dimensione per la sequenza. Questa funzione è analoga a [List. init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), ad eccezione del fatto che gli elementi non vengono creati fino a quando non si scorre la sequenza. Il codice seguente illustra l'uso di `Seq.init`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

L'output è

```console
0 10 20 30 40
```

Utilizzando la funzione [Seq. ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) e [Seq.&#60;ofList&#62; t](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), è possibile creare sequenze da matrici ed elenchi. Tuttavia, è anche possibile convertire matrici ed elenchi in sequenze utilizzando un operatore cast. Entrambe le tecniche sono illustrate nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

Utilizzando [Seq. Cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), è possibile creare una sequenza da una raccolta con tipizzazione debole, ad esempio quelle definite in `System.Collections`. Tali raccolte con tipizzazione debole hanno il tipo di elemento `System.Object` e vengono enumerate usando il tipo di `System.Collections.Generic.IEnumerable&#96;1` non generico. Il codice seguente illustra l'uso di `Seq.cast` per convertire una `System.Collections.ArrayList` in una sequenza.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

È possibile definire sequenze infinite usando la funzione [Seq. initInfinite (](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) . Per una sequenza di questo tipo, è necessario fornire una funzione che genera ogni elemento dall'indice dell'elemento. Sono possibili sequenze infinite a causa della valutazione lazy; gli elementi vengono creati in base alle esigenze chiamando la funzione specificata. Nell'esempio di codice seguente viene prodotta una sequenza infinita di numeri a virgola mobile, in questo caso la serie alternata di reciproci di quadrati di interi consecutivi.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq. unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) genera una sequenza da una funzione di calcolo che accetta uno stato e la trasforma per produrre ogni elemento successivo nella sequenza. Lo stato è solo un valore utilizzato per calcolare ogni elemento e può essere modificato quando ogni elemento viene calcolato. Il secondo argomento per `Seq.unfold` è il valore iniziale utilizzato per avviare la sequenza. `Seq.unfold` usa un tipo di opzione per lo stato, che consente di terminare la sequenza restituendo il valore di `None`. Nel codice seguente vengono illustrati due esempi di sequenze, `seq1` e `fib`, generati da un'operazione `unfold`. Il primo, `seq1`, è semplicemente una sequenza semplice con numeri fino a 20. Il secondo `fib`utilizza `unfold` per calcolare la sequenza di Fibonacci. Poiché ogni elemento nella sequenza di Fibonacci è la somma dei due numeri di Fibonacci precedenti, il valore di stato è una tupla costituita dai due numeri precedenti nella sequenza. Il valore iniziale è `(1,1)`, i primi due numeri nella sequenza.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

L'output è indicato di seguito:

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Il codice seguente è un esempio che usa molte delle funzioni del modulo Sequence descritte qui per generare e calcolare i valori delle sequenze infinite. L'esecuzione del codice potrebbe richiedere alcuni minuti.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>Ricerca e ricerca di elementi

Le sequenze supportano la funzionalità disponibile con gli elenchi: [Seq. Exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq. exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq. Find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq. FindIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [Seq. pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq. tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47)e [Seq. tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Le versioni di queste funzioni disponibili per le sequenze valutano la sequenza solo fino all'elemento in cui viene eseguita la ricerca. Per esempi, vedere gli [elenchi](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).

## <a name="obtaining-subsequences"></a>Acquisizione di sottosequenze

[Seq. Filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) e [Seq. Choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) sono simili alle funzioni corrispondenti disponibili per gli elenchi, tranne per il fatto che il filtro e la scelta non vengono eseguiti fino a quando non vengono valutati gli elementi della sequenza.

[Seq. Truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) crea una sequenza da un'altra sequenza, ma limita la sequenza a un numero specificato di elementi. [Seq. Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) crea una nuova sequenza che contiene solo un numero specificato di elementi dall'inizio di una sequenza. Se nella sequenza sono presenti meno elementi di quelli specificati, `Seq.take` genera un'`System.InvalidOperationException`. La differenza tra `Seq.take` e `Seq.truncate` è che `Seq.truncate` non genera un errore se il numero di elementi è inferiore al numero specificato.

Il codice seguente illustra il comportamento di e le differenze tra `Seq.truncate` e `Seq.take`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

L'output, prima che si verifichi l'errore, è il seguente.

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

Utilizzando [Seq. TakeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), è possibile specificare una funzione di predicato (funzione booleana) e creare una sequenza da un'altra sequenza costituita dagli elementi della sequenza originale per cui il predicato è `true`, ma si arresta prima del primo elemento per il predicato restituisce `false`. [Seq. Skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) restituisce una sequenza che ignora un numero specificato di primi elementi di un'altra sequenza e restituisce gli elementi rimanenti. [Seq. SkipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) restituisce una sequenza che ignora i primi elementi di un'altra sequenza purché il predicato restituisca `true`e quindi restituisce gli elementi rimanenti, a partire dal primo elemento per il quale il predicato restituisce `false`.

Nell'esempio di codice seguente viene illustrato il comportamento di e le differenze tra `Seq.takeWhile`, `Seq.skip`e `Seq.skipWhile`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

L'output è indicato di seguito.

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Trasformazione di sequenze

[Seq. pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) crea una nuova sequenza in cui gli elementi successivi della sequenza di input vengono raggruppati in Tuple.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq. windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) è come `Seq.pairwise`, ad eccezione del fatto che anziché produrre una sequenza di tuple, produce una sequenza di matrici che contengono copie di elementi adiacenti (una *finestra*) dalla sequenza. È possibile specificare il numero di elementi adiacenti che si desidera includere in ogni matrice.

L'esempio di codice seguente illustra l'uso di `Seq.windowed`. In questo caso il numero di elementi nella finestra è 3. Nell'esempio viene usato `printSeq`, definito nell'esempio di codice precedente.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

L'output è indicato di seguito.

Sequenza iniziale:

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Operazioni con più sequenze

[Seq. zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) e [Seq. zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) accettano due o tre sequenze e producono una sequenza di Tuple. Queste funzioni sono simili alle funzioni corrispondenti disponibili per gli [elenchi](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d). Non esiste alcuna funzionalità corrispondente per separare una sequenza in due o più sequenze. Se questa funzionalità è necessaria per una sequenza, convertire la sequenza in un elenco e usare [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).

## <a name="sorting-comparing-and-grouping"></a>Ordinamento, confronto e raggruppamento

Le funzioni di ordinamento supportate per gli elenchi funzionano anche con le sequenze. Sono inclusi [Seq. Sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) e [Seq. sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f). Queste funzioni eseguono l'iterazione dell'intera sequenza.

Per confrontare due sequenze, utilizzare la funzione [Seq. compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) . La funzione Confronta gli elementi successivi a sua volta e si interrompe quando rileva la prima coppia diversa. Eventuali elementi aggiuntivi non contribuiscono al confronto.

Il codice seguente illustra l'uso di `Seq.compareWith`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

Nel codice precedente viene calcolato ed esaminato solo il primo elemento e il risultato è-1.

[Seq. countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) accetta una funzione che genera un valore denominato *chiave* per ogni elemento. Viene generata una chiave per ogni elemento chiamando questa funzione su ogni elemento. `Seq.countBy` restituisce quindi una sequenza che contiene i valori di chiave e un conteggio del numero di elementi che hanno generato ogni valore della chiave.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

L'output è indicato di seguito.

```console
(1, 34) (2, 33) (0, 33)
```

L'output precedente mostra che sono presenti 34 elementi della sequenza originale che hanno prodotto la chiave 1, 33 valori che hanno prodotto la chiave 2 e 33 valori che hanno prodotto la chiave 0.

È possibile raggruppare gli elementi di una sequenza chiamando [Seq. GroupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd). `Seq.groupBy` accetta una sequenza e una funzione che genera una chiave da un elemento. La funzione viene eseguita su ogni elemento della sequenza. `Seq.groupBy` restituisce una sequenza di tuple, in cui il primo elemento di ogni tupla è la chiave e la seconda è una sequenza di elementi che producono tale chiave.

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di `Seq.groupBy` per partizionare la sequenza di numeri da 1 a 100 in tre gruppi con i valori di chiave DISTINCT 0, 1 e 2.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

L'output è indicato di seguito.

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

È possibile creare una sequenza che elimini gli elementi duplicati chiamando [Seq. Distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401). In alternativa, è possibile usare [Seq. distinctBy (](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), che accetta una funzione di generazione delle chiavi da chiamare su ogni elemento. La sequenza risultante contiene elementi della sequenza originale con chiavi univoche. gli elementi successivi che producono una chiave duplicata per un elemento precedente vengono eliminati.

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di `Seq.distinct`. `Seq.distinct` viene dimostrato generando sequenze che rappresentano numeri binari e quindi mostrando che gli unici elementi distinti sono 0 e 1.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

Il codice seguente illustra `Seq.distinctBy` iniziando con una sequenza che contiene numeri negativi e positivi e usando la funzione valore assoluto come funzione di generazione delle chiavi. Nella sequenza risultante mancano tutti i numeri positivi che corrispondono ai numeri negativi nella sequenza, perché i numeri negativi vengono visualizzati in precedenza nella sequenza e pertanto vengono selezionati al posto dei numeri positivi con lo stesso valore assoluto valore o chiave.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>Sequenze di sola lettura e memorizzate nella cache

[Seq. ReadOnly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) crea una copia di sola lettura di una sequenza. `Seq.readonly` è utile quando si dispone di una raccolta di lettura/scrittura, ad esempio una matrice, e non si desidera modificare la raccolta originale. Questa funzione può essere utilizzata per mantenere incapsulamento dei dati. Nell'esempio di codice seguente viene creato un tipo che contiene una matrice. Una proprietà espone la matrice, ma anziché restituire una matrice, restituisce una sequenza creata dalla matrice utilizzando `Seq.readonly`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) crea una versione archiviata di una sequenza. Utilizzare `Seq.cache` per evitare la rivalutazione di una sequenza o quando si dispone di più thread che utilizzano una sequenza, ma è necessario assicurarsi che ogni elemento venga eseguito una sola volta. Quando si dispone di una sequenza utilizzata da più thread, è possibile avere un thread che enumera e calcola i valori per la sequenza originale e i thread rimanenti possono utilizzare la sequenza memorizzata nella cache.

## <a name="performing-computations-on-sequences"></a>Esecuzione di calcoli sulle sequenze

Le operazioni aritmetiche semplici sono simili a quelle degli elenchi, ad esempio [Seq. Average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq. Sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq. averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq. sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)e così via.

[Seq. fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq. reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9)e [Seq. Scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) sono simili alle funzioni corrispondenti disponibili per gli elenchi. Le sequenze supportano un subset delle varianti complete di queste funzioni che elenca il supporto. Per ulteriori informazioni ed esempi, vedere la pagina relativa agli [elenchi](lists.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Tipi F#](fsharp-types.md)
