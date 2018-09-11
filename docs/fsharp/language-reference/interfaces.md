---
title: Interfacce (F#)
description: 'Informazioni su come le interfacce di F # specificare set di membri correlati implementati da altre classi.'
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267271"
---
# <a name="interfaces"></a>Interfacce

*Interfacce* specificare set di membri correlati implementati da altre classi.

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

Le dichiarazioni di interfaccia sono simili alle dichiarazioni di classe, ad eccezione del fatto che nessun membro viene implementato. Al contrario, tutti i membri sono astratti, come indicato dalla parola chiave `abstract`. Non si specifica un corpo del metodo per i metodi astratti. Tuttavia, è possibile fornire un'implementazione predefinita includendo anche una definizione separata del membro come un metodo con il `default` (parola chiave). In questo modo è equivalente alla creazione di un metodo virtuale in una classe di base in altri linguaggi .NET. Tale metodo virtuale può essere sottoposto a override nelle classi che implementano l'interfaccia.

L'accessibilità predefinita per le interfacce è `public`.

È facoltativamente possibile assegnare a ogni parametro del metodo un nome usando la normale sintassi di F #:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

Nell'esempio precedente `ISprintable` esempio, il `Print` metodo ha un solo parametro di tipo `string` con il nome `format`.

Esistono due modi per implementare le interfacce: utilizzando espressioni di oggetto e utilizzando i tipi di classe. In entrambi i casi, l'espressione di tipo o un oggetto classe fornisce i corpi dei metodi per i metodi astratti dell'interfaccia. Le implementazioni sono specifiche per ogni tipo che implementa l'interfaccia. Di conseguenza, i metodi di interfaccia in diversi tipi potrebbero essere diversi da altra.

Le parole chiave `interface` e `end`, sono facoltative che contrassegnano l'inizio e fine della definizione, quando si usa la sintassi leggera. Se non si utilizza queste parole chiave, il compilatore prova a dedurre se il tipo è una classe o un'interfaccia analizzando i costrutti che usi. Se si definisce un membro o altra sintassi di classe, il tipo viene interpretato come una classe.

Stile di codifica .NET consiste nell'iniziare tutte le interfacce con una lettera maiuscola `I`.

## <a name="implementing-interfaces-by-using-class-types"></a>Implementazione delle interfacce usando i tipi di classe

È possibile implementare una o più interfacce in un tipo di classe utilizzando il `interface` parola chiave, il nome dell'interfaccia e il `with` (parola chiave), seguito dalle definizioni del membro di interfaccia, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Le implementazioni dell'interfaccia vengono ereditate, pertanto non è necessario che tutte le classi derivate reimplementare li.

## <a name="calling-interface-methods"></a>Chiamata di metodi di interfaccia

I metodi di interfaccia possono essere chiamati solo tramite l'interfaccia, non tramite qualsiasi oggetto del tipo che implementa l'interfaccia. Di conseguenza, potrebbe essere necessario eseguire l'upcast al tipo di interfaccia usando il `:>` operatore o `upcast` operatore per poter chiamare questi metodi.

Per chiamare il metodo di interfaccia quando si dispone di un oggetto di tipo `SomeClass`, è necessario eseguire l'upcast di oggetto per il tipo di interfaccia, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Un'alternativa consiste nel dichiarare un metodo sull'oggetto tale upcasts e chiama il metodo di interfaccia, come nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementazione delle interfacce usando le espressioni di oggetto

Le espressioni di oggetto forniscono un modo breve per implementare un'interfaccia. Sono utili quando non è necessario creare un tipo denominato, e si desidera semplicemente un oggetto che supporta i metodi di interfaccia senza metodi aggiuntivi. Nel codice seguente è illustrata un'espressione di oggetto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a>Ereditarietà dell'interfaccia

Le interfacce possono ereditare da una o più interfacce di base.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Espressioni di oggetto](object-expressions.md)
- [Classi](classes.md)
