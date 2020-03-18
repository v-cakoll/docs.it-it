---
title: Tipi di valore nullable - Riferimenti per C
description: Informazioni sui tipi di valore nullable di C'è e su come usarli
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: a84b3d60269491846b783e5046a84a1d14e258a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399588"
---
# <a name="nullable-value-types-c-reference"></a>Tipi di valore nullable (riferimenti per C

Un tipo `T?` di *valore nullable* rappresenta tutti i valori del [tipo](value-types.md) `T` di valore sottostante e un valore [null](../keywords/null.md) aggiuntivo. Ad esempio, è possibile assegnare uno `bool?` dei `true`tre `false`valori `null`seguenti a una variabile: , , o . Un tipo `T` di valore sottostante non può essere un tipo di valore nullable.

> [!NOTE]
> La funzionalità dei tipi di riferimento nullable viene introdotta in C . Per ulteriori informazioni, vedere [Tipi di riferimento nullable](../../nullable-references.md). I tipi di valore nullable sono disponibili a partire da C .

Qualsiasi tipo di valore nullable <xref:System.Nullable%601?displayProperty=nameWithType> è un'istanza della struttura generica. È possibile fare riferimento a un tipo `T` di valore nullable con `Nullable<T>` un `T?`tipo sottostante in uno dei seguenti formati intercambiabili: o .

In genere si utilizza un tipo di valore nullable quando è necessario rappresentare il valore non definito di un tipo di valore sottostante. Ad esempio, una `bool`variabile Boolean, oppure `false`, può essere solo o `true` . Tuttavia, in alcune applicazioni un valore di variabile può essere indefinito o mancante. Ad esempio, un campo `true` `false`del database può contenere o , `NULL`oppure non può contenere alcun valore, ovvero . È possibile `bool?` utilizzare il tipo in tale scenario.

## <a name="declaration-and-assignment"></a>Dichiarazione e assegnazione

Poiché un tipo di valore è convertibile in modo implicito nel tipo di valore nullable corrispondente, è possibile assegnare un valore a una variabile di un tipo di valore nullable come si farebbe per il tipo di valore sottostante. È anche possibile assegnare il valore `null`. Ad esempio:

