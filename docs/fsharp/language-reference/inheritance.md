---
title: Ereditarietà
description: Informazioni su come specificare le relazioni di ereditarietà di F, usando la parola chiave 'inherit'.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400288"
---
# <a name="inheritance"></a>Ereditarietà

L'ereditarietà viene utilizzata per modellare la relazione "è-a", o sottotipi, nella programmazione orientata agli oggetti.

## <a name="specifying-inheritance-relationships"></a>Specifica delle relazioni di ereditarietàSpecifying Inheritance Relationships

È possibile specificare `inherit` le relazioni di ereditarietà utilizzando la parola chiave in una dichiarazione di classe. La forma sintattica di base è illustrata nell'esempio seguente.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Una classe può avere al massimo una classe base diretta. Se non si specifica una classe `inherit` base utilizzando la parola `System.Object`chiave , la classe eredita in modo implicito da .

## <a name="inherited-members"></a>Membri ereditati

Se una classe eredita da un'altra classe, i metodi e i membri della classe base sono disponibili per gli utenti della classe derivata come se fossero membri diretti della classe derivata.

Le associazioni let e i parametri del costruttore sono privati per una classe e, pertanto, non sono accessibili dalle classi derivate.

La `base` parola chiave è disponibile nelle classi derivate e fa riferimento all'istanza della classe base. Viene utilizzato come l'autoidentificatore.

## <a name="virtual-methods-and-overrides"></a>Metodi virtuali ed overrideVirtual Methods and Overrides

I metodi virtuali (e le proprietà) funzionano in modo leggermente diverso in F , rispetto ad altri linguaggi .NET. Per dichiarare un nuovo membro `abstract` virtuale, utilizzare la parola chiave . Questa operazione viene estratta indipendentemente dal fatto che si fornisca un'implementazione predefinita per tale metodo. Pertanto, una definizione completa di un metodo virtuale in una classe base segue questo modello:Thus a complete definition of a virtual method in a base class follows this pattern:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

E in una classe derivata, un override di questo metodo virtuale segue questo modello:E in a derived class, an override of this virtual method follows this pattern:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Se si oma l'implementazione predefinita nella classe base, la classe base diventa una classe astratta.

Nell'esempio di codice riportato di `function1` seguito viene illustrata la dichiarazione di un nuovo metodo virtuale in una classe base e come eseguirne l'override in una classe derivata.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Costruttori ed ereditarietà

Il costruttore per la classe base deve essere chiamato nella classe derivata. Gli argomenti per il costruttore della classe `inherit` base vengono visualizzati nell'elenco di argomenti nella clausola. I valori utilizzati devono essere determinati dagli argomenti forniti al costruttore della classe derivata.

Nel codice seguente vengono illustrate una classe base e una classe derivata, in cui la classe derivata chiama il costruttore della classe base nella clausola inherit:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Nel caso di più costruttori, è possibile utilizzare il codice seguente. La prima riga dei costruttori `inherit` di classe derivata è la clausola `val` e i campi vengono visualizzati come campi espliciti dichiarati con la parola chiave . Per ulteriori informazioni, vedere [Campi espliciti: `val` parola chiave](./members/explicit-fields-the-val-keyword.md).

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a>Alternative all'ereditarietà

Nei casi in cui è necessaria una modifica minore di un tipo, è consigliabile usare un'espressione oggetto come alternativa all'ereditarietà. Nell'esempio seguente viene illustrato l'utilizzo di un'espressione oggetto come alternativa alla creazione di un nuovo tipo derivato:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Per ulteriori informazioni sulle espressioni di oggetto, vedere [Espressioni oggetto](object-expressions.md).

Quando si creano gerarchie di oggetti, è consigliabile utilizzare un'unione discriminata anziché l'ereditarietà. Le unioni discriminate possono anche modellare il comportamento varia togliendo diversi oggetti che condividono un tipo generale comune. Una singola unione discriminata può spesso eliminare la necessità di un numero di classi derivate che sono variazioni minori l'una dell'altra. Per informazioni sulle unioni discriminate, vedere [Unioni discriminate](discriminated-unions.md).

## <a name="see-also"></a>Vedere anche

- [Espressioni di oggetto](object-expressions.md)
- [Guida di riferimento al linguaggio F](index.md)
