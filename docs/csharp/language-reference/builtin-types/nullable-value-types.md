---
title: Tipi di valore Nullable C# -Reference
description: Informazioni sui C# tipi di valore nullable e su come usarli
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: 9b7a1e7e639608248b4b465bd440247b4061f52e
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239794"
---
# <a name="nullable-value-types-c-reference"></a>Tipi di valore NullableC# (riferimento)

Un *tipo di valore nullable* `T?` rappresenta tutti i valori del [tipo di valore](value-types.md) sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo. Ad esempio, è possibile assegnare uno dei tre valori seguenti a una variabile `bool?`: `true`, `false`o `null`. Un tipo di valore sottostante `T` non può essere un tipo di valore Nullable.

> [!NOTE]
> C#8,0 introduce la funzionalità dei tipi di riferimento Nullable. Per altre informazioni, vedere [tipi di riferimento Nullable](../../nullable-references.md). I tipi di valore nullable sono disponibili a C# partire da 2.

Qualsiasi tipo di valore Nullable è un'istanza della struttura <xref:System.Nullable%601?displayProperty=nameWithType> generica. È possibile fare riferimento a un tipo di valore nullable con un tipo sottostante `T` in uno qualsiasi dei seguenti formati intercambiabili: `Nullable<T>` o `T?`.

Si usa in genere un tipo di valore nullable quando è necessario rappresentare il valore non definito di un tipo di valore sottostante. Una variabile booleana o `bool`, ad esempio, può essere solo `true` o `false`. Tuttavia, in alcune applicazioni un valore di variabile può essere non definito o mancante. Un campo di database, ad esempio, può contenere `true` o `false`, oppure non può contenere alcun valore, ovvero `NULL`. In questo scenario è possibile utilizzare il tipo `bool?`.

## <a name="declaration-and-assignment"></a>Dichiarazione e assegnazione

Poiché un tipo valore è convertibile in modo implicito nel tipo di valore nullable corrispondente, è possibile assegnare un valore a una variabile di un tipo di valore nullable come per il tipo di valore sottostante. È anche possibile assegnare il valore `null`. Ad esempio:

