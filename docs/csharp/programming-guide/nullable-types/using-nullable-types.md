---
title: Utilizzo di tipi di valore C# Nullable-Guida alla programmazione
ms.custom: seodec18
description: Informazioni su come usare i C# tipi di valore Nullable
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396171"
---
# <a name="using-nullable-value-types-c-programming-guide"></a>Utilizzo di tipi di valoreC# Nullable (Guida per programmatori)

I tipi di valore nullable sono tipi che rappresentano tutti i valori di un tipo di valore sottostante `T` e un valore [null](../../language-reference/keywords/null.md) aggiuntivo. Per ulteriori informazioni, vedere l'argomento [tipi di valore Nullable](index.md) .

> [!NOTE]
> C#8,0 introduce la funzionalità dei tipi di riferimento Nullable. Per altre informazioni, vedere [tipi di riferimento Nullable](../../nullable-references.md). I tipi di valore nullable sono disponibili a C# partire da 2.

È possibile fare riferimento a un tipo di valore nullable in uno dei seguenti formati intercambiabili: `Nullable<T>` o `T?`. `T` deve essere un tipo valore.

## <a name="declaration-and-assignment"></a>Dichiarazione e assegnazione

Poiché un tipo di valore può essere convertito in modo implicito nel tipo di valore nullable corrispondente, assegnare un valore a un tipo nullable come per il tipo di valore sottostante. È anche possibile assegnare il valore `null`. Esempio:

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>Esame di un valore di tipo nullable

Usare le proprietà di sola lettura seguenti per esaminare un'istanza di un tipo di valore Nullable per null e recuperare un valore di un tipo sottostante:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica se un'istanza di un tipo nullable contiene un valore del relativo tipo sottostante.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ottiene il valore di un tipo sottostante se <xref:System.Nullable%601.HasValue%2A> è `true`. Se <xref:System.Nullable%601.HasValue%2A> è `false`, la proprietà <xref:System.Nullable%601.Value%2A> genera un'eccezione <xref:System.InvalidOperationException>.

Il codice nell'esempio seguente usa la proprietà `HasValue` per verificare se la variabile contiene un valore prima di visualizzarla:

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

È anche possibile confrontare una variabile di un tipo di valore nullable con `null` invece di usare la proprietà `HasValue`, come illustrato nell'esempio seguente:

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

A partire C# da 7,0, è possibile usare i [criteri](../../pattern-matching.md) di ricerca per esaminare e ottenere un valore di un tipo di valore Nullable:

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Conversione da un tipo di valore Nullable a un tipo sottostante

Se è necessario assegnare un valore di un tipo di valore Nullable a un tipo non nullable, usare l'operatore di Unione [null `??`](../../language-reference/operators/null-coalescing-operator.md) per specificare il valore da assegnare se un valore di un tipo di valore Nullable è null. è anche possibile usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> per eseguire questa operazione. :

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di un tipo di valore Nullable è `null` deve essere il valore predefinito del tipo di valore sottostante.

È possibile eseguire il cast esplicito di un tipo di valore Nullable a un tipo non nullable. Esempio:

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

In fase di esecuzione, se il valore di un tipo di valore Nullable è `null`, il cast esplicito genera un'<xref:System.InvalidOperationException>.

Un tipo valore non nullable viene convertito in modo implicito nel tipo nullable corrispondente.

## <a name="operators"></a>Operatori

Gli operatori unari e binari predefiniti e tutti gli operatori definiti dall'utente esistenti per i tipi di valore possono essere utilizzati anche dai tipi nullable corrispondenti. Questi operatori producono `null` se uno o entrambi gli operandi sono `null`; in caso contrario, l'operatore utilizza i valori contenuti per calcolare il risultato. Esempio:

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> Per il tipo `bool?`, gli operatori `&` e `|` predefiniti non seguono le regole descritte in questa sezione: il risultato di una valutazione dell'operatore può essere diverso da null anche se uno degli operandi è `null`. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../../language-reference/operators/boolean-logical-operators.md).
  
Per gli operatori relazionali (`<`, `>`, `<=`, `>=`), se uno o entrambi gli operandi sono `null`, il risultato sarà `false`. Non presupporre che poiché un particolare confronto (ad esempio, `<=`) restituisce `false`, il confronto opposto (`>`) restituisce `true`. L'esempio seguente mostra che 10

- non è maggiore o uguale a `null`,
- né minore di `null`.

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

Nell'esempio precedente viene inoltre illustrato che un confronto di uguaglianza tra due tipi valore nullable che sono entrambi null restituisce `true`.

Per altre informazioni, vedere la sezione [Operatori elevati](~/_csharplang/spec/expressions.md#lifted-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="boxing-and-unboxing"></a>Boxing e unboxing

Un tipo valore nullable viene sottoposto a [boxing](../types/boxing-and-unboxing.md) in base alle regole seguenti:

- Se <xref:System.Nullable%601.HasValue%2A> restituisce `false`, viene prodotto il riferimento Null.
- Se <xref:System.Nullable%601.HasValue%2A> restituisce `true`, viene sottoposto a boxing un valore del tipo valore sottostante `T` e non l'istanza di <xref:System.Nullable%601>.

È possibile eseguire la conversione unboxing del tipo valore sottoposto a boxing nel tipo nullable corrispondente, come illustrato nell'esempio seguente:

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a>Vedere anche

- [Tipi valore nullable](index.md)
- [Cosa significa esattamente "elevato"?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
