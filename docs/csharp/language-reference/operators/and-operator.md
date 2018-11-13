---
title: Operatore &amp; (Riferimenti per C#)
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: a8f76ded0ef9f8e8099838a903d90f1695324991
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "43510978"
---
# <a name="amp-operator-c-reference"></a>Operatore &amp; (Riferimenti per C#)

L'operatore `&` è supportato in due forme: un operatore address-of unario o un operatore logico binario.

## <a name="unary-address-of-operator"></a>Operatore address-of unario

L'operatore `&` unario restituisce l'indirizzo del proprio operando. Per altre informazioni, vedere [Procedura: Ottenere l'indirizzo di una variabile](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).

L'operatore address-of `&` richiede un contesto [unsafe](../keywords/unsafe.md).

## <a name="integer-logical-bitwise-and-operator"></a>Operatore AND logico bit per bit intero

Per i tipi interi, l'operatore `&` calcola l'AND logico bit per bit dei relativi operandi:

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> L'esempio precedente usa i valori letterali binari [introdotti in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) e [migliorati in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).

Poiché le operazioni sui tipi interi sono in genere consentite sui tipi di enumerazione, l'operatore `&` supporta anche gli operandi [enum](../keywords/enum.md).

## <a name="boolean-logical-and-operator"></a>Operatore AND logico booleano

Per gli operandi [bool](../keywords/bool.md), l'operatore `&` calcola l'AND logico dei relativi operandi. Il risultato di `x & y` è `true` se `x` e `y` sono `true`. In caso contrario, il risultato è `false`.

L'operatore `&` valuta entrambi gli operandi anche se il primo operando restituisce `false`, in modo che il risultato sia `false` indipendentemente dal valore del secondo operando. L'esempio seguente illustra questo comportamento:

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

L'[operatore AND condizionale](conditional-and-operator.md) `&&` calcola l'AND logico dei relativi operandi, ma valuta il secondo operando solo se il primo operando restituisce `true`.

Per gli operandi bool nullable, il comportamento dell'operatore `&` è coerente con la logica a tre valori di SQL. Per altre informazioni, vedere la sezione [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) dell'articolo [Uso dei tipi nullable](../../programming-guide/nullable-types/using-nullable-types.md).

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `&` binario. Quando viene eseguito l'overload di un operatore `&` binario, viene eseguito in modo implicito anche l'overload dell'[operatore di assegnazione AND](and-assignment-operator.md) `&=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Operatore address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) e [Operatori logici](~/_csharplang/spec/expressions.md#logical-operators) in [Specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Operatore |](or-operator.md)
- [Operatore ^](xor-operator.md)
- [Operatore ~](bitwise-complement-operator.md)
- [Operatore &&](conditional-and-operator.md)