[!code-csharp[declare and assign](snippets/NullableValueTypes.cs#Declaration)]

Il valore predefinito di un `null`tipo di valore nullable rappresenta <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> , `false`ovvero è un'istanza la cui proprietà restituisce .

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a>Esame di un'istanza di un tipo di valore nullable

A partire dalla versione 7.0 di C, è possibile usare `null` l'operatore [ `is` con un modello](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) di tipo per esaminare un'istanza di un tipo di valore nullable per che recuperare un valore di un tipo sottostante:

[!code-csharp-interactive[use pattern matching](snippets/NullableValueTypes.cs#PatternMatching)]

È sempre possibile utilizzare le seguenti proprietà di sola lettura per esaminare e ottenere un valore di una variabile di tipo valore nullable:You always can always use the following read-only properties to examine and get a value of a nullable value type variable:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType>indica se un'istanza di un tipo di valore nullable ha un valore del tipo sottostante.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ottiene il valore di un tipo sottostante se <xref:System.Nullable%601.HasValue%2A> è `true`. Se <xref:System.Nullable%601.HasValue%2A> è `false`, la proprietà <xref:System.Nullable%601.Value%2A> genera un'eccezione <xref:System.InvalidOperationException>.

Nell'esempio seguente `HasValue` viene utilizzata la proprietà per verificare se la variabile contiene un valore prima di visualizzarlo:

[!code-csharp-interactive[use HasValue](snippets/NullableValueTypes.cs#HasValue)]

È anche possibile confrontare una variabile `null` di un `HasValue` tipo di valore nullable con anziché utilizzare la proprietà, come illustrato nell'esempio seguente:You can also compare a variable of a nullable value type with instead of using the property, as the following example shows:

[!code-csharp-interactive[use comparison with null](snippets/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Conversione da un tipo di valore nullable a un tipo sottostanteConversion from a nullable value type to an underlying type

Se si desidera assegnare un valore di un tipo di valore nullable a una variabile di tipo `null`valore non nullable, potrebbe essere necessario specificare il valore da assegnare al posto di . Utilizzare [l'operatore `??` null-coalescing](../operators/null-coalescing-operator.md) per eseguire <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> questa operazione (è anche possibile utilizzare il metodo per lo stesso scopo):

[!code-csharp-interactive[?? operator](snippets/NullableValueTypes.cs#NullCoalescing)]

Se si desidera utilizzare il valore [predefinito](default-values.md) del `null`tipo di <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> valore sottostante al posto di , utilizzare il metodo .

È anche possibile eseguire in modo esplicito il cast di un tipo di valore nullable a un tipo non nullable, come illustrato nell'esempio seguente:You also can explicitly cast a nullable value type to a non-nullable type, as the following example shows:

[!code-csharp[explicit cast](snippets/NullableValueTypes.cs#Cast)]

In fase di esecuzione, se il valore `null`di un tipo <xref:System.InvalidOperationException>di valore nullable è , il cast esplicito genera un'eccezione .

Un tipo `T` di valore non nullable è convertibile in `T?`modo implicito nel tipo di valore nullable corrispondente.

## <a name="lifted-operators"></a>Operatori sollevati

Gli [operatori](../operators/index.md) unari e binari predefiniti o qualsiasi operatore `T` di overload supportato da un `T?`tipo di valore sono supportati anche dal tipo di valore nullable corrispondente. Questi operatori, noti anche `null` come operatori *lifted*, producono `null`se uno o entrambi gli operandi sono ; in caso contrario, l'operatore utilizza i valori contenuti degli operandi per calcolare il risultato. Ad esempio:

[!code-csharp[lifted operators](snippets/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> Per `bool?` il tipo, `&` gli `|` operatori predefiniti e gli operatori non seguono le regole descritte in questa sezione: il risultato di una valutazione dell'operatore può essere non null anche se uno degli operandi è `null`. Per altre informazioni, vedere la sezione [Operatori logici booleani nullable](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) dell'articolo [Operatori logici booleani](../operators/boolean-logical-operators.md).

Per [comparison operators](../operators/comparison-operators.md) `<`gli operatori `>` `<=`di `>=`confronto , , e , `null`se uno `false`o entrambi gli operandi sono , il risultato è ; in caso contrario, vengono confrontati i valori contenuti degli operandi. Non presupporre che poiché un particolare confronto (ad esempio, `<=`) restituisce `false`, il confronto opposto (`>`) restituisce `true`. L'esempio seguente mostra che 10

- né maggiore o uguale a`null`
- né inferiore a`null`

[!code-csharp-interactive[relational and equality operators](snippets/NullableValueTypes.cs#ComparisonOperators)]

Per [l'operatore](../operators/equality-operators.md#equality-operator-) `==`di uguaglianza `null`, se `true`entrambi gli operandi sono `null`, il `false`risultato è , se solo uno degli operandi è , il risultato è ; in caso contrario, vengono confrontati i valori contenuti degli operandi.

Per [l'operatore](../operators/equality-operators.md#inequality-operator-) `!=`di disuguaglianza , `null`se entrambi `false`gli operandi sono , `null`il risultato è , se solo uno degli operandi è , il risultato è `true`; in caso contrario, vengono confrontati i valori contenuti degli operandi.

Se esiste una [conversione definita dall'utente](../operators/user-defined-conversion-operators.md) tra due tipi di valore, la stessa conversione può essere utilizzata anche tra i tipi di valore nullable corrispondenti.

## <a name="boxing-and-unboxing"></a>Boxing e unboxing

Un'istanza di un `T?` tipo di valore nullable è [boxed](../../programming-guide/types/boxing-and-unboxing.md) come segue:

- Se <xref:System.Nullable%601.HasValue%2A> restituisce `false`, viene prodotto il riferimento Null.
- Se <xref:System.Nullable%601.HasValue%2A> `true`restituisce , il valore `T` corrispondente del tipo di <xref:System.Nullable%601>valore sottostante è boxed, non l'istanza di .

È possibile eseguire l'unboxing `T` di un valore boxed di un tipo di valore al tipo di `T?`valore nullable corrispondente, come illustrato nell'esempio seguente:

[!code-csharp-interactive[boxing and unboxing](snippets/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a>Come identificare un tipo di valore nullableHow to identify a nullable value type

Nell'esempio seguente viene illustrato <xref:System.Type?displayProperty=nameWithType> come determinare se un'istanza rappresenta <xref:System.Nullable%601?displayProperty=nameWithType> un tipo di `T`valore nullable costruito, ovvero il tipo con un parametro di tipo specificato:

[!code-csharp-interactive[whether Type is nullable](snippets/NullableValueTypes.cs#IsTypeNullable)]

Come illustrato nell'esempio, si utilizza l'operatore [typeof](../operators/type-testing-and-cast.md#typeof-operator) per creare un'istanza. <xref:System.Type?displayProperty=nameWithType>

Se si desidera determinare se un'istanza è di un tipo <xref:System.Object.GetType%2A?displayProperty=nameWithType> di valore <xref:System.Type> nullable, non utilizzare il metodo per ottenere un'istanza da testare con il codice precedente. Quando si <xref:System.Object.GetType%2A?displayProperty=nameWithType> chiama il metodo su un'istanza di un tipo <xref:System.Object>di valore nullable, l'istanza viene sottoposta a [boxing](#boxing-and-unboxing) in . Poiché il boxing di un'istanza non null di un tipo di valore <xref:System.Object.GetType%2A> nullable <xref:System.Type> equivale al boxing di un valore del tipo sottostante, restituisce un'istanza che rappresenta il tipo sottostante di un tipo di valore nullable:

[!code-csharp-interactive[GetType example](snippets/NullableValueTypes.cs#GetType)]

Inoltre, non utilizzare l'operatore [is](../operators/type-testing-and-cast.md#is-operator) per determinare se un'istanza è di un tipo di valore nullable. Come illustrato nell'esempio seguente, non è possibile distinguere i tipi di `is` un'istanza di tipo di valore nullable e la relativa istanza del tipo sottostante con l'operatore:

[!code-csharp-interactive[is operator example](snippets/NullableValueTypes.cs#IsOperator)]

È possibile utilizzare il codice presentato nell'esempio seguente per determinare se un'istanza è di un tipo di valore nullable:You can use the code presented in the following example to determine whether an instance is of a nullable value type:

[!code-csharp-interactive[whether an instance is of a nullable type](snippets/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> I metodi descritti in questa sezione non sono applicabili nel caso di tipi di [riferimento nullable.](../../nullable-references.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi nullable](~/_csharplang/spec/types.md#nullable-types)
- [Operatori sollevati](~/_csharplang/spec/expressions.md#lifted-operators)
- [Conversioni nullable implicite](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [Conversioni nullable espliciteExplicit nullable conversions](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [Operatori di conversione lifted](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Cosa significa esattamente "elevato"?](https://docs.microsoft.com/archive/blogs/ericlippert/what-exactly-does-lifted-mean)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [Tipi riferimento nullable](../../nullable-references.md)
