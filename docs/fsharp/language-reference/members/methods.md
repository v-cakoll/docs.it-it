---
title: Metodi (F#)
description: 'Informazioni su come un metodo di F # è una funzione associata a un tipo che vengono usate per esporre e implementare le funzionalità e il comportamento degli oggetti e tipi.'
ms.date: 05/16/2016
ms.openlocfilehash: 02d5a7d22d1ce79a06e15462637c373b33623f61
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "44253208"
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

Nella sintassi precedente, è possibile visualizzare le varie forme di definizioni e dichiarazioni di metodo. Nel corpo del metodo più lungo, un'interruzione di riga segue il segno di uguale (=) e l'intero corpo del metodo viene applicato un rientro.

Gli attributi possono essere applicati a qualsiasi dichiarazione di metodo. Essi precedere la sintassi per una definizione di metodo e sono elencati di solito su una riga separata. Per altre informazioni, vedere [Attributi](../attributes.md).

I metodi possono essere contrassegnati `inline`. Per informazioni su `inline`, vedere [Funzioni inline](../functions/inline-functions.md).

I metodi non inline possono essere utilizzato in modo ricorsivo all'interno del tipo; non è necessario usare in modo esplicito il `rec` (parola chiave).

## <a name="instance-methods"></a>Metodi di istanza

Metodi di istanza vengono dichiarati con il `member` parola chiave e un *autoidentificatore*, seguita da un punto (.) e il nome del metodo e i parametri. Come accade per `let` associazioni, il *elenco di parametri* può essere un modello. In genere, racchiuderlo tra (metodo) vengono visualizzati i parametri tra parentesi nel formato di tupla, ovvero i metodi modo F # quando vengono creati in altri linguaggi .NET Framework. Tuttavia, il currying (parametri separati da spazi) è anche comune, e sono supportati anche altri criteri.

L'esempio seguente illustra la definizione e utilizzo di un metodo di istanza non astratta.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

All'interno di metodi di istanza, non usare l'autoidentificatore per accedere ai campi definiti tramite associazioni let. Utilizzare l'autoidentificatore l'accesso ad altri membri e le proprietà.

## <a name="static-methods"></a>Metodi statici

La parola chiave `static` viene usato per specificare che un metodo può essere chiamato senza un'istanza e non è associato a un'istanza dell'oggetto. In caso contrario, i metodi sono metodi di istanza.

L'esempio nella sezione successiva illustra i campi dichiarati con il `let` parola chiave, i membri della proprietà dichiarata con il `member` parola chiave e un metodo statico dichiarata con il `static` (parola chiave).

L'esempio seguente illustra la definizione e l'uso di metodi statici. Si supponga che le definizioni di metodo siano nel `SomeType` classe nella sezione precedente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Metodi virtuali e astratti

La parola chiave `abstract` indica che un metodo dispone di uno slot di distribuzione virtuale e potrebbe non disporre di una definizione della classe. Oggetto *slot di distribuzione virtuale* è una voce in una tabella gestita internamente delle funzioni che è utilizzata in fase di esecuzione per cercare di funzione virtuale chiama in un tipo orientate a oggetti. Il meccanismo di distribuzione virtuale è il meccanismo che implementa *polimorfismo*, una caratteristica importante della programmazione orientata agli oggetti. È una classe che ha almeno un metodo astratto senza una definizione di un *classe astratta*, il che significa che è possibile creare nessuna istanza di tale classe. Per altre informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).

Le dichiarazioni di metodo astratto non includono un corpo del metodo. Al contrario, il nome del metodo è seguito da due punti (:) e una firma di tipo per il metodo. La firma del tipo di un metodo è uguale a quello mostrata da IntelliSense quando si posiziona il puntatore del mouse su un nome di metodo nell'Editor di codice di Visual Studio, ad eccezione senza i nomi dei parametri. Le firme di tipo vengono visualizzate dall'interprete, fsi.exe, anche quando si lavora in modo interattivo. La firma del tipo di un metodo è formata elencando i tipi dei parametri, seguiti dal tipo restituito, con i simboli separatori appropriati. Parametri sottoposti a currying sono separati da `->` e i parametri di tupla sono separati da `*`. Il valore restituito è sempre separato dagli argomenti per un `->` simbolo. Possono utilizzare le parentesi per raggruppare i parametri complessi, ad esempio quando un tipo di funzione è un parametro, o per indicare quando una tupla viene considerata come un singolo parametro anziché come due parametri.

È anche possibile assegnare i metodi astratti definizioni predefinite aggiungendo la definizione per la classe e usato la `default` (parola chiave), come mostrato nel blocco di sintassi in questo argomento. Un metodo astratto con una definizione della stessa classe è equivalente a un metodo virtuale in altri linguaggi .NET Framework. Se esiste una definizione, il `abstract` (parola chiave) crea un nuovo slot di distribuzione nella tabella di funzioni virtuali per la classe.

Indipendentemente dal fatto che una classe base implementa metodi astratti, le classi derivate possono fornire implementazioni dei metodi astratti. Per implementare un metodo astratto in una classe derivata, definire un metodo che ha lo stesso nome e firma nella classe derivata, ad eccezione di usare la `override` o `default` (parola chiave) e specificare il corpo del metodo. Le parole chiave `override` e `default` esattamente lo stesso significato. Usare `override` se il nuovo metodo che esegue l'override di un'implementazione della classe base; usare `default` quando si crea un'implementazione della stessa classe come astratta dichiarazione originale. Non usare il `abstract` (parola chiave) sul metodo che implementa il metodo che è stato dichiarato astratto nella classe di base.

L'esempio seguente illustra un metodo astratto `Rotate` che ha un'implementazione predefinita, l'equivalente di un metodo virtuale di .NET Framework.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Nell'esempio seguente viene illustrata una classe derivata che esegue l'override di un metodo della classe base. In questo caso, la sostituzione viene modificato il comportamento in modo che il metodo non esegue alcuna operazione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Metodi di overload

Metodi di overload sono metodi che dispongono di nomi identici in un determinato tipo, ma che dispongono di argomenti diversi. In F #, gli argomenti facoltativi vengono in genere usati invece i metodi di overload. Tuttavia, i metodi di overload sono consentiti nella lingua, condizione che gli argomenti sono in formato di tupla, non sottoposto a currying.

## <a name="optional-arguments"></a>Argomenti facoltativi

A partire da F # 4.1, è possibile avere anche gli argomenti facoltativi con un valore di parametro predefinito nei metodi.  In modo da facilitare l'interoperabilità con codice c#.  Nell'esempio seguente viene illustrata la sintassi:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Si noti che il valore passato per `DefaultParameterValue` deve corrispondere al tipo di input.  Nell'esempio precedente, è un `int`.  Tentativo di passare un valore diverso da integer in `DefaultParameterValue` comporterebbe un errore di compilazione.

## <a name="example-properties-and-methods"></a>Esempio: Proprietà e metodi

L'esempio seguente contiene un tipo che contiene esempi di campi, funzioni private, le proprietà e un metodo statico.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
