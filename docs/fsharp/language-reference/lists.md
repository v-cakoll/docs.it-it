---
title: Elenchi
description: Informazioni sugli F# elenchi, una serie ordinata e non modificabile di elementi dello stesso tipo.
ms.date: 05/16/2016
ms.openlocfilehash: 72f1779d7d077da0f1f4804df93fa4ac11f9b2e3
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082917"
---
# <a name="lists"></a>Elenchi

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Un elenco in F# è una serie ordinata e non modificabile di elementi dello stesso tipo. Per eseguire operazioni di base sugli elenchi, usare le funzioni nel [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).

## <a name="creating-and-initializing-lists"></a>Creazione e inizializzazione di elenchi

È possibile definire un elenco elencando in modo esplicito gli elementi, separati da punti e virgola e racchiusi tra parentesi quadre, come mostrato nella riga di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

È anche possibile inserire interruzioni di riga tra gli elementi e in questo caso i punti e virgola sono facoltativi. La sintassi precedente può agevolare la lettura del codice in caso di espressioni di inizializzazione degli elementi più lunghe o se si desidera includere un commento per ogni elemento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

In genere, tutti gli elementi dell'elenco devono essere dello stesso tipo. Fanno eccezione gli elenchi in cui gli elementi vengono specificati come tipi di base. Gli elementi di tali elenchi possono essere tipi derivati. Sono pertanto accettabili gli elementi seguenti, poiché sia `Button` che `CheckBox` derivano da `Control`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

È anche possibile definire gli elementi dell'elenco usando un intervallo indicato da numeri interi separati dall'operatore di intervallo (`..`), come mostrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

Un elenco vuoto viene specificato da una coppia di parentesi quadre al cui interno non è presente alcun elemento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

È possibile anche usare un'espressione sequenza per creare un elenco. Per ulteriori informazioni, vedere [espressioni di sequenza](sequences.md#sequence-expressions) . Ad esempio, il codice seguente crea un elenco di quadrati di numeri interi compresi tra 1 e 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a>Operatori per l'uso di elenchi

È possibile associare elementi a un elenco usando l'operatore `::` (cons). Se `list1` è `[2; 3; 4]`, il codice seguente crea `list2` come `[100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

È possibile concatenare gli elenchi con tipi compatibili usando l'operatore `@`, come nel codice seguente. Se `list1` è `[2; 3; 4]` e `list2` è `[100; 2; 3; 4]`, questo codice crea `list3` come `[2; 3; 4; 100; 2; 3; 4]`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

Le funzioni per l'esecuzione di operazioni sugli elenchi sono disponibili nel [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).

Poiché gli elenchi in F# non sono modificabili, qualsiasi operazione di modifica comporta la generazione di nuovi elenchi anziché la modifica di quelli esistenti.

Gli elenchi F# in vengono implementati come elenchi collegati singolarmente, il che significa che le operazioni che accedono solo all'elemento Head dell'elenco sono o (1) e l'accesso agli elementi è o (*n*).

## <a name="properties"></a>Proprietà

Il tipo di elenco supporta le proprietà seguenti:

