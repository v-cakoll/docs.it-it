---
title: Implementazione esplicita dell'interfaccia - Guida per programmatori C#
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ea32a279b7c464174a7fada5ef93ccf62ef39884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167673"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementazione esplicita dell'interfaccia (Guida per programmatori C#)

Se [class](../../language-reference/keywords/class.md) implementa due interfacce che contengono un membro con la stessa firma e quest'ultimo viene implementato nella classe, entrambe le interfacce useranno il membro come propria implementazione. Nell'esempio seguente tutte le chiamate a `Paint` richiamano lo stesso metodo. Questo primo esempio definisce i tipi:This first sample defines the types:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

Nell'esempio seguente vengono chiamii i metodi:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

Quando due membri di interfaccia non eseguono la stessa funzione, porta a un'implementazione non corretta di una o entrambe le interfacce. È possibile implementare un membro di interfaccia in modo esplicito, creando un membro di classe che viene chiamato solo tramite l'interfaccia ed è specifico di tale interfaccia. Assegnare al membro della classe il nome dell'interfaccia e un punto. Ad esempio:

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

Il membro di classe `IControl.Paint` è disponibile solo tramite l'interfaccia`IControl` e `ISurface.Paint` è disponibile solo tramite `ISurface`. Entrambe le implementazioni del metodo sono separate e nessuna delle due è disponibile direttamente nella classe. Ad esempio:

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

L'implementazione esplicita viene utilizzata anche per risolvere i casi in cui due interfacce dichiarano membri diversi con lo stesso nome, ad esempio una proprietà e un metodo. Per implementare entrambe le interfacce, una classe `P`deve utilizzare `P`un'implementazione esplicita per la proprietà , oppure per il metodo , o entrambe, per evitare un errore del compilatore. Ad esempio:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

A partire dalla [versione 8.0](../../whats-new/csharp-8.md#default-interface-methods)di C, è possibile definire un'implementazione per i membri dichiarati in un'interfaccia. Se una classe eredita un'implementazione del metodo da un'interfaccia, tale metodo è accessibile solo tramite un riferimento del tipo di interfaccia. Il membro ereditato non viene visualizzato come parte dell'interfaccia pubblica. L'esempio seguente definisce un'implementazione predefinita per un metodo di interfaccia:The following sample defines a default implementation for an interface method:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

L'esempio seguente richiama l'implementazione predefinita:The following sample invokes the default implementation:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

Qualsiasi classe che `IControl` implementa l'interfaccia può eseguire l'override del metodo predefinito, `Paint` come metodo pubblico o come implementazione esplicita dell'interfaccia.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](../classes-and-structs/index.md)
- [Interfacce](./index.md)
- [Ereditarietà](../classes-and-structs/inheritance.md)
