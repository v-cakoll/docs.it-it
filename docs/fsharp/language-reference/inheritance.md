---
title: Ereditarietà (C#)
description: "Informazioni su come specificare relazioni di ereditarietà F # utilizzando la parola chiave 'inherit'."
ms.date: 05/16/2016
ms.openlocfilehash: 3d0c0785fc595315a8283979b99d0ec4fc5cbc0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="inheritance"></a>Ereditarietà

Ereditarietà viene utilizzata per modellare la relazione "è-a", o definizione di sottotipo, nella programmazione orientata a oggetti.


## <a name="specifying-inheritance-relationships"></a>Specificare le relazioni di ereditarietà
Specificare le relazioni di ereditarietà utilizzando il `inherit` parola chiave in una dichiarazione di classe. Il formato di sintassi di base è illustrato nell'esempio seguente.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Una classe può avere al massimo una classe base diretta. Se non si specifica una classe di base utilizzando il `inherit` (parola chiave), la classe eredita in modo implicito da `System.Object`.


## <a name="inherited-members"></a>Membri ereditati
Se una classe eredita da un'altra classe, i metodi e membri della classe di base sono disponibili per gli utenti della classe derivata, come se fossero membri diretti della classe derivata.

Le associazioni let e i parametri del costruttore sono privati per una classe e, pertanto, non è possibile accedere dalle classi derivate.

La parola chiave `base` è disponibile nelle classi derivate e fa riferimento all'istanza della classe base. Viene utilizzato come identificatore Self-Service.


## <a name="virtual-methods-and-overrides"></a>Metodi virtuali e override
Metodi virtuali (e proprietà) funzionano in modo diverso in F # rispetto ai linguaggi .NET. Per dichiarare un nuovo membro virtuale, utilizzare il `abstract` (parola chiave). A tale scopo, indipendentemente dal fatto che venga fornita un'implementazione predefinita per tale metodo. In questo modo una definizione completa di un metodo virtuale in una classe base segue questo modello:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

E in una classe derivata, un override di questo metodo virtuale segue questo modello:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Se si omette l'implementazione predefinita della classe base, la classe di base diventa una classe astratta.

L'esempio di codice seguente illustra la dichiarazione di un nuovo metodo virtuale `function1` in una classe di base e come eseguirne l'override in una classe derivata.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a>Costruttori ed ereditarietà
Il costruttore per la classe di base deve essere chiamato nella classe derivata. Gli argomenti del costruttore di classe di base sono visualizzati nell'elenco di argomenti in di `inherit` clausola. I valori utilizzati devono essere determinati in base agli argomenti forniti al costruttore della classe derivata.

Il codice seguente illustra una classe di base e una classe derivata, in cui la classe derivata chiama il costruttore di classe di base nella clausola inherit:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Nel caso di più costruttori, è possibile utilizzare il codice seguente. È la prima riga dei costruttori di classe derivata di `inherit` clausola e i campi vengono visualizzati come campi espliciti dichiarati con la `val` (parola chiave). Per ulteriori informazioni, vedere [campi espliciti: il `val` parola chiave](members/explicit-fields-the-val-keyword.md).

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
Nei casi in cui una piccola modifica di un tipo è obbligatoria, considerare l'uso di un'espressione di oggetto come alternativa all'ereditarietà. Nell'esempio seguente viene illustrato l'utilizzo di un'espressione di oggetto come alternativa alla creazione di un nuovo tipo derivato:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Per ulteriori informazioni sulle espressioni di oggetto, vedere [espressioni di oggetto](object-expressions.md).

Durante la creazione di gerarchie di oggetti, considerare l'utilizzo di un'unione discriminata invece dell'ereditarietà. Unioni discriminate possono modellare variato comportamenti di oggetti diversi che condividono un tipo globale comune. Una singola unione discriminata consente spesso di eliminare la necessità di un numero di classi derivate che sono alcune piccole variazioni di altra. Per informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).


## <a name="see-also"></a>Vedere anche
[Espressioni di oggetto](object-expressions.md)

[Riferimenti per il linguaggio F#](index.md)
