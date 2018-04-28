---
title: Sequenze (F#)
description: 'Informazioni su come usare le sequenze di F #, quando si dispone di grandi dimensioni, raccolta ordinata di dati, ma non necessariamente prevede di utilizzare tutti gli elementi.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: a3521037112d40998ed00cd6fed376882c2f2c88
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="sequences"></a>Sequenze

> [!NOTE]
I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Oggetto *sequenza* è una serie logica di elementi dello stesso tipo. Le sequenze sono particolarmente utili quando si dispone di grandi dimensioni, raccolta ordinata di dati, ma non necessariamente prevede di utilizzare tutti gli elementi. Sequenza di singoli elementi vengono calcolati solo se necessario, una sequenza può offrire prestazioni migliori rispetto a un elenco in situazioni in cui non vengono utilizzati tutti gli elementi. Le sequenze vengono rappresentate dal `seq<'T>` tipo, ovvero un alias per `System.Collections.Generic.IEnumerable`. Pertanto, qualsiasi tipo di .NET Framework che implementa `System.IEnumerable` può essere utilizzato come una sequenza. Il [Seq (modulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) fornisce il supporto per le modifiche che coinvolgono le sequenze.

## <a name="sequence-expressions"></a>Espressioni di sequenza
Oggetto *sequenza espressione* è un'espressione che restituisce una sequenza. Le espressioni di sequenza possono accettare un numero di moduli. La forma più semplice specifica un intervallo. Ad esempio, `seq { 1 .. 5 }` crea una sequenza che contiene cinque elementi, inclusi gli endpoint 1 e 5. Può anche specificare un incremento o decremento tra due punti doppio. Il codice seguente crea ad esempio, la sequenza di multipli di 10.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Le espressioni di sequenza sono costituite da espressioni F # che producono valori della sequenza. È possibile utilizzare il `yield` (parola chiave) per produrre valori diventano parte della sequenza.

Ecco un esempio.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

È possibile utilizzare il `->` operatore anziché `yield`, nel qual caso è possibile omettere il `do` (parola chiave), come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Il codice seguente genera un elenco di coppie di coordinate insieme a un indice in una matrice che rappresenta la griglia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Un `if` espressione utilizzata in una sequenza è un filtro. Ad esempio, per generare una sequenza di soli numeri primi, presupponendo che si disponga di una funzione `isprime` di tipo `int -> bool`, costruire la sequenza come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Quando si utilizza `yield` o `->` in un'iterazione, ogni iterazione dovrebbe generare un singolo elemento della sequenza. Se ogni iterazione produce una sequenza di elementi, utilizzare `yield!`. In tal caso, gli elementi generati in ogni iterazione vengono concatenati per produrre la sequenza finale.

È possibile combinare più espressioni in un'espressione sequenza. Gli elementi generati da ogni espressione vengono concatenati. Per un esempio, vedere la sezione "Esempi" di questo argomento.

## <a name="examples"></a>Esempi
Il primo esempio viene utilizzata un'espressione di sequenza che contiene un rendimento per generare una matrice, un filtro e un'iterazione. Questo codice consente di stampare una sequenza di numeri primi compreso tra 1 e 100 nella console.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

Il codice seguente usa `yield` per creare una tabella di moltiplicazione che è costituito da tuple di tre elementi, ciascuno costituito da due fattori e il prodotto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

Nell'esempio seguente viene illustrato l'utilizzo di `yield!` per combinare singole sequenze in un'unica sequenza finale. In questo caso, le sequenze per ogni sottoalbero in un albero binario vengono concatenate in una funzione ricorsiva per produrre la sequenza finale.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]
    
## <a name="using-sequences"></a>Utilizzo di sequenze
Le sequenze supportano molte delle stesse funzioni [Elenca](lists.md). Sequenze supportano anche le operazioni, ad esempio il raggruppamento e il conteggio utilizzando funzioni di generazione di chiavi. Le sequenze supportano anche le funzioni più diverse per l'estrazione di sottosequenze.

Molti tipi di dati, ad esempio elenchi, matrici, set e mappe in modo implicito sono sequenze perché sono raccolte enumerabili. Una funzione che accetta una sequenza come un argomento funziona con qualsiasi di F # tipi di dati, oltre a qualsiasi tipo di dati .NET Framework che implementa `System.Collections.Generic.IEnumerable<'T>`. Diversamente da una funzione che accetta un elenco come argomento, che può accettare solo gli elenchi. Il tipo `seq<'T>` è un'abbreviazione di tipo per `IEnumerable<'T>`. Ciò significa che qualsiasi tipo che implementa l'interfaccia generica `System.Collections.Generic.IEnumerable<'T>`, che include matrici, elenchi, set e mappe in F # e la maggior parte dei tipi di raccolte .NET Framework, è compatibile con il `seq` digitare e possono essere utilizzati ovunque sia prevista una sequenza.


## <a name="module-functions"></a>Funzioni di modulo
Il [Seq (modulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) nel [dello spazio dei nomi Collections](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) include funzioni per l'utilizzo delle sequenze. Queste funzioni con elenchi, matrici, mappe e set nonché, perché tutti i tipi sono enumerabili e pertanto possono essere considerati come una sequenza.


## <a name="creating-sequences"></a>Creazione di sequenze
È possibile creare sequenze utilizzando espressioni di sequenza, come descritto in precedenza o con determinate funzioni.

È possibile creare una sequenza vuota usando [Seq. Empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), oppure è possibile creare una sequenza di un solo elemento specificato utilizzando [SEQ](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

È possibile utilizzare [SEQ](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) per creare una sequenza per cui gli elementi vengono creati utilizzando una funzione specificata dall'utente. È inoltre possibile specificare una dimensione per la sequenza. Questa funzione è analoga [init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), ad eccezione del fatto che gli elementi non vengono creati finché non si scorre la sequenza. Il codice seguente viene illustrato l'utilizzo di `Seq.init`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

L'output è

```
0 10 20 30 40
```

Utilizzando [ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) e [ofList&#60;|&#62; funzione](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), è possibile creare sequenze di matrici ed elenchi. Tuttavia, è possibile inoltre convertire matrici ed elenchi sequenze tramite un operatore cast. Nel codice seguente sono illustrate due tecniche.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

Utilizzando [SEQ](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), è possibile creare una sequenza da una raccolta di tipizzazione, ad esempio quelle definite `System.Collections`. Tali raccolte tipizzazione includono il tipo di elemento `System.Object` e vengono enumerati utilizzando il tipo non generico `System.Collections.Generic.IEnumerable&#96;1` tipo. Il codice seguente viene illustrato l'utilizzo di `Seq.cast` per convertire un `System.Collections.ArrayList` in una sequenza.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

È possibile definire sequenze infinite tramite il [initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) (funzione). Per una sequenza, si fornisce una funzione che genera ogni elemento tra l'indice dell'elemento. Sono possibili sequenze infinite a causa di valutazione lazy; gli elementi vengono creati in base alle esigenze chiamando la funzione specificato. Esempio di codice seguente produce una sequenza infinita di numeri a virgola mobile, in questo caso la serie alternativo di reciproci di quadrati di numeri interi consecutivi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq. unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) genera una sequenza da una funzione di calcolo che accetta uno stato e lo trasforma per produrre ogni elemento successivo nella sequenza. Lo stato è semplicemente un valore che viene utilizzato per calcolare ogni elemento e può essere modificato da ogni elemento viene calcolata. Il secondo argomento `Seq.unfold` è il valore iniziale viene utilizzato per avviare la sequenza. `Seq.unfold` utilizza un tipo di opzione per lo stato, che consente di terminare la sequenza restituendo il `None` valore. Il codice seguente mostra due esempi di sequenze, `seq1` e `fib`, che vengono generati da un `unfold` operazione. Il primo, `seq1`, è una semplice sequenza con numeri fino a 100. Il secondo, `fib`, utilizza `unfold` per calcolare la sequenza di Fibonacci. Poiché ogni elemento nella sequenza di Fibonacci è la somma di due numeri di Fibonacci precedenti, il valore di stato è una tupla costituita da due numeri precedenti nella sequenza. Il valore iniziale è `(1,1)`, i primi due numeri nella sequenza.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

L'output è indicato di seguito:

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Il codice riportato di seguito è riportato un esempio che utilizza molte delle funzioni di modulo sequenza descritte di seguito per generare e calcolare i valori delle sequenze infinite. Il codice potrebbe richiedere alcuni minuti per l'esecuzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]
    
## <a name="searching-and-finding-elements"></a>Ricerca e ricerca di elementi
Sequenze supportano le funzionalità disponibili con gli elenchi: [SEQ](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [SEQ](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [ Seq. pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), e [tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Le versioni di queste funzioni sono disponibili per le sequenze di valutano la sequenza solo fino all'elemento che si sta cercando. Per esempi, vedere [Elenca](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).


## <a name="obtaining-subsequences"></a>Acquisizione di sottosequenze
[Seq. Filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) e [SEQ](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) sono analoghi alle funzioni corrispondenti che sono disponibili per gli elenchi, ad eccezione del fatto che i filtri e la scelta non vengano eseguite fino a quando non vengono valutati gli elementi della sequenza.

[Seq. truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) crea una sequenza da un'altra sequenza, ma limita la sequenza a un numero specificato di elementi. [Seq. Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) crea una nuova sequenza che contiene solo un numero specificato di elementi dall'inizio di una sequenza. Se esistono meno elementi nella sequenza di maggiore di quello specificato per richiedere, `Seq.take` genera un `System.InvalidOperationException`. La differenza tra `Seq.take` e `Seq.truncate` che `Seq.truncate` non produce un errore se il numero di elementi è inferiore al numero specificato.

Il codice seguente viene illustrato il comportamento di e le differenze tra `Seq.truncate` e `Seq.take`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

L'output, prima che si verifichi l'errore, è come indicato di seguito.

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

Utilizzando [TakeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), è possibile specificare una funzione di predicato (una funzione booleana) e creare una sequenza da un'altra sequenza costituita dagli elementi della sequenza originale per cui il predicato è `true`, ma arrestare prima del primo elemento per cui il predicato restituisce `false`. [Seq. Skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) restituisce una sequenza che ignora un numero specificato dei primi elementi di un'altra sequenza e restituisce gli elementi rimanenti. [Seq. SkipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) restituisce una sequenza che ignora i primi elementi di un'altra sequenza, purché il predicato restituisce `true`e quindi restituisce gli elementi rimanenti, a partire dal primo elemento per cui il predicato restituisce `false`.

Esempio di codice seguente viene illustrato il comportamento di e le differenze tra `Seq.takeWhile`, `Seq.skip`, e `Seq.skipWhile`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

L'output è indicato di seguito.

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Trasformazione di sequenze
[Seq. pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) crea una nuova sequenza in cui gli elementi successivi della sequenza di input vengono raggruppati in tuple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq. windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) è simile a `Seq.pairwise`, ad eccezione del fatto che, invece che produce una sequenza di tuple, produce una sequenza di matrici che contengono copie di elementi adiacenti (un *finestra*) dalla sequenza. Specificare il numero di elementi adiacenti che desidera che in ogni matrice.

L'esempio di codice seguente illustra l'uso di `Seq.windowed`. In questo caso, il numero di elementi nella finestra è 3. Nell'esempio viene utilizzato `printSeq`, definito nell'esempio di codice precedente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

L'output è indicato di seguito.

Sequenza iniziale:

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Operazioni con più sequenze
[Seq. zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) e [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) accetta due o tre sequenze e genera una sequenza di tuple. Queste funzioni sono simili alle funzioni corrispondenti disponibili per [Elenca](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d). Non sussiste alcuna funzionalità corrispondente per separare una sequenza in due o più sequenze. Se questa funzionalità è necessaria per una sequenza, la sequenza convertita in un elenco e utilizzare [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).


## <a name="sorting-comparing-and-grouping"></a>Ordinamento, confronto e raggruppamento
Le funzioni di ordinamento supportate per elenchi funzionano anche con le sequenze. Ciò include [SEQ](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) e [sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f). Queste funzioni di scorrere l'intera sequenza.

È possibile confrontare due sequenze tramite la [compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) (funzione). La funzione Confronta gli elementi successivi a sua volta e si arresta quando viene rilevato la prima coppia uguali. Eventuali elementi aggiuntivi non contribuiscono al confronto.

Il codice seguente illustra l'uso di `Seq.compareWith`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

Nel codice precedente, solo il primo elemento è calcolato ed esaminato e il risultato è -1.

[Seq. countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) accetta una funzione che genera un valore denominato un *chiave* per ogni elemento. Chiamare questa funzione su ogni elemento, viene generata una chiave per ogni elemento. `Seq.countBy` Restituisce quindi una sequenza che contiene i valori di chiave e un conteggio del numero di elementi che ha generato ogni valore della chiave.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

L'output è indicato di seguito.

```
(1, 34) (2, 33) (0, 33)
```

L'output precedente mostra che non vi sono 34 elementi della sequenza originale che ha generato la chiave 1, 33 valori che ha generato la chiave 2 e 33 valori che ha generato il tasto 0.

È possibile raggruppare gli elementi di una sequenza chiamando [GroupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd). `Seq.groupBy` accetta una sequenza e una funzione che genera una chiave da un elemento. La funzione viene eseguita su ogni elemento della sequenza. `Seq.groupBy` Restituisce una sequenza di tuple, dove il primo elemento di ogni tupla è la chiave e il secondo è una sequenza di elementi che producono la chiave.

Esempio di codice seguente viene illustrato l'utilizzo di `Seq.groupBy` per partizionare la sequenza di numeri da 1 a 100 in tre gruppi di valori di chiave distinct 0, 1 e 2.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

L'output è indicato di seguito.

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

È possibile creare una sequenza che elimina gli elementi duplicati chiamando [SEQ](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401). Oppure è possibile utilizzare [distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), che accetta una funzione di generazione chiavi a essere chiamato su ogni elemento. La sequenza risulta contiene elementi della sequenza originale che dispongono di chiavi univoche. vengono rimossi gli elementi successivi che producono una chiave duplicata per un elemento precedente.

Esempio di codice seguente viene illustrato l'utilizzo di `Seq.distinct`. `Seq.distinct` viene dimostrata la generazione delle sequenze che rappresentano numeri binari e quindi che mostrano che gli elementi distinti solo 0 e 1.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

Il codice seguente illustra `Seq.distinctBy` a partire da una sequenza che contiene i numeri positivi e negativi e utilizzando la funzione di valore assoluto come la funzione di generazione di chiavi. La sequenza risultante non contiene tutti i numeri positivi che corrispondono ai numeri negativi in sequenza, perché i numeri negativi vengono visualizzati prima nella sequenza e vengono pertanto selezionati anziché i numeri positivi che hanno la stessa assoluto valore o chiave.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]
    
## <a name="readonly-and-cached-sequences"></a>Sola lettura e memorizzata nella cache delle sequenze
[Seq. ReadOnly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) crea una copia di sola lettura di una sequenza. `Seq.readonly` è utile quando si dispone di una raccolta di lettura / scrittura, ad esempio una matrice, e non si desidera modificare la raccolta originale. Questa funzione può essere utilizzata per mantenere l'incapsulamento dei dati. Nell'esempio di codice seguente viene creato un tipo che contiene una matrice. Una proprietà espone la matrice, ma anziché restituire una matrice, restituisce una sequenza che viene creata dalla matrice utilizzando `Seq.readonly`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) crea una versione archiviata di una sequenza. Utilizzare `Seq.cache` per evitare la rivalutazione di una sequenza o quando si dispone di più thread che utilizzano una sequenza, ma è necessario assicurarsi che ogni elemento viene utilizzata solo una volta. Quando si dispone di una sequenza che è utilizzata da più thread, è possibile disporre di un thread che enumera e calcola i valori per la sequenza originale e thread rimanenti possono utilizzare la sequenza memorizzati nella cache.


## <a name="performing-computations-on-sequences"></a>Esecuzione di calcoli sulle sequenze
Semplici operazioni aritmetiche sono analoghe a quelle di elenchi, ad esempio [Seq. Average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)e così via.

[Seq. fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), e [SEQ](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) sono analoghi alle funzioni corrispondenti che sono disponibili per gli elenchi. Le sequenze supportano un subset delle variazioni di queste funzioni complete che elenca il supporto. Per ulteriori informazioni ed esempi, vedere [Elenca](lists.md).

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Tipi F#](fsharp-types.md)