|Proprietà|Type|DESCRIZIONE|
|--------|----|-----------|
|[Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|Primo elemento.|
|[Vuoto](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|Proprietà statica che restituisce un elenco vuoto del tipo appropriato.|
|[IsEmpty](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|`true` se nell'elenco non sono presenti elementi.|
|[Item](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|Elemento in corrispondenza dell'indice specificato (a base zero).|
|[Lunghezza](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|Numero di elementi.|
|[Coda](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|Elenco senza il primo elemento.|

Di seguito sono riportati alcuni esempi per l'uso di queste proprietà.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a>Uso degli elenchi

L'uso degli elenchi nella programmazione consente di eseguire operazioni complesse con una piccola quantità di codice. Questa sezione descrive le operazioni comuni sugli elenchi, fondamentali ai fini della programmazione funzionale.

### <a name="recursion-with-lists"></a>Ricorsione con elenchi

Gli elenchi sono particolarmente adatti per le tecniche di programmazione ricorsive. Nel caso di un'operazione da eseguire su ogni elemento di un elenco, è possibile operare in modo ricorsivo sull'elemento head dell'elenco e quindi passare all'elemento tail, ovvero un elenco di dimensioni ridotte costituito dall'elenco originale senza il primo elemento, per poi tornare al livello successivo di ricorsione.

Per scrivere una funzione ricorsiva di questo tipo, è necessario usare l'operatore cons (`::`) nei criteri di ricerca, per separare l'elemento head dell'elenco dall'elemento tail.

L'esempio di codice seguente illustra come usare i criteri di ricerca per implementare una funzione ricorsiva che esegue le operazioni su un elenco.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

Il codice precedente è ideale per elenchi di piccole dimensioni, ma con gli elenchi di grandi dimensione potrebbe verificarsi un overflow dello stack. Il codice seguente migliora questo tipo di codice mediante un argomento dell'accumulatore, una tecnica standard per l'uso di funzioni ricorsive. L'uso dell'argomento accumulatore rende ricorsivo la funzione tail, risparmiando spazio nello stack.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

`RemoveAllMultiples` è una funzione ricorsiva che accetta due elenchi. Il primo elenco contiene i numeri di cui verranno rimossi i multipli e il secondo è l'elenco da cui rimuovere i numeri. Il codice nell'esempio seguente usa questa funzione ricorsiva per eliminare tutti i numeri non primi da un elenco, restituendo come risultato un elenco di numeri primi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

L'output è indicato di seguito:

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a>Funzioni di modulo

Il [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) fornisce funzioni che accedono agli elementi di un elenco. L'elemento head è il più veloce e più semplice a cui accedere. Usare l' [intestazione](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) della proprietà o l'elenco di funzioni del modulo [. Head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2). È possibile accedere alla parte finale di un elenco usando la proprietà [tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) o la funzione [List. Tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) . Per trovare un elemento in base all'indice, usare la funzione [List. nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) . `List.nth` attraversa l'elenco Pertanto, è O (*n*). Se il codice usa `List.nth` in modo frequente, è opportuno considerare l'uso di una matrice anziché di un elenco L'accesso agli elementi nelle matrici è O(1).

### <a name="boolean-operations-on-lists"></a>Operazioni booleane sugli elenchi

La funzione [List. IsEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) determina se un elenco contiene elementi.

La funzione [List. Exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) applica un test booleano agli elementi di un elenco `true` e restituisce se un elemento soddisfa il test. [List. exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) è simile, ma opera su coppie successive di elementi in due elenchi.

Il codice seguente illustra l'uso di `List.exists`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

L'output è indicato di seguito:

```console
For list [0; 1; 2; 3], contains zero is true
```

L'esempio seguente illustra l'uso di `List.exists2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

L'output è indicato di seguito:

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

È possibile utilizzare [List. ForAll](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) se si desidera verificare se tutti gli elementi di un elenco soddisfano una condizione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

L'output è indicato di seguito:

```console
true
false
```

In modo analogo, [List. forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determina se tutti gli elementi nelle posizioni corrispondenti di due elenchi soddisfano un'espressione booleana che prevede ogni coppia di elementi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

L'output è indicato di seguito:

```console
true
false
```

### <a name="sort-operations-on-lists"></a>Operazioni di ordinamento sugli elenchi

Le funzioni [List. Sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List. sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359)e [List. sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) ordinano gli elenchi. La funzione di ordinamento determina quali funzioni usare tra le tre indicate in precedenza. `List.sort` usa il confronto generico predefinito. Il confronto generico usa gli operatori globali basati sulla funzione di confronto generico per confrontare i valori. È perfettamente compatibile con un'ampia gamma di tipi di elemento, ad esempio tipi numerici semplici, tuple, record, unioni discriminate, elenchi, matrici e qualsiasi tipo che implementa `System.IComparable`. Per i tipi che implementano `System.IComparable`, il confronto generico usa la funzione `System.IComparable.CompareTo()`. Il confronto generico usa anche le stringhe, ma adotta un ordinamento indipendente dalle impostazioni cultura. Non è opportuno usare il confronto generico sui tipi non supportati, ad esempio i tipi di funzione. Le prestazioni del confronto generico predefinito risultano inoltre ottimali per i tipi strutturati di piccole dimensioni, mentre per i tipi strutturati di grandi dimensioni, che devono essere confrontati e ordinati con frequenza, provare a implementare `System.IComparable` e a fornire un'implementazione efficiente del metodo `System.IComparable.CompareTo()`.

`List.sortBy` accetta una funzione che restituisce un valore usato come criterio di ordinamento e `List.sortWith` accetta una funzione di confronto come argomento. Queste ultime due funzioni risultano utili nel caso in cui vengano usati tipi che non supportano il confronto oppure se il confronto richiede una semantica più complessa, come nel caso di stringhe dipendenti dalle impostazioni cultura.

L'esempio seguente illustra l'uso di `List.sort`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

L'output è indicato di seguito:

```console
[-2; 1; 4; 5; 8]
```

L'esempio seguente illustra l'uso di `List.sortBy`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

L'output è indicato di seguito:

```console
[1; -2; 4; 5; 8]
```

L'esempio seguente illustra l'uso di `List.sortWith`. In questo esempio, la funzione di confronto personalizzato `compareWidgets` viene usata per confrontare in primo luogo un campo di un tipo personalizzato, quindi un altro campo, se i valori del primo campo sono uguali.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

L'output è indicato di seguito:

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a>Operazioni di ricerca sugli elenchi

Per gli elenchi sono supportate numerose operazioni di ricerca. Il più semplice, [List. Find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), consente di trovare il primo elemento che corrisponde a una determinata condizione.

L'esempio di codice seguente illustra l'uso di `List.find` per trovare il primo numero divisibile per 5 in un elenco.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

Il risultato è 5.

Se gli elementi devono essere trasformati per primi, chiamare [List. pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), che accetta una funzione che restituisce un'opzione e cerca il primo valore `Some(x)`di opzione corrispondente a. Anziché restituire l'elemento, `List.pick` restituisce il risultato `x`. Se non viene trovato alcun elemento corrispondente, `List.pick` genera un'eccezione `System.Collections.Generic.KeyNotFoundException`. Il codice seguente illustra l'uso di `List.pick`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

L'output è indicato di seguito:

```console
"b"
```

Un altro gruppo di operazioni di ricerca, [List. tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) e funzioni correlate, restituisce un valore di opzione. La funzione `List.tryFind` restituisce il primo elemento di un elenco che soddisfa una condizione se tale elemento è presente e il valore di opzione `None` in caso contrario. La variante [List. tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) restituisce l'indice dell'elemento, se ne viene trovato uno, anziché l'elemento stesso. Queste funzioni vengono illustrate nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

L'output è indicato di seguito:

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a>Operazioni aritmetiche sugli elenchi

Le operazioni aritmetiche comuni come Sum e Average sono compilate nel [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788). Per lavorare con [List. Sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), il tipo di elemento dell'elenco deve `+` supportare l'operatore e avere un valore pari a zero. Tutti i tipi aritmetici incorporati soddisfano queste condizioni. Per lavorare con [List. Average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), il tipo di elemento deve supportare la divisione senza un resto, che esclude i tipi integrali ma consente i tipi a virgola mobile. Le funzioni [List. sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) e [List. averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) accettano una funzione come parametro e i risultati di questa funzione vengono usati per calcolare i valori per la somma o la media.

Il codice seguente illustra l'uso di `List.sum`, `List.sumBy` e `List.average`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

L'output è `1.000000`.

Il codice seguente illustra l'uso di `List.averageBy`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

L'output è `5.5`.

### <a name="lists-and-tuples"></a>Elenchi e tuple

Gli elenchi che contengono tuple possono essere modificati da funzioni di compressione e decompressione. Queste funzioni combinano due elenchi di valori singoli in un elenco di tuple o separano un elenco di tuple in due elenchi di valori singoli. La funzione [List. zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) più semplice accetta due elenchi di elementi singoli e produce un unico elenco di coppie di Tuple. Un'altra versione, [List. zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), accetta tre elenchi di elementi singoli e produce un unico elenco di tuple che hanno tre elementi. L'esempio di codice seguente illustra l'uso di `List.zip`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

L'output è indicato di seguito:

```console
[(1, -1); (2, -2); (3; -3)]
```

L'esempio di codice seguente illustra l'uso di `List.zip3`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

L'output è indicato di seguito:

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

Le versioni unzip corrispondenti, [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) ed [List. unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), accettano elenchi di tuple e restituiscono elenchi in una tupla, dove il primo elenco contiene tutti gli elementi che erano primi in ogni tupla e il secondo elenco contiene il secondo elemento di ogni tupla. tupla e così via.

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

L'output è indicato di seguito:

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di [List. unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

L'output è indicato di seguito:

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a>Operazioni sugli elementi dell'elenco

F# supporta un'ampia gamma di operazioni sugli elementi di un elenco. Il più semplice è [List. iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), che consente di chiamare una funzione su ogni elemento di un elenco. Le varianti includono [List. iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), che consente di eseguire un'operazione su elementi di due elenchi, [List. iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), che è simile `List.iter` a, ad eccezione del fatto che l'indice di ogni elemento viene passato come argomento alla funzione chiamata per ogni elemento. Element e [List. iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), che è una combinazione delle funzionalità di `List.iter2` e. `List.iteri` Queste funzioni vengono illustrate nell'esempio di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

L'output è indicato di seguito:

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

Un'altra funzione di uso frequente che trasforma gli elementi elenco è [List. map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), che consente di applicare una funzione a ogni elemento di un elenco e inserire tutti i risultati in un nuovo elenco. [List. map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) e [List. map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) sono varianti che accettano più elenchi. È anche possibile usare [List. MAPI](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) ed [List. mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), se, oltre all'elemento, la funzione deve essere passata all'indice di ogni elemento. L'unica differenza tra `List.mapi2` e `List.mapi` consiste nel fatto che `List.mapi2` usa due elenchi. Nell'esempio seguente viene illustrato [List. map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

L'output è indicato di seguito:

```console
[2; 3; 4]
```

L'esempio seguente illustra l'uso di `List.map2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

L'output è indicato di seguito:

```console
[5; 7; 9]
```

L'esempio seguente illustra l'uso di `List.map3`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

L'output è indicato di seguito:

```console
[7; 10; 13]
```

L'esempio seguente illustra l'uso di `List.mapi`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

L'output è indicato di seguito:

```console
[1; 3; 5]
```

L'esempio seguente illustra l'uso di `List.mapi2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

L'output è indicato di seguito:

```console
[0; 7; 18]
```

[List. Collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) è simile `List.map`a, ad eccezione del fatto che ogni elemento produce un elenco e tutti gli elenchi sono concatenati in un elenco finale. Nel codice seguente ogni elemento dell'elenco genera tre numeri, che vengono raccolti in un elenco.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

L'output è indicato di seguito:

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

È anche possibile usare [List. Filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), che accetta una condizione booleana e produce un nuovo elenco costituito solo da elementi che soddisfano la condizione specificata.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

L'elenco risultante è `[2; 4; 6]`.

Una combinazione di map e Filter, [List. Choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) consente di trasformare e selezionare gli elementi contemporaneamente. `List.choose` applica una funzione che restituisce un'opzione a ogni elemento di un elenco e restituisce un nuovo elenco dei risultati per gli elementi quando la funzione restituisce il valore di opzione `Some`.

Il codice seguente illustra l'uso di `List.choose` per selezionare parole in lettere maiuscole da un elenco di parole.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

L'output è indicato di seguito:

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a>Operazioni su più elenchi

Gli elenchi possono essere uniti. Per unire due elenchi in uno, usare [List. Append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426). Per unire in join più di due elenchi, usare [List. Concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a>Operazioni di riduzione e analisi

Alcune operazioni sugli elenchi comportano interdipendenze tra tutti gli elementi di un elenco. Le operazioni di analisi e riduzioni `List.iter` sono `List.map` simili a e in quanto si richiama una funzione su ogni elemento, ma queste operazioni forniscono un parametro aggiuntivo denominato *accumulatore* che trasporta informazioni attraverso il calcolo.

Usare `List.fold` per eseguire un calcolo in un elenco.

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di [List. fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) per eseguire varie operazioni.

L'elenco viene attraversato. L'accumulatore `acc` è un valore passato contestualmente all'esecuzione del calcolo. Il primo argomento accetta l'accumulatore e l'elemento dell'elenco e restituisce il risultato provvisorio del calcolo per l'elemento dell'elenco. Il secondo argomento è il valore iniziale dell'accumulatore.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

Le versioni di queste funzioni che contengono una cifra nel nome della funzione consentono di eseguire operazioni su più di un elenco. [List. fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) , ad esempio, esegue calcoli in due elenchi.

L'esempio seguente illustra l'uso di `List.fold2`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

`List.fold`e [List. Scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differiscono in `List.fold` che restituisce il valore finale del parametro aggiuntivo, ma `List.scan` restituisce l'elenco dei valori intermedi (insieme al valore finale) del parametro aggiuntivo.

Ognuna di queste funzioni include una variazione inversa, ad esempio [List. foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), che differisce dall'ordine in cui viene attraversato l'elenco e dall'ordine degli argomenti. Inoltre, `List.fold` e `List.foldBack` hanno variazioni, [List. fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) e [List. foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), che accettano due elenchi di uguale lunghezza. La funzione eseguita su ogni elemento può usare elementi corrispondenti di entrambi gli elenchi per eseguire un'azione. I tipi di elementi dei due elenchi possono essere diversi, come nell'esempio seguente, in cui un elenco contiene importi di transazioni per un conto bancario e l'altro contiene il tipo di transazione (deposito o prelievo).

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

Per un calcolo quale una somma, `List.fold` e `List.foldBack` producono lo stesso effetto, poiché il risultato non dipende dall'ordine di attraversamento. Nell'esempio seguente viene usato `List.foldBack` per aggiungere gli elementi a un elenco.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

Per l'esempio seguente viene nuovamente usato il conto bancario precedente. Questa volta viene aggiunto un nuovo tipo di transazione: il calcolo degli interessi. Il saldo finale dipende ora dall'ordine delle transazioni.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

L'elenco di funzioni [. reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) è piuttosto `List.fold` simile `List.scan`a e, ad eccezione del fatto che anziché passare un `List.reduce` accumulatore separato, accetta una funzione che accetta due argomenti del tipo di elemento anziché solo uno e uno di questi arguments funge da accumulatore, ovvero archivia il risultato intermedio del calcolo. `List.reduce` esegue innanzitutto le operazioni sui primi due elementi dell'elenco, quindi usa il risultato dell'operazione insieme all'elemento successivo. Poiché nessun accumulatore separato ha un proprio tipo, `List.reduce` può essere usato al posto di `List.fold` solo se l'accumulatore e il tipo di elemento hanno lo stesso tipo. Il codice seguente illustra l'uso di `List.reduce`. `List.reduce` genera un'eccezione se l'elenco fornito non contiene elementi.

Nel codice seguente per la prima chiamata all'espressione lambda vengono forniti gli argomenti 2 e 4, quindi la chiamata restituisce 6. Per la chiamata successiva vengono forniti gli argomenti 6 e 10, pertanto il risultato è 16.

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a>Conversione tra elenchi e altri tipi di raccolta

Il modulo `List` fornisce funzioni per la conversione da e verso sequenze e matrici. Per eseguire la conversione da o verso una sequenza, usare [List. toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) o [List. ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0). Per eseguire la conversione da o verso una matrice, usare [List. ToArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) o [List. ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).

### <a name="additional-operations"></a>Operazioni aggiuntive

Per informazioni sulle operazioni aggiuntive sugli elenchi, vedere il [Modulo Collections. list](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d)dell'argomento di riferimento della libreria.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Tipi F#](fsharp-types.md)
- [Sequenze](sequences.md)
- [Matrici](arrays.md)
- [Opzioni](options.md)
