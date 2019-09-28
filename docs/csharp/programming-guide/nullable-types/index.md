---
title: Tipi di valore Nullable C# -Guida alla programmazione
ms.custom: seodec18
description: Informazioni sui C# tipi di valore nullable e su come usarli
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#]
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: b8b52e7fb34adf65d5c76d59811ea6dd0ab16a98
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396226"
---
# <a name="nullable-value-types-c-programming-guide"></a>Tipi di valore NullableC# (Guida per programmatori)

I tipi di valore nullable sono istanze della struttura <xref:System.Nullable%601?displayProperty=nameWithType>. I tipi di valore nullable possono rappresentare tutti i valori di un tipo sottostante `T` e un valore [null](../../language-reference/keywords/null.md) aggiuntivo. Il tipo sottostante `T` può essere qualsiasi [tipo valore](../../language-reference/keywords/value-types.md) non nullable. `T` non può essere un tipo riferimento.

> [!NOTE]
> C#8,0 introduce la funzionalità dei tipi di riferimento Nullable. Per altre informazioni, vedere [tipi di riferimento Nullable](../../nullable-references.md). I tipi di valore nullable sono disponibili a C# partire da 2.

È ad esempio possibile assegnare `null` o qualsiasi valore integer compreso tra <xref:System.Int32.MinValue?displayProperty=nameWithType> e <xref:System.Int32.MaxValue?displayProperty=nameWithType> a `Nullable<int>` e [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) o `null` a `Nullable<bool>`.

Si utilizza un tipo di valore nullable quando è necessario rappresentare il valore non definito di un tipo sottostante. Una variabile booleana può avere solo due valori: `true` e `false`. Non è previsto alcun valore "non definito". In molte applicazioni di programmazione, in particolare nelle interazioni tra database, un valore di variabile può essere non definito o mancante. Ad esempio un campo di un database può contenere i valori true o false oppure è possibile che non contenga alcun valore. In tale caso si usa un tipo `Nullable<bool>`.

I tipi di valore Nullable hanno le caratteristiche seguenti:

- I tipi di valore nullable rappresentano variabili di tipo valore a cui è possibile assegnare il valore `null`.

- La sintassi `T?` è un'abbreviazione per `Nullable<T>`. Le due forme sono intercambiabili.

- Assegnare un valore a un tipo di valore Nullable esattamente come per un tipo di valore sottostante: `int? x = 10;` o `double? d = 4.108;`. È anche possibile assegnare il valore `null`: `int? x = null;`.

- Usare le proprietà di sola lettura <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> e <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> per verificare la presenza di valori null e recuperare il valore, come illustrato nell'esempio seguente: `if (x.HasValue) y = x.Value;`

  - La proprietà <xref:System.Nullable%601.HasValue%2A> restituisce `true` se la variabile contiene un valore o `false` se è `null`.

  - La proprietà <xref:System.Nullable%601.Value%2A> restituisce un valore se <xref:System.Nullable%601.HasValue%2A> restituisce `true`. In caso contrario, verrà generata un'eccezione <xref:System.InvalidOperationException>.

- È anche possibile usare gli operatori `==` e `!=` con un tipo di valore Nullable, come illustrato nell'esempio seguente: `if (x != null) y = x.Value;`. Se `a` e `b` sono Null, `a == b` restituisce `true`.

- A partire da C# 7.0, è possibile usare i [criteri di ricerca](../../pattern-matching.md#the-is-type-pattern-expression) per esaminare e ottenere un valore di un tipo nullable: `if (x is int valueOfX) y = valueOfX;`.

- Il valore predefinito di `T?` è un'istanza la cui proprietà <xref:System.Nullable%601.HasValue%2A> restituisce `false`.

- Usare il metodo <xref:System.Nullable%601.GetValueOrDefault> per restituire il valore assegnato oppure il valore [predefinito](../../language-reference/keywords/default-values-table.md) del tipo valore sottostante se il valore del tipo nullable è `null`.

- Usare il metodo <xref:System.Nullable%601.GetValueOrDefault(%600)> per restituire il valore assegnato oppure il valore predefinito specificato se il valore del tipo nullable è `null`.

- Usare l' [operatore](../../language-reference/operators/null-coalescing-operator.md)di Unione null, `??`, per assegnare un valore a una variabile di un tipo di valore sottostante in base a un valore di tipo nullable: `int? x = null; int y = x ?? -1;`. Nell'esempio, dal momento che `x` è `null`, il valore del risultato di `y` è `-1`.

- Se viene definita una conversione definita dall'utente tra due tipi di valore, la stessa conversione può essere usata anche con i tipi nullable corrispondenti.

- I tipi di valore nullable annidati non sono consentiti. La riga seguente non verrà compilata: `Nullable<Nullable<int>> n;`

Per ulteriori informazioni, vedere l'argomento relativo all' [utilizzo dei tipi di valore Nullable](using-nullable-types.md) e [procedura: identificare un tipo di valore Nullable](how-to-identify-a-nullable-type.md) .

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [?? (operatore)](../../language-reference/operators/null-coalescing-operator.md)
- [Tipi di valori nullable (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
