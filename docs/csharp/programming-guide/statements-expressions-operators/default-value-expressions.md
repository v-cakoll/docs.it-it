---
title: Espressioni con valore predefinito - Guida per programmatori C#
ms.custom: seodec18
description: Le espressioni con valore predefinito producono il valore predefinito per qualsiasi tipo riferimento o tipo valore
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 4b14714a55f77763425299ffc13ba579ead57810
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237285"
---
# <a name="default-value-expressions-c-programming-guide"></a>espressioni con valore predefinito (guida per programmatori C#)

Un'espressione con valore predefinito `default(T)` produce il valore predefinito per un tipo `T`. La tabella seguente mostra i valori generati per vari tipi:

|Tipo|Valore predefinito|
|---------|---------|
|Qualsiasi tipo riferimento|`null`|
|Tipo di valore numerico|Zero|
|[bool](../../language-reference/keywords/bool.md)|`false`|
|[char](../../language-reference/keywords/char.md)|`'\0'`|
|[enum](../../language-reference/keywords/enum.md)|Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.|
|[struct](../../language-reference/keywords/struct.md)|Valore generato impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.|
|Tipi nullable|Un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita.|

Le espressioni con valore predefinito risultano particolarmente utili nelle classi e nei metodi generici. Un problema relativo all'uso dei metodi generici riguarda l'assegnazione di un valore predefinito a un tipo con parametri `T` quando non è noto quanto segue:

- Se `T` è un tipo riferimento o un tipo valore.
- Se `T` è un tipo valore, se sarà un valore numerico o struct.

 Data una variabile `t` di un tipo con parametri `T`, l'istruzione `t = null` è valida solo se `T` è un tipo riferimento. L'assegnazione `t = 0` funziona solo per i tipi di valore numerico ma non per gli struct. Per risolvere questo problema, usare un valore predefinito:

```csharp
T t = default(T);
```

L'espressione `default(T)` non è limitata a classi e metodi generici. Le espressioni con valore predefinito possono essere usate con qualsiasi tipo gestito. Tutte le espressioni seguenti sono valide:

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 L'esempio seguente dalla classe `GenericList<T>` mostra come usare l'operatore `default(T)` in una classe generica. Per altre informazioni, vedere [Introduzione ai generics](../generics/introduction-to-generics.md).

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>Valore letterale e inferenza del tipo

A partire dalla versione C# 7.1, il valore letterale `default` può essere usato per le espressioni con valore predefinito quando il compilatore è in grado di eseguire l'inferenza del tipo dell'espressione. Il valore letterale `default` produce lo stesso valore dell'equivalente `default(T)` dove `T` è il tipo dedotto. Questo approccio può consentire di rendere più conciso il codice, riducendo la ridondanza dovuta alla dichiarazione ripetuta di un tipo. Il valore letterale `default` può essere usato in una qualsiasi delle posizioni seguenti:

- Inizializzatore di variabile
- assegnazione di variabili
- Dichiarazione del valore predefinito per un parametro facoltativo
- Specifica del valore per l'argomento della chiamata di un metodo
- Istruzione return (o espressione in un membro con corpo di espressione)

L'esempio seguente mostra molti utilizzi del valore letterale `default` in un'espressione con valore predefinito:

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>  
- [Guida per programmatori C#](../index.md)  
- [Generics (Guida per programmatori C#)](../generics/index.md)  
- [Metodi generici](../generics/generic-methods.md)  
- [Generics in .NET](~/docs/standard/generics/index.md)  
- [Tabella dei valori predefiniti](../../language-reference/keywords/default-values-table.md)
