---
title: Operatore stackalloc - Riferimenti per C#
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 9c9767e0c9945a9589d049fa7abba192cb928ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846252"
---
# <a name="stackalloc-operator-c-reference"></a>Operatore stackalloc (Riferimenti per C#)

L'operatore `stackalloc` alloca un blocco di memoria nello stack. Un blocco di memoria allocato nello stack, creato durante l'esecuzione del metodo, viene automaticamente eliminato alla restituzione del metodo. Non è possibile eliminare esplicitamente memoria allocata con l'operatore `stackalloc`. Un blocco di memoria allocato dello stack non è soggetto a [Garbage Collection](../../../standard/garbage-collection/index.md) e non deve essere bloccato con [ `fixed` un'istruzione](../keywords/fixed-statement.md).

È possibile assegnare il risultato dell'operatore `stackalloc` a una variabile di uno dei tipi seguenti:

- A partire da C <xref:System.Span%601?displayProperty=nameWithType> , <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>7.2, o , come illustrato nell'esempio seguente:

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  Non è necessario usare un contesto [unsafe](../keywords/unsafe.md) quando si assegna un blocco di memoria allocato nello stack a una variabile <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.

  Se si usano questi tipi, è possibile applicare un'espressione `stackalloc` in espressioni [condizionali](conditional-operator.md) o di assegnazione, come illustrato nell'esempio seguente.

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  A partire dalla versione 8.0 `stackalloc` di C, è <xref:System.Span%601> <xref:System.ReadOnlySpan%601> possibile usare un'espressione all'interno di altre espressioni ogni volta che è consentita una variabile o, come illustrato nell'esempio seguente:At beginning with C's 8.0, you can use a expression inside other expressions whenever a or variable is allowed, as the following example shows:

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > In presenza di memoria allocata nello stack, è consigliabile usare il tipo <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> ogni qualvolta sia possibile.

- Un [tipo di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md), come nell'esempio seguente.

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  Come illustrato nell'esempio precedente, quando si usa un tipo di puntatore è necessario adottare un contesto `unsafe`.

  Nel caso dei tipi puntatore, `stackalloc` è possibile utilizzare un'espressione solo in una dichiarazione di variabile locale per inizializzare la variabile.

Il contenuto della memoria appena allocata non è definito. A partire dalla versione 7.3 di C, è possibile usare la sintassi dell'inizializzatore di matrice per definire il contenuto della memoria appena allocata. Nell'esempio seguente vengono illustrati vari modi per eseguire questa operazione.

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

In `stackalloc T[E]`expression `T` , deve essere `E` un tipo non [gestito](../builtin-types/unmanaged-types.md) e deve essere un'espressione di tipo [int](../builtin-types/integral-numeric-types.md).

## <a name="security"></a>Security

L'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR). Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Relativa all'allocazione dello stack](~/_csharplang/spec/unsafe-code.md#stack-allocation) della specifica del [linguaggio C](~/_csharplang/spec/introduction.md) ' e la nota proposta di funzionalità Consenti [ `stackalloc` nei contesti annidati.](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Operatori relativi al puntatore](pointer-related-operators.md)
- [Tipi di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi correlati alla memoria e agli intervalli](../../../standard/memory-and-spans/index.md)
