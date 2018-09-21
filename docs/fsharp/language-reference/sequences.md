---
title: Sequenze (F#)
description: 'Informazioni su come usare le sequenze di F #, quando si hanno grandi dimensioni, raccolta ordinata di dati, ma non necessariamente prevediate di usare tutti gli elementi.'
ms.date: 05/16/2016
ms.openlocfilehash: cfe8d1e350a8ac46b7700c12aa84d250f8b35855
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532386"
---
# <a name="sequences"></a>Sequenze

> [!NOTE]
I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Oggetto *sequenza* è una serie logica di elementi dello stesso tipo. Le sequenze sono particolarmente utili quando si hanno grandi dimensioni, raccolta ordinata di dati, ma non necessariamente prevede di usare tutti gli elementi. Sequenza di singoli elementi vengono calcolati solo se necessario e quindi una sequenza può fornire prestazioni migliori rispetto a un elenco in situazioni in cui non vengono usati tutti gli elementi. Le sequenze sono rappresentate dal `seq<'T>` tipo, che è un alias per `System.Collections.Generic.IEnumerable`. Pertanto, qualsiasi tipo .NET Framework che implementa `System.IEnumerable` può essere usato come una sequenza. Il [Seq (modulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) fornisce il supporto per le modifiche che coinvolgono le sequenze.

## <a name="sequence-expressions"></a>Espressioni di sequenza

Oggetto *espressioni di sequenza* è un'espressione che restituisce una sequenza. Espressioni di sequenza possono richiedere diversi formati. La forma più semplice specifica un intervallo. Ad esempio, `seq { 1 .. 5 }` crea una sequenza che contiene cinque elementi, inclusi gli endpoint 1 e 5. È possibile anche specificare un incremento (o diminuire) tra due punti doppio. Ad esempio, il codice seguente crea la sequenza di multipli pari a 10.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Espressioni di sequenza sono costituite da espressioni F # che producono valori della sequenza. È possibile usare il `yield` (parola chiave) per produrre valori diventano parte della sequenza.

Di seguito è riportato un esempio.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

È possibile usare la `->` invece dell'operatore `yield`, nel qual caso è possibile omettere il `do` (parola chiave), come illustrato nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Il codice seguente genera un elenco di coppie di coordinate insieme a un indice in una matrice che rappresenta la griglia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Un `if` espressione utilizzata in una sequenza è un filtro. Ad esempio, per generare una sequenza dei soli numeri primi, presupponendo che si disponga di una funzione `isprime` di tipo `int -> bool`, costruire la sequenza come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Quando si usa `yield` o `->` in un'iterazione, si dovrà generare un singolo elemento della sequenza di ogni iterazione. Se ogni iterazione produce una sequenza di elementi, usare `yield!`. In tal caso, gli elementi generati in ogni iterazione vengono concatenati per produrre la sequenza finale.

È possibile combinare più espressioni in un'espressione di sequenza. Gli elementi generati da ogni espressione vengono concatenati tra loro. Per un esempio, vedere la sezione "Esempi" di questo argomento.

## <a name="examples"></a>Esempi

Il primo esempio Usa un'espressione di sequenza che contiene una parola chiave yield per generare una matrice, un filtro e un'iterazione. Questo codice visualizza una sequenza di numeri primi compreso tra 1 e 100 nella console.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

Il codice seguente usa `yield` per creare una tabella di moltiplicazione che è costituito da tuple di tre elementi, ognuno costituito da due fattori e il prodotto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

L'esempio seguente illustra l'uso di `yield!` combinare singoli sequenze in un'unica sequenza finale. In questo caso, le sequenze per ogni sottoalbero in un albero binario vengono concatenate in una funzione ricorsiva per produrre la sequenza finale.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>Utilizzo di sequenze

Le sequenze supportano molte funzioni analoghe come [Elenca](lists.md). Le sequenze supportano anche operazioni come il raggruppamento e il conteggio usando funzioni di generazione chiavi. Le sequenze di supportano anche maggiori sono funzioni per l'estrazione di sottosequenze.

Molti tipi di dati, ad esempio elenchi, matrici, set e le mappe sono implicitamente sequenze perché sono raccolte enumerabili. Una funzione che accetta una sequenza come un argomento funziona con una qualsiasi di F # tipi di dati comuni, oltre a qualsiasi tipo di dati .NET Framework che implementa `System.Collections.Generic.IEnumerable<'T>`. Questo va confrontato con una funzione che accetta un elenco come argomento, che può accettare solo gli elenchi. Il tipo `seq<'T>` è un'abbreviazione di tipo per `IEnumerable<'T>`. Ciò significa che qualsiasi tipo che implementa l'interfaccia generica `System.Collections.Generic.IEnumerable<'T>`, che include le matrici, elenchi, set e mappe in F # e la maggior parte dei tipi di raccolte .NET Framework, è compatibile con il `seq` digitare e possono essere utilizzati ovunque sia prevista una sequenza.

## <a name="module-functions"></a>Funzioni di modulo

Il [Seq (modulo)](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) nel [Microsoft.FSharp.Collections dello spazio dei nomi](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) contiene funzioni per l'utilizzo di sequenze. Queste funzioni usano gli elenchi, matrici, mappe e set, perché tutti questi tipi sono enumerable e pertanto possono essere considerati come una sequenza.

## <a name="creating-sequences"></a>Creazione di sequenze

È possibile creare sequenze utilizzando espressioni di sequenza, come descritto in precedenza o con determinate funzioni.

È possibile creare una sequenza vuota usando [SEQ](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), oppure è possibile creare una sequenza di un solo elemento specificato usando [SEQ](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

È possibile usare [SEQ](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) per creare una sequenza per il quale gli elementi vengono creati utilizzando una funzione specificata dall'utente. È inoltre possibile specificare una dimensione per la sequenza. Questa funzione è analoga a [init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), ad eccezione del fatto che gli elementi non vengono creati finché non si scorre la sequenza. Il codice seguente illustra l'uso di `Seq.init`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

L'output è

```
0 10 20 30 40
```

Usando [Seq. ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) e [ofList&#60;l&#62; funzioni](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), è possibile creare sequenze di matrici ed elenchi. Tuttavia, è possibile anche convertire matrici ed elenchi sequenze tramite un operatore cast. Entrambe le tecniche sono visualizzate nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

Usando [SEQ](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), è possibile creare una sequenza da una raccolta di tipizzazione debole, come quelle definite in `System.Collections`. Tali raccolte tipizzazione debole presentano il tipo di elemento `System.Object` e vengono enumerate utilizzando non generica `System.Collections.Generic.IEnumerable&#96;1` tipo. Il codice seguente illustra l'uso di `Seq.cast` per convertire un `System.Collections.ArrayList` in una sequenza.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

È possibile definire sequenze infinite usando il [Seq. initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) (funzione). Per una sequenza, viene fornita una funzione che genera ogni elemento dall'indice dell'elemento. Sono consentite sequenze infinite grazie al evaluation lazy; gli elementi vengono creati in base alle esigenze chiamando la funzione specificata. Esempio di codice seguente produce una sequenza di numeri a virgola mobile, in questo caso la serie alternata di reciproci di quadrati di numeri interi consecutivi infinita.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq. unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) genera una sequenza da una funzione di calcolo che accetta uno stato e li trasforma in modo da generare ogni elemento successivo nella sequenza. Lo stato è semplicemente un valore viene usato per calcolare ogni elemento, che possono essere modificate come viene calcolato ogni elemento. Il secondo argomento `Seq.unfold` è il valore iniziale che consente di avviare la sequenza. `Seq.unfold` utilizza un tipo di opzione per lo stato, che consente di terminare la sequenza restituendo il `None` valore. Il codice seguente mostra due esempi di sequenze `seq1` e `fib`, che vengono generati da un `unfold` operazione. Il primo, `seq1`, è una semplice sequenza con i numeri fino a 100. La seconda `fib`, Usa `unfold` per calcolare la sequenza di Fibonacci. Poiché ogni elemento nella sequenza di Fibonacci è la somma dei due numeri di Fibonacci precedenti, il valore di stato è una tupla costituita da due numeri precedenti nella sequenza. Il valore iniziale è `(1,1)`, i primi due numeri nella sequenza.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

L'output è indicato di seguito:

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Il codice seguente è un esempio che usa molte delle funzioni del modulo sequenza descritte di seguito per generare e calcolare i valori delle sequenze infinite. Il codice potrebbe richiedere alcuni minuti per l'esecuzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>La ricerca e ricerca di elementi

Le sequenze di supportano le funzionalità disponibili con gli elenchi: [SEQ](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq. Find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq. findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [ Seq. pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq. tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), e [tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Le versioni di queste funzioni che sono disponibili per le sequenze di valutano la sequenza solo fino all'elemento che viene viene eseguita la ricerca. Per esempi, vedere [Elenca](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).

## <a name="obtaining-subsequences"></a>Acquisizione di sottosequenze

[Seq. Filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) e [SEQ](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) sono analoghi alle funzioni corrispondenti che sono disponibili per gli elenchi, ad eccezione del fatto che l'applicazione di filtri e scegliendo non vengano eseguite fino a quando non vengono valutati gli elementi della sequenza.

[Seq. truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) crea una sequenza da un'altra sequenza, ma limita la sequenza a un numero specificato di elementi. [Seq. Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) crea una nuova sequenza che contiene solo un numero specificato di elementi dall'inizio di una sequenza. Se esistono meno elementi nella sequenza di maggiore di quello specificato per sfruttare, `Seq.take` genera un `System.InvalidOperationException`. La differenza tra `Seq.take` e `Seq.truncate` è che `Seq.truncate` non produce un errore se il numero di elementi è inferiore al numero specificato.

Il codice seguente viene illustrato il comportamento di e le differenze tra `Seq.truncate` e `Seq.take`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

L'output, prima che si verifichi l'errore, è come indicato di seguito.

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

Usando [TakeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), è possibile specificare una funzione di predicato (una funzione booleana) e creare una sequenza da un'altra sequenza costituita dagli elementi della sequenza originale per il quale il predicato è `true`, ma arresta. prima del primo elemento per cui il predicato restituisce `false`. [Seq. Skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) restituisce una sequenza che ignora un determinato numero dei primi elementi di un'altra sequenza e restituisce gli elementi rimanenti. [Seq. SkipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) restituisce una sequenza che ignora i primi elementi di un'altra sequenza, purché il predicato restituisce `true`e quindi restituisce gli elementi rimanenti, a partire dal primo elemento per cui il predicato restituisce `false`.

Esempio di codice seguente illustra il comportamento della e le differenze tra `Seq.takeWhile`, `Seq.skip`, e `Seq.skipWhile`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

L'output è indicato di seguito.

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Trasformazione di sequenze

[Seq. pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) crea una nuova sequenza in cui vengono raggruppati in elementi successivi della sequenza di input inseriti in tuple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq. windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) è simile a `Seq.pairwise`, ad eccezione del fatto che, invece di produrre una sequenza di tuple, produce una sequenza di matrici che contengono copie degli elementi adiacenti (un *finestra*) dalla sequenza. Specificare il numero di elementi adiacenti che desidera che in ogni matrice.

L'esempio di codice seguente illustra l'uso di `Seq.windowed`. In questo caso il numero di elementi nella finestra è 3. L'esempio Usa `printSeq`, che viene definito nell'esempio di codice precedente.

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

[Seq. zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) e [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) utilizzano due o tre sequenze e producono una sequenza di tuple. Queste funzioni sono analoghe alle funzioni corrispondenti disponibile per [Elenca](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d). Non vi è alcuna funzionalità corrispondente per separare una sequenza in due o più sequenze. Se questa funzionalità è necessaria per una sequenza, la sequenza convertita in un elenco e utilizzare [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).

## <a name="sorting-comparing-and-grouping"></a>L'ordinamento, confronto e raggruppamento

Le funzioni di ordinamento supportate per gli elenchi funzionano anche con le sequenze. Sono inclusi [SEQ](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) e [sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f). Queste funzioni di scorrere l'intera sequenza.

È possibile confrontare due sequenze utilizzando il [Seq. compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) (funzione). La funzione Confronta gli elementi successivi a sua volta e si interrompe quando viene rilevato la prima coppia non equivalente rilevata. Eventuali elementi aggiuntivi non vengono conteggiati per il confronto.

Il codice seguente illustra l'uso di `Seq.compareWith`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

Nel codice precedente, viene calcolato ed esaminato solo il primo elemento e il risultato è -1.

[Seq. countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) accetta una funzione che genera un valore chiamato un' *chiave* per ogni elemento. Una chiave viene generata per ogni elemento chiamando questa funzione su ogni elemento. `Seq.countBy` quindi restituisce una sequenza che contiene i valori di chiave e un conteggio del numero di elementi che ha generato ogni valore della chiave.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

L'output è indicato di seguito.

```
(1, 34) (2, 33) (0, 33)
```

L'output precedente mostra che si sono verificati 34 elementi della sequenza originale che ha generato la chiave 1, 33 valori che ha generato la chiave 2 e 33 valori che ha generato la chiave di 0.

È possibile raggruppare gli elementi di una sequenza chiamando [GroupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd). `Seq.groupBy` accetta una sequenza e una funzione che genera una chiave da un elemento. La funzione viene eseguita su ogni elemento della sequenza. `Seq.groupBy` Restituisce una sequenza di tuple, dove il primo elemento di ogni tupla è la chiave e il secondo è una sequenza di elementi che generano tale chiave.

Esempio di codice seguente viene illustrato l'utilizzo di `Seq.groupBy` per partizionare la sequenza di numeri da 1 a 100 in tre gruppi che includono i valori di chiave distinti 0, 1 e 2.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

L'output è indicato di seguito.

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

È possibile creare una sequenza che consente di eliminare elementi duplicati chiamando [SEQ](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401). In alternativa è possibile usare [Seq. distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), che accetta una funzione di generazione chiavi a essere chiamato su ogni elemento. La sequenza risultante contiene gli elementi della sequenza originale con chiavi univoche. vengono rimossi gli elementi successivi che producono una chiave duplicata per un elemento precedente.

Esempio di codice seguente viene illustrato l'utilizzo di `Seq.distinct`. `Seq.distinct` viene illustrata la generazione delle sequenze che rappresentano numeri binari e quindi mostrando che gli elementi distinti solo sono 0 e 1.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

Il codice seguente illustra `Seq.distinctBy` inizia con una sequenza che contiene i numeri negativi e positivi e usando la funzione di valore assoluto della funzione di generazione chiavi. La sequenza risultante mancano tutti i numeri positivi che corrispondono ai numeri negativi in sequenza, in quanto i numeri negativi vengono visualizzati in precedenza nella sequenza e pertanto sono selezionati anziché i numeri positivi che hanno la stessa assoluto valore, o chiave.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>Sola lettura e memorizzata nella cache le sequenze

[Seq. ReadOnly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) crea una copia di sola lettura di una sequenza. `Seq.readonly` è utile quando si dispone di una raccolta di lettura / scrittura, ad esempio una matrice, e non si desidera modificare la raccolta originale. Questa funzione è utilizzabile per mantenere l'incapsulamento dei dati. Nell'esempio di codice seguente, viene creato un tipo che contiene una matrice. Matrice di espone una proprietà, ma invece di restituire una matrice, restituisce una sequenza che viene creata dalla matrice usando `Seq.readonly`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq. cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) crea una versione archiviata di una sequenza. Usare `Seq.cache` per evitare una nuova valutazione di una sequenza o quando si dispone di più thread che usa una sequenza, ma è necessario assicurarsi che ogni elemento viene utilizzata una sola volta. Quando si dispone di una sequenza che è usata da più thread, è possibile avere un solo thread che enumera e calcola i valori per la sequenza originale e thread rimanenti possono utilizzare la sequenza memorizzati nella cache.

## <a name="performing-computations-on-sequences"></a>Esecuzione di calcoli sulle sequenze

Semplici operazioni aritmetiche sono simili a quelli di elenchi, ad esempio [Seq. Average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [SEQ](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq. averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq. sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)e così via.

[Seq. fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), e [SEQ](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) sono analoghi alle funzioni corrispondenti che sono disponibili per gli elenchi. Le sequenze supportano un subset delle varianti complete di queste funzioni che elenca il supporto. Per altre informazioni ed esempi, vedere [Elenca](lists.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Tipi F#](fsharp-types.md)
