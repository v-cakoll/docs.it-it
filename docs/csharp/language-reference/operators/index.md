---
title: Operatori C# - Riferimenti per C#
ms.date: 04/28/2020
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 76a9b1efb46af976e59e5f16d3180891ec54ecee
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507403"
---
# <a name="c-operators-c-reference"></a>Operatori C# (Riferimenti per C#)

C# include una serie di operatori supportati dai tipi predefiniti. Ad esempio, gli [operatori aritmetici](arithmetic-operators.md) eseguono operazioni aritmetiche con operandi numerici e gli [operatori logici booleani](boolean-logical-operators.md) eseguono operazioni logiche con operandi [bool](../builtin-types/bool.md). Certi operatori possono essere [sottoposti a overload](operator-overloading.md). Con l'overload degli operatori, è possibile specificare il comportamento dell'operatore per gli operandi di un tipo definito dall'utente.

In un'[espressione](../../programming-guide/statements-expressions-operators/expressions.md), la precedenza e l'associatività degli operatori determinano l'ordine in cui vengono eseguite le operazioni. È possibile usare le parentesi per cambiare l'ordine di valutazione imposto dalla precedenza e dall'associatività degli operatori.

## <a name="operator-precedence"></a>Precedenza degli operatori

In un'espressione con più operatori, gli operatori con precedenza superiore vengono valutati prima degli operatori con precedenza più bassa. Nell'esempio seguente, la moltiplicazione viene eseguita per prima perché ha una precedenza più alta rispetto all'addizione:

```csharp-interactive
var a = 2 + 2 * 2;
Console.WriteLine(a); //  output: 6
```

Usare le parentesi per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:

```csharp-interactive
var a = (2 + 2) * 2;
Console.WriteLine(a); //  output: 8
```

La tabella seguente elenca gli operatori C# in ordine decrescente di precedenza. Gli operatori nella stessa riga hanno la stessa precedenza.

| Operatori | Categoria o nome |
| --------- | ---------------- |
| [x. y](member-access-operators.md#member-access-expression-), [f (x)](member-access-operators.md#invocation-expression-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [`x?[y]`](member-access-operators.md#null-conditional-operators--and-), [x + +](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [x!](null-forgiving.md), [New](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [dechecked](../keywords/unchecked.md), [default](default.md), [NameOf](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Primaria |
| [+ x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [ \!x](boolean-logical-operators.md#logical-negation-operator-), [~ x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [+ + x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^ x](member-access-operators.md#index-from-end-operator-), [(T) x](type-testing-and-cast.md#cast-expression), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [* x](pointer-related-operators.md#pointer-indirection-operator-), [true e false](true-false-operators.md) | Unaria |
| [x.. y](member-access-operators.md#range-operator-) | Range |
| [switch](../../whats-new/csharp-8.md#switch-expressions) | Espressione `switch` |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | Moltiplicazione|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | Additive |
| [ \< x \< y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Turno |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator) | Operatori relazionali e operatori di test del tipo |
| [x = = y](equality-operators.md#equality-operator-), [x! = y](equality-operators.md#inequality-operator-) | Uguaglianza |
| `x & y` | [AND logico booleano](boolean-logical-operators.md#logical-and-operator-) o [AND bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [XOR logico booleano](boolean-logical-operators.md#logical-exclusive-or-operator-) o [XOR bit per bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [OR logico booleano](boolean-logical-operators.md#logical-or-operator-) o [OR bit per bit](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | AND condizionale |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | OR condizionale |
| [x ?? y](null-coalescing-operator.md) | Operatore null-coalescing |
| [c ? t : f](conditional-operator.md) | Operatore condizionale |
| [x = y](assignment-operator.md), [x + = y](arithmetic-operators.md#compound-assignment), [x-= y](arithmetic-operators.md#compound-assignment), [x * = y](arithmetic-operators.md#compound-assignment), [x/= y](arithmetic-operators.md#compound-assignment), [x% = y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^ = y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [x? = y](null-coalescing-operator.md),[=>](lambda-operator.md) | Assegnazione e dichiarazione lambda |

## <a name="operator-associativity"></a>Associatività degli operatori

Quando gli operatori hanno la stessa precedenza, l'associatività degli operatori determina l'ordine di esecuzione delle operazioni:

- Gli operatori *associativi a sinistra* vengono valutati nell'ordine da sinistra a destra. Ad eccezione degli operatori di [assegnazione](assignment-operator.md) e degli [operatori che uniscono valori null](null-coalescing-operator.md), tutti gli operatori binari sono associativi a sinistra. L'espressione `a + b - c` viene ad esempio valutata come `(a + b) - c`.
- Gli operatori *associativi a destra* vengono valutati nell'ordine da destra a sinistra. Gli operatori di assegnazione, gli operatori che uniscono valori null e l' [operatore `?:` condizionale](conditional-operator.md) sono associativi a destra. L'espressione `x = y = z` viene ad esempio valutata come `x = (y = z)`.

Usare le parentesi per cambiare l'ordine di valutazione imposto dall'associatività degli operatori:

```csharp-interactive
int a = 13 / 5 / 2;
int b = 13 / (5 / 2);
Console.WriteLine($"a = {a}, b = {b}");  // output: a = 1, b = 6
```

## <a name="operand-evaluation"></a>Valutazione dell'operando

Senza correlazione con la precedenza e l'associatività degli operatori, gli operandi in un'espressione vengono valutati da sinistra a destra. Gli esempi seguenti dimostrano l'ordine di valutazione degli operatori e degli operandi:

| Expression | Ordine di valutazione |
| ---------- | ------------------- |
|`a + b`|a, b, +|
|`a + b * c`|a, b, c, *, +|
|`a / b + c * d`|a, b, /, c, d, *, +|
|`a / (b + c) * d`|a, b, c, +, /, d, *|

In genere, vengono valutati tutti gli operandi dell'operatore. Tuttavia, alcuni operatori valutano gli operandi in modo condizionale. Ovvero, il valore dell'operando più a sinistra di tale operatore definisce se (o quali) devono essere valutati altri operandi. Questi operatori sono gli operatori logici [and`&&`()](boolean-logical-operators.md#conditional-logical-and-operator-) e [or`||`()](boolean-logical-operators.md#conditional-logical-or-operator-) condizionali, gli [ `??` operatori con Unione null `??=`e ](null-coalescing-operator.md), gli [operatori `?.` condizionali null `?[]`e ](member-access-operators.md#null-conditional-operators--and-)e l' [operatore `?:`condizionale ](conditional-operator.md). Per ulteriori informazioni, vedere la descrizione di ogni operatore.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori](~/_csharplang/spec/expressions.md#operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Espressioni](../../programming-guide/statements-expressions-operators/expressions.md)
