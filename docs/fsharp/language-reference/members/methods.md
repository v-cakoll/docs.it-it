---
title: Metodi
description: Informazioni su come un metodo F è una funzione associata a un tipo utilizzato per esporre e implementare la funzionalità e il comportamento di oggetti e tipi.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400211"
---
# <a name="methods"></a>Metodi

Un *metodo* è una funzione associata a un tipo. Nella programmazione orientata agli oggetti, i metodi vengono utilizzati per esporre e implementare la funzionalità e il comportamento di oggetti e tipi.

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

## <a name="remarks"></a>Osservazioni

Nella sintassi precedente, è possibile visualizzare le varie forme di dichiarazioni e definizioni di metodo. Nei corpi di metodo più lunghi, un'interruzione di riga segue il segno di uguale (-) e l'intero corpo del metodo è rientrato.

Gli attributi possono essere applicati a qualsiasi dichiarazione di metodo. Precedono la sintassi per una definizione di metodo e sono in genere elencati in una riga separata. Per altre informazioni, vedere [Attributi](../attributes.md).

I metodi `inline`possono essere contrassegnati con . Per informazioni su `inline`, vedere [Funzioni inline](../functions/inline-functions.md).

I metodi non inline possono essere utilizzati in modo ricorsivo all'interno del tipo; non è necessario utilizzare `rec` in modo esplicito la parola chiave.

## <a name="instance-methods"></a>Metodi di istanza

I metodi di `member` istanza vengono dichiarati con la parola chiave e un *autoidentificatore*, seguiti da un punto (.) e dal nome del metodo e dai parametri. Come nel caso `let` delle associazioni, l'elenco *di parametri* può essere un modello. In genere, i parametri del metodo vengono racchiusi tra parentesi in un formato di tupla, ovvero il modo in cui i metodi vengono visualizzati in F , quando vengono creati in altri linguaggi .NET Framework. Tuttavia, anche la forma sottoposta a curryle (parametri separati da spazi) è comune e sono supportati anche altri modelli.

Nell'esempio seguente vengono illustrati la definizione e l'utilizzo di un metodo di istanza non astratto.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

All'interno dei metodi di istanza, non utilizzare l'autoidentificatore per accedere ai campi definiti utilizzando let associazioni. Utilizzare l'autoidentificatore quando si accede ad altri membri e proprietà.

## <a name="static-methods"></a>Metodi statici

La `static` parola chiave viene utilizzata per specificare che un metodo può essere chiamato senza un'istanza e non è associato a un'istanza dell'oggetto. In caso contrario, i metodi sono metodi di istanza.

L'esempio nella sezione successiva mostra `let` i campi dichiarati `member` con la parola chiave `static` , i membri di proprietà dichiarati con la parola chiave e un metodo statico dichiarato con la parola chiave .

Nell'esempio seguente vengono illustrati la definizione e l'utilizzo di metodi statici. Si supponga che queste `SomeType` definizioni di metodo sono nella classe nella sezione precedente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Metodi virtuali e astratti

La `abstract` parola chiave indica che un metodo dispone di uno slot di invio virtuale e potrebbe non avere una definizione nella classe. Uno slot di *invio virtuale* è una voce in una tabella di funzioni gestita internamente utilizzata in fase di esecuzione per cercare chiamate di funzione virtuale in un tipo orientato agli oggetti. Il meccanismo di invio virtuale è il meccanismo che implementa il *polimorfismo,* una caratteristica importante della programmazione orientata agli oggetti. Una classe che dispone di almeno un metodo astratto senza una definizione è una *classe astratta*, il che significa che non è possibile creare alcuna istanza di tale classe. Per ulteriori informazioni sulle classi astratte, vedere [Classi astratte](../abstract-classes.md).

Le dichiarazioni di metodi astratti non includono un corpo del metodo. Al contrario, il nome del metodo è seguito da due punti (:) e una firma del tipo per il metodo. La firma del tipo di un metodo è uguale a quella visualizzata da IntelliSense quando si posiziona il puntatore del mouse sul nome di un metodo nell'editor di codice di Visual Studio, ad eccezione dei nomi di parametro. Le firme di tipo vengono visualizzate anche dall'interprete, fsi.exe, quando si lavora in modo interattivo. La firma del tipo di un metodo viene formata elencando i tipi dei parametri, seguiti dal tipo restituito, con i simboli di separatore appropriati. I parametri sottoposti a `->` curryè sono separati `*`da e i parametri della tupla sono separati da . Il valore restituito è sempre separato `->` dagli argomenti da un simbolo. Le parentesi possono essere usate per raggruppare parametri complessi, ad esempio quando un tipo di funzione è un parametro, o per indicare quando una tupla viene considerata come un singolo parametro anziché come due parametri.

È inoltre possibile assegnare definizioni predefinite ai metodi `default` astratti aggiungendo la definizione alla classe e usando la parola chiave , come illustrato nel blocco di sintassi in questo argomento. Un metodo astratto con una definizione nella stessa classe è equivalente a un metodo virtuale in altri linguaggi .NET Framework. Indipendentemente dal fatto che `abstract` esista o meno una definizione, la parola chiave crea un nuovo slot di invio nella tabella delle funzioni virtuali per la classe.

Indipendentemente dal fatto che una classe base implementa i relativi metodi astratti, le classi derivate possono fornire implementazioni di metodi astratti. Per implementare un metodo astratto in una classe derivata, definire un metodo `override` con `default` lo stesso nome e la stessa firma nella classe derivata, ad eccezione di utilizzare la parola chiave o e fornire il corpo del metodo. Le `override` parole `default` chiave e significano esattamente la stessa cosa. Utilizzare `override` se il nuovo metodo esegue l'override di un'implementazione della classe base; utilizzare `default` quando si crea un'implementazione nella stessa classe della dichiarazione astratta originale. Non utilizzare `abstract` la parola chiave sul metodo che implementa il metodo dichiarato abstract nella classe base.

Nell'esempio seguente viene `Rotate` illustrato un metodo astratto con un'implementazione predefinita, l'equivalente di un metodo virtuale di .NET Framework.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

Nell'esempio seguente viene illustrata una classe derivata che esegue l'override di un metodo della classe base. In questo caso, l'override modifica il comportamento in modo che il metodo non eseda alcuna operazione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Metodi di overload

I metodi di overload sono metodi con nomi identici in un determinato tipo ma con argomenti diversi. In F , gli argomenti facoltativi vengono in genere utilizzati al posto dei metodi di overload. Tuttavia, i metodi di overload sono consentiti nel linguaggio, a condizione che gli argomenti siano in formato tupla, non sottoposti a curryazione.

## <a name="optional-arguments"></a>Argomenti facoltativi

A partire dalla versione 4.1, è anche possibile avere argomenti facoltativi con un valore di parametro predefinito nei metodi.  In questo modo è possibile facilitare l'interoperabilità con il codice di C.  Nell'esempio seguente viene illustrata la sintassi:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Si noti che `DefaultParameterValue` il valore passato per deve corrispondere al tipo di input.  Nell'esempio precedente, è `int`un file .  Il tentativo di passare un `DefaultParameterValue` valore non intero in genererebbe un errore di compilazione.

## <a name="example-properties-and-methods"></a>Esempio: Proprietà e metodi

L'esempio seguente contiene un tipo che contiene esempi di campi, funzioni private, proprietà e un metodo statico.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
