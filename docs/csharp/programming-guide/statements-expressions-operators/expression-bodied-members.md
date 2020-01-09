---
title: Membri con corpo di espressione - Guida per programmatori C#
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711987"
---
# <a name="expression-bodied-members-c-programming-guide"></a>Membri con corpo di espressione (Guida per programmatori C#)

Le definizioni dei corpi di espressione consentono di eseguire l'implementazione di un membro in un modulo molto conciso e leggibile. È possibile usare una definizione di corpo di espressione ogni volta che la logica per un membro supportato, ad esempio un metodo o proprietà, è costituita da un'unica espressione. Una definizione di corpo di espressione presenta la seguente sintassi generale:

```csharp
member => expression;
```

dove *expression* è un'espressione valida.

Il supporto per le definizioni dei corpi di espressione è stato introdotto per i metodi e le proprietà di sola lettura in C# 6 ed è stato ampliato in C# 7.0. Le definizioni dei corpi di espressione possono essere usate con i membri dei tipi elencati nella tabella seguente:

|Member  |Supportato a partire da... |
|---------|---------|
|[Metodo](#methods)  |C# 6 |
|[Proprietà di sola lettura](#read-only-properties)   |C# 6  |
|[Property](#properties)  |C# 7.0 |
|[Costruttore](#constructors)   |C# 7.0 |
|[Finalizzatore](#finalizers)     |C# 7.0 |
|[Indicizzatore](#indexers)       |C# 7.0 |

## <a name="methods"></a>Metodi

Un metodo con corpo di espressione è costituito da una singola espressione che restituisce un valore il cui tipo corrisponde al tipo restituito del metodo oppure, per i metodi che restituiscono `void`, che esegue una determinata operazione. Ad esempio, i tipi che eseguono l'override del metodo <xref:System.Object.ToString%2A> di solito includono una singola espressione che restituisce la rappresentazione di stringa dell'oggetto corrente.

L'esempio seguente definisce una classe `Person` che esegue l'override del metodo <xref:System.Object.ToString%2A> con una definizione di corpo di espressione. Definisce inoltre un metodo `DisplayName` che visualizza un nome nella console. Si noti che la parola chiave `return` non viene usata nella definizione del corpo di espressione `ToString`.

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

Per altre informazioni, vedere [Metodi (Guida per programmatori C#)](../classes-and-structs/methods.md).

## <a name="read-only-properties"></a>Proprietà di sola lettura

A partire da C# 6, è possibile usare una definizione del corpo dell'espressione per implementare una proprietà di sola lettura. A questo scopo, usare la sintassi seguente:

```csharp
PropertyType PropertyName => expression;
```

L'esempio seguente definisce una classe `Location` la cui proprietà `Name` di sola lettura viene implementata come definizione del corpo dell'espressione che restituisce il valore del campo `locationName` privato:

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

Per altre informazioni sulle proprietà, vedere [Proprietà (Guida per programmatori C#)](../classes-and-structs/properties.md).

## <a name="properties"></a>Proprietà

A partire da C# 7.0, è possibile usare definizioni del corpo dell'espressione per implementare la proprietà `get` e le funzioni di accesso `set`. Nell'esempio riportato di seguito viene illustrato come procedere:

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

Per altre informazioni sulle proprietà, vedere [Proprietà (Guida per programmatori C#)](../classes-and-structs/properties.md).

## <a name="constructors"></a>Costruttori

Una definizione di corpo di espressione per un costruttore in genere è costituita da una singola espressione di assegnazione o da una chiamata al metodo che gestisce gli argomenti del costruttore o inizializza lo stato dell'istanza.

L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*. La definizione del corpo dell'espressione assegna l'argomento alla proprietà `Name`.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Per altre informazioni, vedere [Costruttori (Guida per programmatori C#)](../classes-and-structs/constructors.md).

## <a name="finalizers"></a>Finalizzatori

Una definizione di corpo di espressione per un finalizzatore in genere contiene istruzioni di pulitura, ad esempio le istruzioni che rilasciano risorse non gestite.

L'esempio seguente definisce un finalizzatore che usa una definizione di corpo di espressione per indicare che è stato chiamato il finalizzatore.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

Per altre informazioni, vedere [Finalizzatori (Guida per programmatori C#)](../classes-and-structs/destructors.md).

## <a name="indexers"></a>Indexers (Indicizzatori)

Analogamente alle proprietà, le funzioni di accesso Indexer `get` e `set` sono costituite da definizioni del corpo dell'espressione se la funzione di accesso `get` è costituita da una singola espressione che restituisce un valore o la funzione di accesso `set` esegue un'assegnazione semplice.

Nell'esempio seguente viene definita una classe denominata `Sports` che include una matrice <xref:System.String> interna contenente i nomi di alcuni sport. Le funzioni di accesso `get` e `set` dell'indicizzatore sono implementate come definizioni del corpo dell'espressione.

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

Per altre informazioni, vedere [Indicizzatori (Guida per programmatori C#)](../indexers/index.md).
