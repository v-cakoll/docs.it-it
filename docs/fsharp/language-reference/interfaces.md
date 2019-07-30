---
title: Interfacce
description: Informazioni su F# come le interfacce specificano i set di membri correlati che altre classi implementano.
ms.date: 05/16/2016
ms.openlocfilehash: 8f054a668ad0fbc2453a45883e8052471280eca3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627656"
---
# <a name="interfaces"></a>Interfacce

Le *interfacce* specificano set di membri correlati implementati da altre classi.

## <a name="syntax"></a>Sintassi

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a>Note

Le dichiarazioni di interfaccia sono simili alle dichiarazioni di classe, ad eccezione del fatto che nessun membro viene implementato. Al contrario, tutti i membri sono astratti, come indicato dalla `abstract`parola chiave. Non viene fornito il corpo di un metodo per i metodi astratti. Tuttavia, è possibile fornire un'implementazione predefinita includendo anche una definizione separata del membro come metodo insieme alla `default` parola chiave. Questa operazione equivale alla creazione di un metodo virtuale in una classe base in altri linguaggi .NET. Questo metodo virtuale può essere sottoposto a override nelle classi che implementano l'interfaccia.

L'accessibilità predefinita per le `public`interfacce è.

Facoltativamente, è possibile assegnare un nome a ogni parametro di F# metodo usando la sintassi normale:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

Nell'esempio precedente `ISprintable` , il `Print` metodo dispone di un solo parametro del tipo `string` con il nome `format`.

Esistono due modi per implementare le interfacce: usando le espressioni di oggetto e usando i tipi di classe. In entrambi i casi, il tipo di classe o l'espressione di oggetto fornisce corpi del metodo per i metodi astratti dell'interfaccia. Le implementazioni sono specifiche per ogni tipo che implementa l'interfaccia. Pertanto, i metodi di interfaccia su tipi diversi potrebbero essere diversi tra loro.

Le parole `interface` chiave `end`e, che contrassegnano l'inizio e la fine della definizione, sono facoltative quando si usa la sintassi Lightweight. Se non si utilizzano queste parole chiave, il compilatore tenta di dedurre se il tipo è una classe o un'interfaccia analizzando i costrutti utilizzati. Se si definisce un membro o si utilizza un'altra sintassi della classe, il tipo viene interpretato come una classe.

Lo stile di codifica .NET prevede l'avvio di tutte le interfacce `I`con una maiuscola.

## <a name="implementing-interfaces-by-using-class-types"></a>Implementazione di interfacce tramite tipi di classe

È possibile implementare una o più interfacce in un tipo di classe usando la `interface` parola chiave, il nome dell'interfaccia e la `with` parola chiave, seguita dalle definizioni dei membri di interfaccia, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Le implementazioni dell'interfaccia vengono ereditate, pertanto le classi derivate non devono essere reimplementate.

## <a name="calling-interface-methods"></a>Chiamata di metodi di interfaccia

I metodi di interfaccia possono essere chiamati solo tramite l'interfaccia, non tramite alcun oggetto del tipo che implementa l'interfaccia. Quindi, potrebbe essere necessario eseguire il cast al tipo di interfaccia usando l' `:>` operatore o l' `upcast` operatore per chiamare questi metodi.

Per chiamare il metodo di interfaccia quando si dispone di un oggetto `SomeClass`di tipo, è necessario eseguire il cast dell'oggetto al tipo di interfaccia, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

In alternativa, è possibile dichiarare un metodo sull'oggetto che esegue il cast e chiama il metodo di interfaccia, come nell'esempio seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementazione di interfacce tramite espressioni di oggetto

Le espressioni di oggetto forniscono un metodo breve per implementare un'interfaccia. Sono utili quando non è necessario creare un tipo denominato e si vuole solo un oggetto che supporta i metodi di interfaccia, senza metodi aggiuntivi. Nel codice seguente viene illustrata un'espressione di oggetto.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>Ereditarietà dell'interfaccia

Le interfacce possono ereditare da una o più interfacce di base.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Espressioni di oggetto](object-expressions.md)
- [Classi](classes.md)
