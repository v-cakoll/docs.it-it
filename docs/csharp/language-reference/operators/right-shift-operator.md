---
title: '>> Operatore - - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 809cd2cab29d3378892ea224cf846e9d0909b073
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219724"
---
# <a name="-operator-c-reference"></a>Operatore >> (Riferimenti per C#)

L'operatore di scorrimento a destra `>>` scorre verso destra il primo operando del numero di bit definito dal secondo operando. Tutti i tipi integer supportano l'operatore `>>`. Il tipo del secondo operando deve essere tuttavia [int](../keywords/int.md) o un tipo con una [conversione numerica implicita predefinita](../keywords/implicit-numeric-conversions-table.md) in `int`.

L'operazione di scorrimento a destra rimuove i bit meno significativi. Le posizioni dei bit vuoti più significativi vengono impostate in base al tipo del primo operando come segue:

- Se il primo operando è di tipo [int](../keywords/int.md) oppure [long](../keywords/long.md), l'operatore di scorrimento a destra esegue uno scorrimento **aritmetico**: il valore del bit più significativo (il bit di segno) del primo operando viene propagato alle posizioni dei bit vuoti più significativi. Vale a dire, le posizioni dei bit vuoti più significativi vengono impostate su zero se il primo operando è un valore non negativo e impostate su uno se è negativo.

- Se il primo operando è di tipo [uint](../keywords/uint.md) oppure [ulong](../keywords/ulong.md), l'operatore di scorrimento a destra esegue uno scorrimento **logico**: le posizioni dei bit vuoti più significativi vengono sempre impostate su zero.

L'esempio seguente illustra questo comportamento:

[!code-csharp-interactive[right shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShift)]

## <a name="shift-count"></a>Conteggio degli scorrimenti

Per l'espressione `x >> count`, il conteggio degli scorrimenti effettivo dipende dal tipo di `x` come indicato di seguito:

- Se il tipo di `x` è [int](../keywords/int.md) o [uint](../keywords/uint.md), il conteggio degli scorrimenti è dato dai *cinque* bit meno significativi del secondo operando. Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x1F` (o `count & 0b_1_1111`).

- Se il tipo di `x` è [long](../keywords/long.md) o [ulong](../keywords/ulong.md), il conteggio degli scorrimenti è dato dai *sei* bit meno significativi del secondo operando. Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x3F` (o `count & 0b_11_1111`).

L'esempio seguente illustra questo comportamento:

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftByLargeCount)]

## <a name="remarks"></a>Osservazioni

Le operazioni di scorrimento non causano mai overflow e producono gli stessi risultati nei contesti [checked e unchecked](../keywords/checked-and-unchecked.md).

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `>>`. Se un tipo definito dall'utente `T` esegue l'overload dell'operatore `>>`, il tipo del primo operando deve essere `T` e il tipo del secondo operando deve essere `int`. Quando viene eseguito l'overload dell'operatore `>>`, viene eseguito in modo implicito anche l'overload dell'[operatore di assegnazione di scorrimento a destra](right-shift-assignment-operator.md) `>>=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori di scorrimento](~/_csharplang/spec/expressions.md#shift-operators) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Operatore <<](left-shift-operator.md)