[!code-csharp[declare and assign](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#Declaration)]

Il valore predefinito di un tipo di valore Nullable rappresenta `null`, ovvero un'istanza la cui proprietà <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> restituisce `false`.

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a>Esame di un'istanza di un tipo di valore Nullable

A partire C# da 7,0, è possibile usare l' [operatore`is` con un modello di tipo](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) per esaminare un'istanza di un tipo di valore Nullable per `null` e recuperare un valore di un tipo sottostante:

[!code-csharp-interactive[use pattern matching](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#PatternMatching)]

Per esaminare e ottenere un valore di una variabile di tipo valore Nullable, è sempre possibile usare le proprietà di sola lettura seguenti:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica se un'istanza di un tipo di valore nullable ha un valore del tipo sottostante.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ottiene il valore di un tipo sottostante se <xref:System.Nullable%601.HasValue%2A> è `true`. Se <xref:System.Nullable%601.HasValue%2A> è `false`, la proprietà <xref:System.Nullable%601.Value%2A> genera un'eccezione <xref:System.InvalidOperationException>.

Nell'esempio seguente viene utilizzata la proprietà `HasValue` per verificare se la variabile contiene un valore prima di visualizzarlo:

[!code-csharp-interactive[use HasValue](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#HasValue)]

È anche possibile confrontare una variabile di un tipo di valore nullable con `null` invece di usare la proprietà `HasValue`, come illustrato nell'esempio seguente:

[!code-csharp-interactive[use comparison with null](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Conversione da un tipo di valore Nullable a un tipo sottostante

Se si desidera assegnare un valore di un tipo di valore Nullable a una variabile di tipo valore non nullable, potrebbe essere necessario specificare il valore da assegnare al posto di `null`. Usare l' [operatore di Unione null `??`](../operators/null-coalescing-operator.md) a tale scopo. è anche possibile usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> per lo stesso scopo:

[!code-csharp-interactive[?? operator](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#NullCoalescing)]

Se si desidera utilizzare il valore [predefinito](default-values.md) del tipo di valore sottostante al posto di `null`, utilizzare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>.

È anche possibile eseguire il cast esplicito di un tipo di valore Nullable a un tipo non nullable, come illustrato nell'esempio seguente:

[!code-csharp[explicit cast](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#Cast)]

In fase di esecuzione, se il valore di un tipo di valore Nullable è `null`, il cast esplicito genera un'<xref:System.InvalidOperationException>.

Un tipo di valore non nullable `T` è convertibile in modo implicito nel tipo di valore nullable corrispondente `T?`.

## <a name="lifted-operators"></a>Operatori rimossi

Gli [operatori](../operators/index.md) unari e binari predefiniti o gli operatori di overload supportati da un tipo di valore `T` sono supportati anche dal tipo di valore nullable corrispondente `T?`. Questi operatori, noti anche come *operatori lifted*, producono `null` se uno o entrambi gli operandi sono `null`; in caso contrario, l'operatore utilizza i valori contenuti degli operandi per calcolare il risultato. Ad esempio:

[!code-csharp[lifted operators](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> Per il tipo di `bool?`, gli operatori `&` e `|` predefiniti non seguono le regole descritte in questa sezione: il risultato di una valutazione dell'operatore può essere diverso da null anche se uno degli operandi è `null`. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).

Per gli [operatori di confronto](../operators/comparison-operators.md) `<`, `>`, `<=`e `>=`, se uno o entrambi gli operandi sono `null`, il risultato sarà `false`; in caso contrario, vengono confrontati i valori contenuti degli operandi. Non presupporre che poiché un particolare confronto (ad esempio, `<=`) restituisce `false`, il confronto opposto (`>`) restituisce `true`. L'esempio seguente mostra che 10

- non è maggiore o uguale a `null`
- né minore di `null`

[!code-csharp-interactive[relational and equality operators](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#ComparisonOperators)]

Per l' [operatore di uguaglianza](../operators/equality-operators.md#equality-operator-) `==`, se entrambi gli operandi sono `null`, il risultato viene `true`, se viene `null`solo uno degli operandi, il risultato è `false`; in caso contrario, vengono confrontati i valori contenuti degli operandi.

Per l' [operatore di disuguaglianza](../operators/equality-operators.md#inequality-operator-) `!=`, se entrambi gli operandi sono `null`, il risultato viene `false`, se viene `null`solo uno degli operandi, il risultato è `true`; in caso contrario, vengono confrontati i valori contenuti degli operandi.

Se esiste una [conversione definita dall'utente](../operators/user-defined-conversion-operators.md) tra due tipi di valore, è possibile usare la stessa conversione anche tra i tipi di valore nullable corrispondenti.

## <a name="boxing-and-unboxing"></a>Boxing e unboxing

Un'istanza di un tipo di valore Nullable `T?` viene [boxed](../../programming-guide/types/boxing-and-unboxing.md) come indicato di seguito:

- Se <xref:System.Nullable%601.HasValue%2A> restituisce `false`, viene prodotto il riferimento Null.
- Se <xref:System.Nullable%601.HasValue%2A> restituisce `true`, il valore corrispondente del tipo di valore sottostante `T` è boxed, non l'istanza di <xref:System.Nullable%601>.

È possibile eseguire l'unboxing di un valore boxed di un tipo di valore `T` al tipo di valore nullable corrispondente `T?`, come illustrato nell'esempio seguente:

[!code-csharp-interactive[boxing and unboxing](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a>Come identificare un tipo di valore Nullable

Nell'esempio seguente viene illustrato come determinare se un'istanza di <xref:System.Type?displayProperty=nameWithType> rappresenta un tipo di valore Nullable costruito, ovvero il tipo di <xref:System.Nullable%601?displayProperty=nameWithType> con un parametro di tipo specificato `T`:

[!code-csharp-interactive[whether Type is nullable](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsTypeNullable)]

Come illustrato nell'esempio, è possibile usare l'operatore [typeof](../operators/type-testing-and-cast.md#typeof-operator) per creare un'istanza di <xref:System.Type?displayProperty=nameWithType>.

Per determinare se un'istanza è di un tipo di valore Nullable, non usare il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> per ottenere un'istanza di <xref:System.Type> da testare con il codice precedente. Quando si chiama il metodo <xref:System.Object.GetType%2A?displayProperty=nameWithType> su un'istanza di un tipo di valore Nullable, l'istanza viene sottoposta a [boxing](#boxing-and-unboxing) <xref:System.Object>. Poiché la conversione boxing di un'istanza non null di un tipo di valore Nullable equivale alla conversione boxing di un valore del tipo sottostante, <xref:System.Object.GetType%2A> restituisce un'istanza di <xref:System.Type> che rappresenta il tipo sottostante di un tipo di valore Nullable:

[!code-csharp-interactive[GetType example](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#GetType)]

Inoltre, non usare l'operatore [is](../operators/type-testing-and-cast.md#is-operator) per determinare se un'istanza è un tipo di valore Nullable. Come illustrato nell'esempio seguente, non è possibile distinguere i tipi di un'istanza del tipo di valore nullable e l'istanza del tipo sottostante con l'operatore `is`:

[!code-csharp-interactive[is operator example](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsOperator)]

È possibile utilizzare il codice presentato nell'esempio seguente per determinare se un'istanza è un tipo di valore Nullable:

[!code-csharp-interactive[whether an instance is of a nullable type](~/samples/snippets/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> I metodi descritti in questa sezione non sono applicabili in caso di [tipi di riferimento Nullable](../../nullable-references.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi nullable](~/_csharplang/spec/types.md#nullable-types)
- [Operatori rimossi](~/_csharplang/spec/expressions.md#lifted-operators)
- [Conversioni implicite Nullable](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [Conversioni esplicite Nullable](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [Operatori di conversione accurati](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Cosa significa esattamente "elevato"?](https://docs.microsoft.com/archive/blogs/ericlippert/what-exactly-does-lifted-mean)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [Tipi riferimento nullable](../../nullable-references.md)
