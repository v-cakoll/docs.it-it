---
title: Record
description: Informazioni sul F# modo in cui i record rappresentano aggregazioni semplici di valori denominati, facoltativamente con i membri.
ms.date: 06/09/2019
ms.openlocfilehash: 1ba002407b1ccbcbceed32df8636fb860e89e3b6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053932"
---
# <a name="records"></a>Record

I record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri. Possono essere struct o tipi di riferimento.  Sono tipi di riferimento per impostazione predefinita.

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

Nella sintassi precedente, *typeName* è il nome del tipo di record, *Label1* e *Label2* sono nomi di valori, denominati *labels*e *tipo1* e *tipo2* sono i tipi di questi valori. *Member-List* è l'elenco facoltativo di membri per il tipo.  È possibile utilizzare l' `[<Struct>]` attributo per creare un record struct anziché un record che è un tipo di riferimento.

Di seguito sono riportati alcuni esempi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

Quando ogni etichetta si trova su una riga distinta, il punto e virgola è facoltativo.

È possibile impostare valori nelle espressioni note come *espressioni di record*. Il compilatore deduce il tipo dalle etichette utilizzate (se le etichette sono sufficientemente distinte da quelle di altri tipi di record). Racchiudere l'espressione di record tra parentesi graffe ({}). Il codice seguente illustra un'espressione di record che Inizializza un record con tre elementi float con `x`etichette `y` , `z`e.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

Non usare il formato abbreviato se può essere presente un altro tipo che ha anche le stesse etichette.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

Le etichette del tipo dichiarato più di recente hanno la precedenza su quelle del tipo dichiarato in precedenza, pertanto nell'esempio precedente, `mypoint3D` viene dedotto `Point3D`come. È possibile specificare in modo esplicito il tipo di record, come nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

I metodi possono essere definiti per i tipi di record come per i tipi di classe.

## <a name="creating-records-by-using-record-expressions"></a>Creazione di record tramite espressioni di record

È possibile inizializzare i record usando le etichette definite nel record. Un'espressione che esegue questa operazione viene definita espressione di *record*. Utilizzare le parentesi graffe per racchiudere l'espressione di record e utilizzare il punto e virgola come delimitatore.

Nell'esempio seguente viene illustrato come creare un record.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

I punti e virgola dopo l'ultimo campo nell'espressione di record e nella definizione del tipo sono facoltativi, indipendentemente dal fatto che i campi si trovino tutti in una sola riga.

Quando si crea un record, è necessario specificare i valori per ogni campo. Non è possibile fare riferimento ai valori di altri campi nell'espressione di inizializzazione per qualsiasi campo.

Nel codice seguente, il tipo di `myRecord2` viene dedotto dai nomi dei campi. Facoltativamente, è possibile specificare il nome del tipo in modo esplicito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Un altro tipo di costruzione di record può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo. Questa operazione viene illustrata nella seguente riga di codice.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

Questa forma dell'espressione di record è denominata *espressione di copia e aggiornamento del record*.

I record non sono modificabili per impostazione predefinita. Tuttavia, è possibile creare facilmente record modificati usando un'espressione di copia e aggiornamento. È anche possibile specificare in modo esplicito un campo modificabile.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

Non usare l'attributo DefaultValue con i campi di record. Un approccio migliore consiste nel definire le istanze predefinite dei record con i campi inizializzati sui valori predefiniti e quindi usare un'espressione di copia e aggiornamento del record per impostare i campi che differiscono dai valori predefiniti.

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

## <a name="creating-mutually-recursive-records"></a>Creazione di record ricorsivi reciproci

A volte, quando si crea un record, è possibile che dipenda da un altro tipo che si desidera definire in seguito. Si tratta di un errore di compilazione a meno che non si definiscono i tipi di record per essere ricorsivi reciproci.

La definizione di record ricorsivi reciproci viene `and` eseguita con la parola chiave. In questo modo è possibile collegare due o più tipi di record.

Ad esempio, il codice seguente definisce un `Person` tipo `Address` e come ricorsivamente ricorsivo:

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
    PostCode: string
    Occupant: Person }
```

Se si definisce l'esempio precedente senza la `and` parola chiave, non verrà compilato. La `and` parola chiave è obbligatoria per le definizioni ricorsive reciproche.

## <a name="pattern-matching-with-records"></a>Criteri di ricerca con record

I record possono essere usati con i criteri di ricerca. È possibile specificare in modo esplicito alcuni campi e fornire variabili per altri campi che verranno assegnati quando si verifica una corrispondenza. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

L'output di questo codice è il seguente.

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a>Differenze tra record e classi

I campi di record sono diversi dalle classi perché vengono esposti automaticamente come proprietà e vengono usati nella creazione e nella copia di record. La costruzione di record differisce anche dalla costruzione delle classi. In un tipo di record non è possibile definire un costruttore. Viene invece applicata la sintassi di costruzione descritta in questo argomento. Le classi non hanno alcuna relazione diretta tra i parametri del costruttore, i campi e le proprietà.

Analogamente ai tipi unione e struttura, i record hanno una semantica di uguaglianza strutturale. Le classi hanno una semantica di uguaglianza di riferimento. Nell'esempio di codice seguente viene illustrata questa possibilità.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

L'output di questo codice è il seguente:

```
The records are equal.
```

Se si scrive lo stesso codice con le classi, i due oggetti classe sarebbero diversi perché i due valori rappresenterebbero due oggetti nell'heap e verranno confrontati solo gli indirizzi (a meno che il tipo di classe non esegua l'override del `System.Object.Equals` metodo).

Se è necessaria l'uguaglianza dei riferimenti per i record, `[<ReferenceEquality>]` aggiungere l'attributo sopra il record.

## <a name="see-also"></a>Vedere anche

- [Tipi F#](fsharp-types.md)
- [Classi](classes.md)
- [Riferimenti per il linguaggio F#](index.md)
- [Riferimento-uguaglianza](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [Criteri di ricerca](pattern-matching.md)
