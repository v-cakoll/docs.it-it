---
title: Operatore () - Riferimenti per C#
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 412d3ac5296eaf7d67f4a5e84b7a42f6fa5bb8a5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633836"
---
# <a name="-operator-c-reference"></a>Operatore () (Riferimenti per C#)

Le parentesi `()` vengono in genere usate per la chiamata di un metodo o un delegato o nelle espressioni cast.

È anche possibile usare le parentesi per specificare l'ordine in cui valutare le operazioni in un'espressione. Per altre informazioni, vedere la sezione [Aggiunta di parentesi](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) dell'articolo [Operatori](../../programming-guide/statements-expressions-operators/operators.md). Per l'elenco degli operatori ordinati in base al livello di precedenza, vedere [ Operatori C#](index.md).

## <a name="method-invocation"></a>Chiamata del metodo

L'esempio seguente illustra come richiamare un metodo (con o senza argomenti) e un delegato:

[!code-csharp-interactive[use for invocation](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

Le parentesi si usano anche per richiamare un [costruttore](../../programming-guide/classes-and-structs/constructors.md) con un operatore [`new`](../keywords/new-operator.md).

Per altre informazioni sui metodi, vedere [Metodi](../../programming-guide/classes-and-structs/methods.md). Per altre informazioni sui delegati, vedere [Delegati](../../programming-guide/delegates/index.md).

## <a name="cast-expression"></a>Espressione cast

Un'espressione cast con formato `(T)E` richiama un operatore di conversione per convertire il valore dell'espressione `E` nel tipo `T`. Se non esiste alcuna conversione esplicita dal tipo `E` al tipo `T`, si verifica un errore in fase di compilazione. Per informazioni su come definire un operatore di conversione, vedere gli articoli sulle parole chiave [explicit](../keywords/explicit.md) e [implicit](../keywords/implicit.md).

L'esempio seguente illustra la conversione di tipi tra tipi numerici:

[!code-csharp-interactive[use for cast](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

Per altre informazioni sulle conversioni esplicite predefinite tra tipi numerici, vedere [Tabella delle conversioni numeriche esplicite](../keywords/explicit-numeric-conversions-table.md).

Per altre informazioni, vedere [Cast e conversioni di tipi](../../programming-guide/types/casting-and-type-conversions.md) e [Operatori di conversione](../../programming-guide/statements-expressions-operators/conversion-operators.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Non è possibile sottoporre a overload l'operatore `()`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni [Espressioni di chiamata](~/_csharplang/spec/expressions.md#invocation-expressions) e [Espressioni cast](~/_csharplang/spec/expressions.md#cast-expressions) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
