---
title: Ereditarietà (C#)
description: Informazioni su come specificare relazioni di ereditarietà F# usando la parola chiave 'inherit'.
ms.date: 05/16/2016
ms.openlocfilehash: e4d79244fb9bada5db0c5c4c7179d4bfe6e21f3d
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43864469"
---
# <a name="inheritance"></a>Ereditarietà

Ereditarietà viene usata per modellare la relazione "is-a", o definizione dei sottotipi nella programmazione orientata agli oggetti.

## <a name="specifying-inheritance-relationships"></a>Specifica di relazioni di ereditarietà

Specificare le relazioni di ereditarietà utilizzando la `inherit` parola chiave in una dichiarazione di classe. La forma sintattica di base è illustrata nell'esempio seguente.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Una classe può avere al massimo una classe base diretta. Se non si specifica una classe di base usando la `inherit` parola chiave, la classe eredita in modo implicito da `System.Object`.

## <a name="inherited-members"></a>Membri ereditati

Se una classe eredita da un'altra classe, i metodi e membri della classe di base sono disponibili per gli utenti della classe derivata come se fossero membri diretti della classe derivata.

Le associazioni let e i parametri del costruttore sono privati per una classe e, pertanto, non sono accessibile dalle classi derivate.

La parola chiave `base` è disponibile nelle classi derivate e fa riferimento all'istanza della classe base. Viene usato come identificatore Self-Service.

## <a name="virtual-methods-and-overrides"></a>Le sostituzioni e metodi virtuali

Metodi virtuali (e proprietà) funzionano in modo diverso in F# rispetto a altri linguaggi .NET. Per dichiarare un nuovo membro virtuale, Usa il `abstract` (parola chiave). A tale scopo, indipendentemente dal fatto che è fornire un'implementazione predefinita per il metodo. In questo modo una definizione completa di un metodo virtuale in una classe di base segue questo modello:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

E in una classe derivata, un override di questo metodo virtuale segue questo modello:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Se si omette l'implementazione predefinita della classe base, la classe di base diventa una classe astratta.

L'esempio di codice seguente illustra la dichiarazione di un nuovo metodo virtuale `function1` in una classe di base e su come eseguirne l'override in una classe derivata.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Costruttori ed ereditarietà

Il costruttore per la classe di base deve essere chiamato nella classe derivata. Gli argomenti per il costruttore di classe di base vengono visualizzati nell'elenco di argomenti in di `inherit` clausola. I valori utilizzati devono essere determinati dagli argomenti forniti al costruttore della classe derivata.

Il codice seguente illustra una classe di base e una classe derivata, in cui la classe derivata chiama il costruttore di classe di base nella clausola eredita:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Nel caso di più costruttori, il codice seguente può essere utilizzato. La prima riga dei costruttori di classe derivata è il `inherit` clausola e i campi vengono visualizzati come campi espliciti che vengono dichiarati con la `val` (parola chiave). Per altre informazioni, vedere [i campi espliciti: il `val` parola chiave](members/explicit-fields-the-val-keyword.md).

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

Nei casi in cui è necessaria una modifica secondaria di un tipo, è consigliabile usare un'espressione di oggetto come un'alternativa all'ereditarietà. Nell'esempio seguente viene illustrato l'utilizzo di un'espressione di oggetto come alternativa alla creazione di un nuovo tipo derivato:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Per altre informazioni sulle espressioni di oggetto, vedere [espressioni di oggetto](object-expressions.md).

Quando si siano creando gerarchie di oggetti, utilizzare un'unione discriminata invece dell'ereditarietà. Le unioni discriminate possono anche comportamento del modello consentono di variare di diversi oggetti che condividono un tipo globale comune. Un'unione discriminata singola spesso possa eliminare la necessità di un numero di classi derivate che si lievi variazioni tra loro. Per informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).

## <a name="see-also"></a>Vedere anche

- [Espressioni di oggetto](object-expressions.md)
- [Riferimenti per il linguaggio F#](index.md)
