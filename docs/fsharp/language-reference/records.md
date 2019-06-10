---
title: Record
description: Informazioni su come F# i record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.
ms.date: 06/09/2019
ms.openlocfilehash: cfb8de8272b479571119ae4cf91ea1d6fd5db73c
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816196"
---
# <a name="records"></a>Record

I record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri. Reti virtuali possono essere tipi riferimento o struct.  Si tratta di tipi di riferimento per impostazione predefinita.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a>Note

Nella sintassi precedente *nomeTipo* è il nome del tipo di record, *label1* e *label2* sono nomi di valori, detti *etichette*, e *type1* e *type2* sono i tipi di questi valori. *elenco di membri* è riportato l'elenco facoltativo di membri per il tipo.  È possibile usare il `[<Struct>]` attributo per creare un record di struct, anziché un record che è un tipo riferimento.

Di seguito sono riportati alcuni esempi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Una volta ogni etichetta in una riga separata, il punto e virgola è facoltativo.

È possibile impostare i valori nelle espressioni dette *espressioni di record*. Il compilatore deduce il tipo dalle etichette usato (se le etichette sono sufficientemente distinte da quelli di altri tipi di record). Le parentesi graffe ({}) racchiudono l'espressione di record. Il codice seguente illustra un'espressione di record che inizializza un record con tre elementi di float con etichette `x`, `y` e `z`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

Non utilizzare la forma abbreviata se è possibile che un altro tipo che ha anche le stesse etichette.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Le etichette del tipo dichiarato più di recente hanno la precedenza rispetto a quelli del tipo dichiarato in precedenza, pertanto nell'esempio precedente `mypoint3D` viene dedotto come `Point3D`. È possibile specificare in modo esplicito il tipo di record, come nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

I metodi possono essere definiti per i tipi di record in modo analogo ai tipi di classe.

## <a name="creating-records-by-using-record-expressions"></a>Creazione di record utilizzando espressioni di Record

È possibile inizializzare i record con le etichette che sono definite nel record. Un'espressione che esegue questa operazione è detta una *espressione di record*. Usare le parentesi graffe per racchiudere l'espressione di record e usare il punto e virgola come delimitatore.

Nell'esempio seguente viene illustrato come creare un record.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

I punti e virgola dopo l'ultimo campo nell'espressione di record e nella definizione del tipo sono facoltativi, indipendentemente dal fatto che i campi sono tutti in un'unica riga.

Quando si crea un record, è necessario fornire valori per ogni campo. È possibile fare riferimento ai valori di altri campi nell'espressione di inizializzazione per tutti i campi.

Nel codice seguente, il tipo di `myRecord2` viene dedotto dai nomi dei campi. Facoltativamente, è possibile specificare il nome del tipo in modo esplicito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Un'altra forma di costruzione di record può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo. La riga di codice seguente illustra questa soluzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Questa forma di espressione di record viene chiamata il *copiare e aggiornare l'espressione di record*.

I record non sono modificabili per impostazione predefinita. Tuttavia, è possibile creare facilmente record modificati tramite un'espressione di copia e l'aggiornamento. È possibile specificare in modo esplicito un campo modificabile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

Non usare l'attributo DefaultValue con i campi di record. Un approccio migliore è definire le istanze predefinite di record con i campi che vengono inizializzati sui valori predefiniti e quindi utilizzare una copia e aggiornare l'espressione di record per impostare tutti i campi che differiscono dai valori predefiniti.

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a>La creazione di record ricorsiva si escludono a vicenda

Un intervallo di tempo durante la creazione di un record, è possibile fare in modo che dipendono da un altro tipo che si vuole definire in un secondo momento. Si tratta di un errore di compilazione se non si definiscono i tipi di record siano reciprocamente ricorsiva.

Definizione dei record ricorsivo si escludono a vicenda viene eseguita con il `and` (parola chiave). Ciò consente di collegare i tipi di 2 o più record.

Ad esempio, il codice seguente definisce una `Person` e `Address` tipo ricorsive reciproche:

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string }
```

Se si dovesse definire l'esempio precedente senza i `and` (parola chiave), quindi, non sarà possibile compilare. Il `and` parola chiave è obbligatoria per le definizioni di ricorsivo si escludono a vicenda.

## <a name="pattern-matching-with-records"></a>Criteri di ricerca con i record

I record sono utilizzabili con criteri di ricerca. È possibile specificare in modo esplicito alcuni campi e specificare le variabili per gli altri campi che verranno assegnati quando viene rilevata una corrispondenza. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

L'output di questo codice è come indicato di seguito.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>Differenze tra classi e i record

Campi del record differiscono dalle classi vengono esposti automaticamente come proprietà e sono utilizzati nella creazione e alla copia dei record. Costruzione di record è diversa anche dalla costruzione della classe. In un tipo di record, è possibile definire un costruttore. Al contrario, si applica la sintassi di costruzione descritte in questo argomento. Classi di avere alcuna relazione diretta tra i parametri del costruttore, campi e proprietà.

Come i tipi di struttura e unione, record hanno una semantica di uguaglianza strutturale. Le classi hanno riferimenti semantica di uguaglianza. Nell'esempio di codice seguente viene illustrata questa possibilità.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

Come indicato di seguito è riportato l'output di questo codice:

```
The records are equal.
```

Se si scrittura lo stesso codice con le classi, i due oggetti di classe sarebbe diversi perché i due valori rappresenterebbe due oggetti nell'heap e potrebbero essere confrontati solo gli indirizzi (a meno che il tipo di classe esegue l'override di `System.Object.Equals` (metodo)).

Se è necessario fare riferimento l'uguaglianza dei record, aggiungere l'attributo `[<ReferenceEquality>]` sopra il record.

## <a name="see-also"></a>Vedere anche

- [Tipi F#](fsharp-types.md)
- [Classi](classes.md)
- [Riferimenti per il linguaggio F#](index.md)
- [Reference-Equality](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [Criteri di ricerca](pattern-matching.md)
