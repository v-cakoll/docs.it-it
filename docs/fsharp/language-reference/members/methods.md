---
title: Metodi
description: Informazioni su come F# un metodo è una funzione associata a un tipo che viene usato per esporre e implementare le funzionalità e il comportamento di oggetti e tipi.
ms.date: 05/16/2016
ms.openlocfilehash: 13503690a59ace13dacba93b6fce9ea3240c5cc2
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627448"
---
# <a name="methods"></a>Metodi

Un *Metodo* è una funzione associata a un tipo. Nella programmazione orientata a oggetti, i metodi vengono utilizzati per esporre e implementare le funzionalità e il comportamento di oggetti e tipi.

## <a name="syntax"></a>Sintassi

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a>Note

Nella sintassi precedente è possibile vedere le varie forme delle dichiarazioni e delle definizioni dei metodi. Nei corpi dei metodi più lunghi, un'interruzioni di riga segue il segno di uguale (=) e l'intero corpo del metodo viene rientrato.

Gli attributi possono essere applicati a qualsiasi dichiarazione di metodo. Precedono la sintassi per una definizione di metodo e sono in genere elencate in una riga separata. Per altre informazioni, vedere [Attributi](../attributes.md).

I metodi possono essere `inline`contrassegnati. Per informazioni su `inline`, vedere [Funzioni inline](../functions/inline-functions.md).

I metodi non inline possono essere usati in modo ricorsivo all'interno del tipo. non è necessario usare in modo esplicito la `rec` parola chiave.

## <a name="instance-methods"></a>Metodi di istanza

I metodi di istanza sono dichiarati con la `member` parola chiave e un autoidentificatore, seguiti da un punto (.) e dal nome del metodo e dai parametri. Come nel caso `let` delle associazioni, l'elenco di *parametri* può essere un modello. In genere, i parametri del metodo vengono racchiusi tra parentesi in un form di tupla, ovvero il modo F# in cui vengono visualizzati i metodi quando vengono creati in altre lingue .NET Framework. Tuttavia, il modulo sottoposto a currying (parametri separati da spazi) è comune e anche altri modelli sono supportati.

Nell'esempio seguente viene illustrata la definizione e l'utilizzo di un metodo di istanza non astratto.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Nei metodi di istanza, non usare l'identificatore automatico per accedere ai campi definiti mediante le associazioni let. Usare l'identificatore automatico quando si accede ad altri membri e proprietà.

## <a name="static-methods"></a>Metodi statici

La parola `static` chiave viene usata per specificare che un metodo può essere chiamato senza un'istanza di e non è associato a un'istanza dell'oggetto. In caso contrario, i metodi sono metodi di istanza.

Nell'esempio riportato nella sezione successiva vengono mostrati i campi `let` dichiarati con la parola chiave `member` , i membri della proprietà dichiarati con `static` la parola chiave e un metodo statico dichiarato con la parola chiave.

Nell'esempio seguente viene illustrata la definizione e l'utilizzo di metodi statici. Si supponga che queste definizioni di metodo si `SomeType` trovino nella classe della sezione precedente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Metodi virtuali e astratti

La parola `abstract` chiave indica che un metodo ha uno slot di invio virtuale e potrebbe non avere una definizione nella classe. Uno *slot di invio virtuale* è una voce in una tabella di funzioni gestita internamente che viene utilizzata in fase di esecuzione per cercare le chiamate di funzioni virtuali in un tipo orientato a oggetti. Il meccanismo di invio virtuale è il meccanismo cheimplementa il polimorfismo, una funzionalità importante della programmazione orientata a oggetti. Una classe che ha almeno un metodo astratto senza una definizione è una *classe astratta*, il che significa che non è possibile creare istanze di tale classe. Per ulteriori informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).

Le dichiarazioni di metodo astratto non includono il corpo di un metodo. Il nome del metodo è invece seguito da due punti (:) e una firma del tipo per il metodo. La firma del tipo di un metodo è identica a quella mostrata da IntelliSense quando si posiziona il puntatore del mouse su un nome di metodo nell'editor di Visual Studio Code, eccetto senza i nomi di parametro. Le firme dei tipi vengono visualizzate anche dall'interprete, FSI. exe, quando si lavora in modo interattivo. La firma del tipo di un metodo è costituita da un elenco dei tipi di parametri, seguiti dal tipo restituito, con i simboli di separatore appropriati. I parametri sottoposti a currying sono separati da `->` e i parametri di tupla sono separati da. `*` Il valore restituito è sempre separato dagli argomenti da un `->` simbolo. Le parentesi possono essere utilizzate per raggruppare parametri complessi, ad esempio quando un tipo di funzione è un parametro o per indicare quando una tupla viene considerata come un singolo parametro anziché come due parametri.

È anche possibile assegnare definizioni predefinite dei metodi astratti aggiungendo la definizione alla classe e usando la `default` parola chiave, come illustrato nel blocco della sintassi in questo argomento. Un metodo astratto con una definizione nella stessa classe è equivalente a un metodo virtuale in altri linguaggi .NET Framework. Indipendentemente dal fatto che esista o meno `abstract` una definizione, la parola chiave crea un nuovo slot di distribuzione nella tabella delle funzioni virtuali per la classe.

Indipendentemente dal fatto che una classe base implementi i metodi astratti, le classi derivate possono fornire implementazioni di metodi astratti. Per implementare un metodo astratto in una classe derivata, definire un metodo con lo stesso nome e la stessa firma nella classe derivata, eccetto usare la `override` parola `default` chiave o e fornire il corpo del metodo. Le parole `override` chiave `default` e indicano esattamente la stessa cosa. Usare `override` se il nuovo metodo esegue l'override di un'implementazione della `default` classe di base; usare quando si crea un'implementazione nella stessa classe della dichiarazione astratta originale. Non usare la `abstract` parola chiave sul metodo che implementa il metodo dichiarato abstract nella classe di base.

Nell'esempio seguente viene illustrato un metodo `Rotate` astratto che dispone di un'implementazione predefinita, l'equivalente di un .NET Framework metodo virtuale.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Nell'esempio seguente viene illustrata una classe derivata che esegue l'override di un metodo della classe base. In questo caso, l'override modifica il comportamento in modo che il metodo non esegua alcuna operazione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Metodi di overload

I metodi di overload sono metodi con nomi identici in un determinato tipo ma con argomenti diversi. In F#gli argomenti facoltativi vengono in genere utilizzati al posto dei metodi di overload. Tuttavia, i metodi di overload sono consentiti nel linguaggio, a condizione che gli argomenti siano in formato tupla, non in un modulo sottoposto a currying.

## <a name="optional-arguments"></a>Argomenti facoltativi

A partire F# da 4,1, è anche possibile avere argomenti facoltativi con un valore di parametro predefinito nei metodi.  Questo consente di semplificare l'interoperabilità C# con il codice.  Nell'esempio seguente viene illustrata la sintassi:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Si noti che il valore passato in `DefaultParameterValue` per deve corrispondere al tipo di input.  Nell'esempio precedente, si tratta di un `int`oggetto.  Il tentativo di passare un valore non integer a `DefaultParameterValue` comporterebbe un errore di compilazione.

## <a name="example-properties-and-methods"></a>Esempio: Proprietà e metodi

Nell'esempio seguente è contenuto un tipo con esempi di campi, funzioni private, proprietà e un metodo statico.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
