---
title: Uso dei tipi nullable (Guida per programmatori C#)
description: Informazioni su come usare i tipi nullable in C#
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 9c9ab5c3ca1dd49f011bf9c980945fa9da0d8cfc
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148353"
---
# <a name="using-nullable-types-c-programming-guide"></a>Uso dei tipi nullable (Guida per programmatori C#)

I tipi nullable sono tipi che rappresentano tutti i valori di un tipo valore sottostante `T` e un valore [Null](../../language-reference/keywords/null.md) aggiuntivo. Per altre informazioni, vedere l'argomento [Tipi nullable](index.md).

È possibile fare riferimento a un tipo nullable in uno dei formati seguenti: `Nullable<T>` o `T?`. Questi due formati sono intercambiabili.  
  
## <a name="declaration-and-assignment"></a>Dichiarazione e assegnazione

Dal momento che un tipo valore può essere convertito in modo implicito nel tipo nullable corrispondente, è possibile assegnare un valore a un tipo nullable seguendo la stessa procedura adottata per il relativo tipo valore sottostante. È anche possibile assegnare il valore `null`.  Ad esempio:
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>Esame di un valore di tipo nullable

Usare le proprietà di sola lettura seguenti per esaminare un'istanza di un tipo nullable e verificare la presenza di valori Null e recuperare un valore di un tipo sottostante:  
  
- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica se un'istanza di un tipo nullable contiene un valore del relativo tipo sottostante.
  
- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ottiene il valore di un tipo sottostante se <xref:System.Nullable%601.HasValue%2A> è `true`. Se <xref:System.Nullable%601.HasValue%2A> è `false`, la proprietà <xref:System.Nullable%601.Value%2A> genera un'eccezione <xref:System.InvalidOperationException>.
  
Il codice nell'esempio seguente usa la proprietà `HasValue` per verificare se la variabile contiene un valore prima di visualizzarla:
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
È anche possibile confrontare una variabile di tipo nullable con `null` invece di usare la proprietà `HasValue`, come illustrato nell'esempio seguente:  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

A partire da C# 7.0, è possibile usare i [criteri di ricerca](../../pattern-matching.md) per esaminare e ottenere un valore di un tipo nullable:

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a>Conversione da un tipo nullable a un tipo sottostante

Se è necessario assegnare un valore di tipo nullable a un tipo non nullable, usare l'[operatore null-coalescing `??` ](../../language-reference/operators/null-coalescing-operator.md) per specificare il valore da assegnare se un valore di tipo nullable è Null. A questo scopo, è anche possibile usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>.
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

Usare il metodo <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> se il valore da usare quando un valore di tipo nullable è Null deve essere il valore predefinito del tipo valore sottostante.
  
È possibile eseguire il cast in modo esplicito di un tipo nullable in un tipo non nullable. Ad esempio:  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

Se in fase di esecuzione il valore di un tipo nullable è Null, il cast esplicito genera un'eccezione <xref:System.InvalidOperationException>.

Un tipo valore non nullable viene convertito in modo implicito nel tipo nullable corrispondente.
  
## <a name="operators"></a>Operatori

Gli operatori unari e binari predefiniti e gli eventuali operatori definiti dall'utente esistenti per i tipi di valore possono essere usati anche dai tipi nullable. Questi operatori generano un valore Null se uno o entrambi gli operandi sono Null. In caso contrario, l'operatore usa i valori contenuti per calcolare il risultato. Ad esempio:  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]
  
Per gli operatori relazionali (`<`, `>`, `<=`, `>=`), se uno o entrambi gli operandi sono Null, il risultato è `false`. Non presupporre che poiché un particolare confronto (ad esempio, `<=`) restituisce `false`, il confronto opposto (`>`) restituisce `true`. L'esempio seguente mostra che 10

- non è né maggiore o uguale a Null,
- né minore di Null.
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
L'esempio precedente mostra anche che un confronto di uguaglianza tra due tipi nullable che sono entrambi Null restituisce `true`.

## <a name="boxing-and-unboxing"></a>Boxing e unboxing

Un tipo valore nullable viene sottoposto a [boxing](../types/boxing-and-unboxing.md) in base alle regole seguenti:

- Se <xref:System.Nullable%601.HasValue%2A> restituisce `false`, viene prodotto il riferimento Null.  
- Se <xref:System.Nullable%601.HasValue%2A> restituisce `true`, viene sottoposto a boxing un valore del tipo valore sottostante `T` e non l'istanza di <xref:System.Nullable%601>.

È possibile eseguire la conversione unboxing del tipo valore sottoposto a boxing nel tipo nullable corrispondente, come illustrato nell'esempio seguente:

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="the-bool-type"></a>Tipo bool?

Il tipo nullable `bool?` può contenere tre valori diversi: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) e [null](../../language-reference/keywords/null.md). Il tipo `bool?` è simile al tipo di variabile booleano usato in SQL. Per garantire che i risultati prodotti dagli operatori `&` e `|` siano coerenti con il tipo booleano a tre valori in SQL, sono disponibili gli operatori predefiniti seguenti:

- `bool? operator &(bool? x, bool? y)`  
- `bool? operator |(bool? x, bool? y)`  
  
La semantica di questi operatori è definita dalla tabella seguente:  
  
|x|y|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|False|false|true|  
|true|Null|Null|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|Null|False|Null|  
|Null|true|Null|true|  
|Null|False|False|Null|  
|Null|Null|Null|Null|  

Tenere presente che questi due operatori non si attengono alle regole descritte nella sezione [Operatori](#operators): il risultato di una valutazione degli operatori può essere diverso da Null, anche se uno degli operandi è Null.
  
## <a name="see-also"></a>Vedere anche

- [Tipi nullable](index.md)  
- [Guida per programmatori C#](../../programming-guide/index.md)  
- [Cosa significa esattamente "elevato"?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)  
