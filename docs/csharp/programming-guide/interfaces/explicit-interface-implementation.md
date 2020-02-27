---
title: Implementazione esplicita dell'interfaccia - Guida per programmatori C#
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628150"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementazione esplicita dell'interfaccia (Guida per programmatori C#)

Se [class](../../language-reference/keywords/class.md) implementa due interfacce che contengono un membro con la stessa firma e quest'ultimo viene implementato nella classe, entrambe le interfacce useranno il membro come propria implementazione. Nell'esempio seguente tutte le chiamate a `Paint` richiamano lo stesso metodo. Il primo esempio definisce i tipi:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

Nell'esempio seguente vengono chiamati i metodi:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

Quando due membri di interfaccia non eseguono la stessa funzione, comporta un'implementazione non corretta di una o entrambe le interfacce. È possibile implementare un membro di interfaccia in modo esplicito, creando un membro della classe che viene chiamato solo tramite l'interfaccia ed è specifico di tale interfaccia. Denominare il membro della classe con il nome dell'interfaccia e un punto. Ad esempio,

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

Il membro di classe `IControl.Paint` è disponibile solo tramite l'interfaccia`IControl` e `ISurface.Paint` è disponibile solo tramite `ISurface`. Entrambe le implementazioni dei metodi sono separate e nessuna delle due è disponibile direttamente nella classe. Ad esempio,

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

L'implementazione esplicita viene usata anche per risolvere i casi in cui due interfacce dichiarano membri diversi con lo stesso nome, ad esempio una proprietà e un metodo. Per implementare entrambe le interfacce, una classe deve usare l'implementazione esplicita per la proprietà `P`o il metodo `P`, o entrambi, per evitare un errore del compilatore. Ad esempio,

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

Se una classe eredita un'implementazione del metodo da un'interfaccia, il metodo è accessibile solo tramite un riferimento del tipo di interfaccia. Il membro ereditato non viene visualizzato come parte dell'interfaccia pubblica. Nell'esempio seguente viene definita un'implementazione predefinita per un metodo di interfaccia:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

Nell'esempio seguente viene richiamata l'implementazione predefinita:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

Qualsiasi classe che implementa l'interfaccia `IControl` può eseguire l'override del metodo `Paint` predefinito, sia come metodo pubblico, che come implementazione esplicita dell'interfaccia.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](../classes-and-structs/index.md)
- [Interfacce](./index.md)
- [Ereditarietà](../classes-and-structs/inheritance.md)
