---
title: Ereditarietà
description: Informazioni su come specificare F# relazioni di ereditarietà usando la parola chiave ' Inherit '.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627661"
---
# <a name="inheritance"></a>Ereditarietà

L'ereditarietà viene utilizzata per modellare la relazione "is-a" o la sottotipizzazione nella programmazione orientata a oggetti.

## <a name="specifying-inheritance-relationships"></a>Specifica di relazioni di ereditarietà

È possibile specificare relazioni di ereditarietà usando `inherit` la parola chiave in una dichiarazione di classe. Nell'esempio seguente viene illustrato il formato sintattico di base.

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

Una classe può avere al massimo una classe di base diretta. Se non si specifica una classe base tramite la `inherit` parola chiave, la classe eredita in modo implicito da. `System.Object`

## <a name="inherited-members"></a>Membri ereditati

Se una classe eredita da un'altra classe, i metodi e i membri della classe di base sono disponibili per gli utenti della classe derivata come se fossero membri diretti della classe derivata.

Tutte le associazioni let e i parametri del costruttore sono privati a una classe e, pertanto, non è possibile accedervi dalle classi derivate.

La parola `base` chiave è disponibile nelle classi derivate e fa riferimento all'istanza della classe di base. Viene usato come l'identificatore automatico.

## <a name="virtual-methods-and-overrides"></a>Metodi e sostituzioni virtuali

I metodi e le proprietà virtuali funzionano in modo diverso F# in rispetto ad altri linguaggi .NET. Per dichiarare un nuovo membro virtuale, usare la `abstract` parola chiave. Questa operazione viene eseguita indipendentemente dal fatto che venga fornita un'implementazione predefinita per il metodo. Quindi, una definizione completa di un metodo virtuale in una classe base segue questo modello:

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

In una classe derivata, un override di questo metodo virtuale segue questo modello:

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

Se si omette l'implementazione predefinita nella classe di base, la classe di base diventa una classe astratta.

Nell'esempio di codice seguente viene illustrata la dichiarazione di un nuovo `function1` metodo virtuale in una classe di base e come eseguire l'override in una classe derivata.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a>Costruttori ed ereditarietà

Il costruttore per la classe base deve essere chiamato nella classe derivata. Gli argomenti per il costruttore della classe base vengono visualizzati nell'elenco di argomenti `inherit` nella clausola. I valori usati devono essere determinati dagli argomenti forniti al costruttore della classe derivata.

Il codice seguente illustra una classe base e una classe derivata, in cui la classe derivata chiama il costruttore della classe base nella clausola inherit:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

Nel caso di più costruttori, è possibile usare il codice seguente. La prima riga dei costruttori della classe derivata è la `inherit` clausola e i campi vengono visualizzati come campi espliciti dichiarati con la `val` parola chiave. Per ulteriori informazioni, vedere [campi espliciti: `val` Parola chiave](./members/explicit-fields-the-val-keyword.md).

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

Nei casi in cui è necessaria una modifica secondaria di un tipo, è consigliabile utilizzare un'espressione di oggetto come alternativa all'ereditarietà. Nell'esempio seguente viene illustrato l'utilizzo di un'espressione di oggetto come alternativa alla creazione di un nuovo tipo derivato:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

Per ulteriori informazioni sulle espressioni di oggetto, vedere [espressioni di oggetti](object-expressions.md).

Quando si creano gerarchie di oggetti, è consigliabile utilizzare un'unione discriminata anziché l'ereditarietà. Le unioni discriminate possono anche modellare un comportamento variegato di oggetti diversi che condividono un tipo globale comune. Una singola unione discriminata può spesso eliminare la necessità di una serie di classi derivate che sono varianti secondarie. Per informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).

## <a name="see-also"></a>Vedere anche

- [Espressioni di oggetto](object-expressions.md)
- [Riferimenti per il linguaggio F#](index.md)
