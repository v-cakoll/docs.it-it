---
title: Record (F#)
description: 'Informazioni su come record F # rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1270bf4eaeba99a15b0f81b5477f4c3b98644f66
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="records"></a>Record

I record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.  A partire da F # 4.1, essi può essere struct o tipi di riferimento.  Si tratta di tipi di riferimento per impostazione predefinita.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type [accessibility-modifier] typename = {
    [ mutable ] label1 : type1;
    [ mutable ] label2 : type2;
    ...
}
    [ member-list ]
```

## <a name="remarks"></a>Note
Nella sintassi precedente, *typename* è il nome del tipo di record, *label1* e *label2* sono nomi dei valori, detti *etichette*, e *type1* e *type2* sono i tipi di questi valori. *elenco di membri* è l'elenco dei membri per il tipo di parametro facoltativo.  È possibile utilizzare il `[<Struct>]` attributo per creare un record di struct, anziché un record che è un tipo riferimento.

Di seguito sono riportati alcuni esempi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Una volta ogni etichetta in una riga separata, il punto e virgola è facoltativo.

È possibile impostare i valori nelle espressioni note come *registrare espressioni*. Il compilatore deduce il tipo dalle etichette utilizzate (se le etichette sono sufficientemente diversi da quelli di altri tipi di record). Le parentesi graffe ({}) racchiudono l'espressione di record. Il codice seguente è illustrata un'espressione di record che inizializza un record con tre elementi float con etichette `x`, `y` e `z`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

Non utilizzare la forma abbreviata se potrebbe esserci un altro tipo anche con le stesse etichette.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Le etichette del tipo dichiarato più di recente hanno la precedenza rispetto a quelli del tipo dichiarato in precedenza, in tal caso, nell'esempio precedente, `mypoint3D` viene considerato `Point3D`. È possibile specificare in modo esplicito il tipo di record, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

Metodi possono essere definiti per i tipi di record come per i tipi di classe.

## <a name="creating-records-by-using-record-expressions"></a>La creazione di record utilizzando espressioni di Record
È possibile inizializzare i record utilizzando le etichette che sono definite nel record. Un'espressione che esegue questa operazione è detta un *registrare espressione*. Utilizzare le parentesi graffe per racchiudere l'espressione di record e utilizzare il punto e virgola come delimitatore.

Nell'esempio seguente viene illustrato come creare un record.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

I punti e virgola dopo l'ultimo campo nell'espressione di record e nella definizione del tipo sono facoltativi, indipendentemente dal fatto che i campi sono tutti in una riga.

Quando si crea un record, è necessario fornire valori per ogni campo. È possibile fare riferimento ai valori di altri campi nell'espressione di inizializzazione per tutti i campi.

Nel codice seguente, il tipo di `myRecord2` è derivato dai nomi dei campi. Facoltativamente, è possibile specificare il nome del tipo in modo esplicito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Un'altra forma di costruzione di record può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori dei campi. Questa condizione è illustrata la riga di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Questa forma di espressione record viene chiamata la *espressione record copia e aggiornamento*.

Record non sono modificabili per impostazione predefinita. Tuttavia, è possibile creare facilmente modificati tramite un'espressione di copia e aggiornamento. Anche in modo esplicito, è possibile specificare un campo modificabile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

Non utilizzare l'attributo DefaultValue con campi di record. Un approccio migliore consiste nel definire le istanze predefinite di record con campi che vengono inizializzati i valori predefiniti e quindi utilizzare una copia espressione record e aggiornamento per impostare tutti i campi che sono diversi dai valori predefiniti.

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
{
    field1 : int
    field2 : int
}

let defaultRecord1 = { field1 = 0; field2 = 0 }
let defaultRecord2 = { field1 = 1; field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with field2 = 42 }
```

## <a name="pattern-matching-with-records"></a>Criteri di ricerca con i record
I record sono utilizzabili con criteri di ricerca. È possibile specificare in modo esplicito alcuni campi e fornire le variabili per gli altri campi che verranno assegnati quando si verifica una corrispondenza. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

L'output di questo codice è come indicato di seguito.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>Differenze tra i record e classi
I campi del record differiscono dalle classi in automaticamente sono esposti come proprietà e sono utilizzate per la creazione e la copia di record. La costruzione di record è diversa anche dalla costruzione di classi. In un tipo di record, è possibile definire un costruttore. Al contrario, la sintassi di costruzione descritta in questo argomento si applica. Le classi non dispongono di alcuna relazione diretta tra i parametri del costruttore, campi e proprietà.

Come tipi di unione e struttura, record hanno una semantica di uguaglianza strutturale. Le classi dispongono di riferimento semantica di uguaglianza. Nell'esempio di codice seguente viene illustrata questa possibilità.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

Se si scrive lo stesso codice con le classi, i due oggetti di classe sarebbero uguali perché i due valori rappresenterebbero due oggetti sull'heap e verrebbero confrontati solo gli indirizzi (a meno che il tipo di classe esegue l'override di `System.Object.Equals` (metodo)).

Se è necessario fare riferimento l'uguaglianza per i record, aggiungere l'attributo `[<ReferenceEquality>]` sopra il record.

## <a name="see-also"></a>Vedere anche
[Tipi F#](fsharp-types.md)

[Classi](classes.md)

[Riferimenti per il linguaggio F#](index.md)

[Uguaglianza di riferimento](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[Criteri di ricerca](pattern-matching.md)
