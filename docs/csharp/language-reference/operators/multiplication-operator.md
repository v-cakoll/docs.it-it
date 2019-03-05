---
title: '* Operatore * - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977344"
---
# <a name="-operator-c-reference"></a>Operatore * (Riferimenti per C#)

L'operatore `*` è supportato in due forme: un operatore unario di riferimento indiretto a puntatore o un operatore di moltiplicazione binario.

## <a name="pointer-indirection-operator"></a>Operatore di riferimento indiretto a puntatore

Usare l'operatore unario `*` per ottenere la variabile a cui punta un operando di un tipo di puntatore. Per altre informazioni, vedere [Procedura: Ottenere il valore di una variabile puntatore](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).

L'operatore di riferimento indiretto a puntatore `*` richiede il contesto [unsafe](../keywords/unsafe.md).

## <a name="multiplication-operator"></a>Operatore di moltiplicazione

Per i tipi numerici, l'operatore `*` calcola il prodotto dei due operandi:

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a>Overload degli operatori

I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) di un operatore `*` binario. Quando viene eseguito l'overload di un operatore `*`, viene anche aggiunto l'[operatore di assegnazione di moltiplicazione](multiplication-assignment-operator.md) `*=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Riferimento indiretto a puntatore](~/_csharplang/spec/unsafe-code.md#pointer-indirection) e [Operatore di moltiplicazione](~/_csharplang/spec/expressions.md#multiplication-operator) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)