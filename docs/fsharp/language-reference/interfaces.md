---
title: Interfacce (F#)
description: 'Informazioni su come le interfacce di F # specificare set di membri correlati che implementano le altre classi.'
ms.date: 05/16/2016
ms.openlocfilehash: 174e30c03cd555d2d9c89c88bd80e06a2cdcef46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="interfaces"></a>Interfacce

*Interfacce* specificare set di membri correlati che implementano le altre classi.

## <a name="syntax"></a>Sintassi

```fsharp
// Interface declaration:
[ attributes ]
type interface-name =
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
Le dichiarazioni di interfaccia sono simili alle dichiarazioni di classe, ad eccezione del fatto che non vengono implementati membri. Al contrario, tutti i membri astratti, come indicato dalla parola chiave `abstract`. Non si specifica un corpo del metodo per i metodi astratti. Tuttavia, è possibile fornire un'implementazione predefinita includendo anche una definizione separata del membro come un metodo con il `default` (parola chiave). In questo modo è equivalente alla creazione di un metodo virtuale in una classe base in altri linguaggi .NET. Tale metodo virtuale può essere sottoposto a override nelle classi che implementano l'interfaccia.

È facoltativamente possibile assegnare a ogni parametro del metodo un nome usando la normale sintassi F #:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

Nel precedente `ISprintable` esempio, il `Print` metodo ha un solo parametro di tipo `string` con il nome `format`.

Esistono due modi per implementare le interfacce: tramite espressioni di oggetto e, utilizzando i tipi di classe. In entrambi i casi, l'espressione di tipo o un oggetto di classe fornisce corpi di metodo per i metodi astratti dell'interfaccia. Le implementazioni sono specifiche di ogni tipo che implementa l'interfaccia. Metodi di interfaccia su diversi tipi di conseguenza, potrebbero essere diversi da altro.

Le parole chiave `interface` e `end`, che contrassegna l'inizio e fine della definizione di sono facoltativi quando si utilizza la sintassi leggera. Se non si utilizzano queste parole chiave, il compilatore prova a dedurre se il tipo è una classe o un'interfaccia, analizzando i costrutti in uso. Se si definisce un membro o utilizzare un'altra sintassi di classe, il tipo viene interpretato come una classe.

.NET nello stile di codifica consiste nell'iniziare tutte le interfacce con una lettera maiuscola `I`.


## <a name="implementing-interfaces-by-using-class-types"></a>Implementazione delle interfacce usando i tipi di classe
È possibile implementare una o più interfacce in un tipo di classe utilizzando il `interface` (parola chiave), il nome dell'interfaccia e `with` (parola chiave), seguita dalle definizioni di membro di interfaccia, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

Le implementazioni di interfaccia vengono ereditate, pertanto non è necessario che tutte le classi derivate reimplementare li.


## <a name="calling-interface-methods"></a>Chiamata di metodi di interfaccia
Metodi di interfaccia possono essere chiamati solo tramite l'interfaccia, non tramite qualsiasi oggetto di tipo che implementa l'interfaccia. Di conseguenza, potrebbe essere necessario eseguire l'upcast al tipo di interfaccia utilizzando il `:>` operatore o `upcast` operatore per chiamare questi metodi.

Per chiamare il metodo di interfaccia, quando si dispone di un oggetto di tipo `SomeClass`, è necessario eseguire l'upcast l'oggetto per il tipo di interfaccia, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

Un'alternativa consiste nel dichiarare un metodo sull'oggetto di tale upcasts e chiama il metodo di interfaccia, come nell'esempio seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]
    
## <a name="implementing-interfaces-by-using-object-expressions"></a>Implementazione di interfacce tramite espressioni di oggetto
Espressioni di oggetto consentono di implementare un'interfaccia in modo breve. E sono utili quando non è necessario creare un tipo denominato, e si desidera semplicemente un oggetto che supporta i metodi di interfaccia, senza metodi aggiuntivi. Un'espressione di oggetto come illustrata nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]
    
## <a name="interface-inheritance"></a>Ereditarietà dell'interfaccia
Le interfacce possono ereditare da una o più interfacce base.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]
    
## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Espressioni di oggetto](object-expressions.md)

[Classi](classes.md)
