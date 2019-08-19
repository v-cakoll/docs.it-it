---
title: Operatori C# - Riferimenti per C#
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 7db61e530ba5c3e0b5ae0ee0002621e369e1833b
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566844"
---
# <a name="c-operators-c-reference"></a>Operatori C# (Riferimenti per C#)

C# fornisce una serie di operatori predefiniti supportati dai tipi incorporati. Ad esempio, gli [operatori aritmetici](arithmetic-operators.md) eseguono operazioni aritmetiche con gli operandi di tipi numerici incorporati e gli [operatori logici booleani](boolean-logical-operators.md) eseguono operazioni logiche con gli operandi [bool](../keywords/bool.md).

Un tipo definito dall'utente può eseguire l'overload di operatori specifici per definire il comportamento corrispondente per gli operandi di quel tipo. Per altre informazioni, vedere [Overload degli operatori](operator-overloading.md).

La tabella seguente elenca gli operatori C# in ordine decrescente di precedenza. Gli operatori nella stessa riga hanno lo stesso livello di precedenza.

| Operatori | Categoria o nome |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-operator-), [x?.y](member-access-operators.md#null-conditional-operators--and-), [x?[y]](member-access-operators.md#null-conditional-operators--and-), [f(x)](member-access-operators.md#invocation-operator-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Primario |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [(T)x](type-testing-and-cast.md#cast-operator-), [await](../keywords/await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true e false](true-false-operators.md) | Unario |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | Moltiplicazione|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | Addizione |
| [x \<\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Shift |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator) | Operatori relazionali e operatori di test del tipo |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | Uguaglianza |
| `x & y` | [AND logico booleano](boolean-logical-operators.md#logical-and-operator-) o [AND bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [XOR logico booleano](boolean-logical-operators.md#logical-exclusive-or-operator-) o [XOR bit per bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [OR logico booleano](boolean-logical-operators.md#logical-or-operator-) o [OR bit per bit](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | AND condizionale |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | OR condizionale |
| [x ?? y](null-coalescing-operator.md) | Operatore null-coalescing |
| [c ? t : f](conditional-operator.md) | Operatore condizionale |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [=>](lambda-operator.md) | Assegnazione e dichiarazione lambda |

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori](../../programming-guide/statements-expressions-operators/operators.md)
