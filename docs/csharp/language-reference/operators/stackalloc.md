---
title: Operatore stackalloc - Riferimenti per C#
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 3be4e827e75e4e26a34d9ed70423af5aa317e7fb
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025012"
---
# <a name="stackalloc-operator-c-reference"></a>Operatore stackalloc (Riferimenti per C#)

L'operatore `stackalloc` alloca un blocco di memoria nello stack. Un blocco di memoria allocato nello stack, creato durante l'esecuzione del metodo, viene automaticamente eliminato alla restituzione del metodo. Non è possibile eliminare esplicitamente memoria allocata con l'operatore `stackalloc`. Un blocco di memoria allocato nello stack non è soggetto a una [Garbage Collection](../../../standard/garbage-collection/index.md) e non deve necessariamente essere aggiunto con l'[istruzione `fixed`](../keywords/fixed-statement.md).

È possibile assegnare il risultato dell'operatore `stackalloc` a una variabile di uno dei tipi seguenti:

- A partire da C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, come nell'esempio seguente.

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  Non è necessario usare un contesto [unsafe](../keywords/unsafe.md) quando si assegna un blocco di memoria allocato nello stack a una variabile <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.

  Se si usano questi tipi, è possibile applicare un'espressione `stackalloc` in espressioni [condizionali](conditional-operator.md) o di assegnazione, come illustrato nell'esempio seguente.

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > In presenza di memoria allocata nello stack, è consigliabile usare il tipo <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> ogni qualvolta sia possibile.

- Un [tipo di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md), come nell'esempio seguente.

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  Come illustrato nell'esempio precedente, quando si usa un tipo di puntatore è necessario adottare un contesto `unsafe`.

Il contenuto della memoria appena allocata non è definito. A partire da C# 7.3, è possibile usare la sintassi dell'inizializzatore di matrice per definire il contenuto della memoria appena allocata. Nell'esempio seguente vengono illustrati vari modi per eseguire questa operazione.

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a>Sicurezza

L'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR). Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Allocazione nello stack](~/_csharplang/spec/unsafe-code.md#stack-allocation) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- [Operatori relativi al puntatore](pointer-related-operators.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi correlati alla memoria e agli intervalli](../../../standard/memory-and-spans/index.md)
