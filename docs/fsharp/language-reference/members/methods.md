---
title: Metodi (F#)
description: 'Informazioni su come un metodo di F # è una funzione associata a un tipo che consentono di esporre e implementare le funzionalità e il comportamento degli oggetti e tipi.'
ms.date: 05/16/2016
ms.openlocfilehash: e30300b4dd6cc26712a5adbc8abf720f2c312a6f
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
ms.locfileid: "34456640"
---
# <a name="methods"></a>Metodi

Oggetto *metodo* è una funzione che è associata a un tipo. Nella programmazione orientata agli oggetti, metodi vengono utilizzati per esporre e implementare le funzionalità e il comportamento degli oggetti e tipi.


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
Nella sintassi precedente, è possibile visualizzare le varie forme di dichiarazioni e definizioni. In più corpi di metodo, un'interruzione di riga segue il segno di uguale (=) e l'intero corpo del metodo è rientrato.

Gli attributi possono essere applicati a qualsiasi dichiarazione di metodo. Essi precedono la sintassi per una definizione di metodo e in genere sono elencati in una riga separata. Per altre informazioni, vedere [Attributi](../attributes.md).

Metodi possono essere contrassegnati `inline`. Per informazioni su `inline`, vedere [Funzioni inline](../functions/inline-functions.md).

I metodi non inline possono essere utilizzato in modo ricorsivo all'interno del tipo; non è necessario utilizzare in modo esplicito il `rec` (parola chiave).


## <a name="instance-methods"></a>Metodi di istanza
I metodi di istanza vengono dichiarati con la `member` (parola chiave) e un *autoidentificatore*, seguito da un punto (.) e il nome di metodo e i parametri. Come accade per `let` associazioni, la *elenco di parametri* può essere un modello. Metodo parametri tra parentesi nel formato di tupla, ovvero i metodi modo vengono visualizzati in genere, racchiudere in F # quando vengono creati in altri linguaggi .NET Framework. Tuttavia, currying (parametri separati da spazi) è inoltre comune e supportati anche altri modelli.

Nell'esempio seguente viene illustrata la definizione e utilizzo di un metodo di istanza non astratte.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

All'interno di metodi di istanza, non utilizzare l'autoidentificatore per accedere ai campi definiti tramite associazioni let. Utilizzare l'autoidentificatore per l'accesso ad altri membri e proprietà.


## <a name="static-methods"></a>Metodi statici
La parola chiave `static` viene utilizzata per specificare che un metodo può essere chiamato senza un'istanza e non è associata a un'istanza dell'oggetto. In caso contrario, i metodi sono metodi di istanza.

L'esempio nella sezione successiva mostra i campi dichiarati con la `let` (parola chiave), i membri della proprietà è dichiarata con la `member` (parola chiave) e un metodo statico dichiarato con il `static` (parola chiave).

Nell'esempio seguente viene illustrata la definizione e l'utilizzo di metodi statici. Si presume che queste definizioni di metodo nel `SomeType` classe nella sezione precedente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Metodi virtuali e astratti
La parola chiave `abstract` indica che un metodo dispone di uno slot di distribuzione virtuale e potrebbe non avere una definizione della classe. Oggetto *slot di invio virtuale* è una voce in una tabella gestita internamente di funzioni che è utilizzata in fase di esecuzione per cercare di funzione virtuale chiamate in un tipo di oggetto. Il meccanismo di distribuzione virtuale è il meccanismo che implementa *polimorfismo*, un'importante funzionalità di programmazione orientata a oggetti. È una classe che ha almeno un metodo astratto senza una definizione di un *classe astratta*, il che significa che è possibile creare nessuna istanza di tale classe. Per ulteriori informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).

Le dichiarazioni di metodo astratto non includono un corpo del metodo. Al contrario, il nome del metodo è seguito da due punti (:) e una firma di tipo per il metodo. La firma del tipo di un metodo corrisponde a quello mostrata da IntelliSense quando si posiziona il puntatore del mouse sul nome di un metodo nell'Editor di codice di Visual Studio, ad eccezione senza nomi di parametro. Le firme di tipo vengono visualizzate dall'interprete, fsi.exe, anche quando si lavora in modo interattivo. La firma del tipo di un metodo viene creata elencando i tipi di parametri, seguiti dal tipo restituito, con simboli di separatore appropriato. Parametri sottoposti a currying sono separati da `->` e parametri di tupla sono separati da `*`. Il valore restituito è sempre separato dagli argomenti da un `->` simbolo. Possono utilizzare le parentesi per raggruppare parametri complessi, ad esempio quando un tipo di funzione è un parametro, o per indicare quando una tupla viene considerata come un singolo parametro anziché come due parametri.

È anche possibile assegnare i metodi astratti definizioni predefinite aggiungendo la definizione per la classe e utilizzando il `default` (parola chiave), come mostrato nel blocco di sintassi in questo argomento. Un metodo astratto che dispone di una definizione nella stessa classe è equivalente a un metodo virtuale in altri linguaggi .NET Framework. Se esiste una definizione, il `abstract` (parola chiave) crea un nuovo slot di distribuzione nella tabella di funzioni virtuali per la classe.

Indipendentemente dal fatto che una classe base implementa i metodi astratti, le classi derivate possono fornire le implementazioni dei metodi astratti. Per implementare un metodo astratto in una classe derivata, definire un metodo che presenta lo stesso nome e firma nella classe derivata, ma utilizzare il `override` o `default` (parola chiave) e fornire il corpo del metodo. Le parole chiave `override` e `default` esattamente lo stesso significato. Utilizzare `override` se il nuovo metodo esegue l'override di un'implementazione della classe base; utilizzare `default` quando si crea un'implementazione della stessa classe come astratta dichiarazione originale. Non utilizzare il `abstract` (parola chiave) sul metodo che implementa il metodo che è stato dichiarato nella classe base astratto.

Nell'esempio seguente viene illustrato un metodo astratto `Rotate` che ha un'implementazione predefinita, l'equivalente di un metodo virtuale .NET Framework.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Nell'esempio seguente viene illustrata una classe derivata che esegue l'override di un metodo della classe base. In questo caso, la sostituzione modifica il comportamento in modo che il metodo non esegue alcuna operazione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Metodi di overload
Metodi di overload sono metodi che dispongono di nomi identici in un determinato tipo, ma che dispongono di argomenti diversi. In F #, gli argomenti facoltativi vengono normalmente utilizzati invece i metodi di overload. Metodi di overload, tuttavia, sono consentiti nella lingua, condizione che gli argomenti sono in formato di tupla, non a currying

## <a name="optional-arguments"></a>Argomenti facoltativi

A partire da F # 4.1, è anche possibile argomenti facoltativi con un valore di parametro predefinito nei metodi.  Si tratta per facilitare l'interoperabilità con codice c#.  Nell'esempio seguente viene illustrata la sintassi:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Si noti che il valore passato per `DefaultParameterValue` deve corrispondere al tipo di input.  Nell'esempio precedente, è un `int`.  Il tentativo di passare un valore non intero in `DefaultParameterValue` comporterebbe un errore di compilazione.

## <a name="example-properties-and-methods"></a>Esempio: Proprietà e metodi
Nell'esempio seguente contiene un tipo che include esempi di campi, funzioni private, proprietà e un metodo statico.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Vedere anche
[Membri](index.md)
