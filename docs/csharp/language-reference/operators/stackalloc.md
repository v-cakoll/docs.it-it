---
title: Stackalloc espressione - Riferimento c'è
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 2e99ce8b1e44dfa040c1acac799a3a55b375bd91
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546601"
---
# <a name="stackalloc-expression-c-reference"></a>stackalloc (riferimenti per C

Un'espressione `stackalloc` alloca un blocco di memoria nello stack. Un blocco di memoria allocato nello stack, creato durante l'esecuzione del metodo, viene automaticamente eliminato alla restituzione del metodo. Non è possibile liberare `stackalloc`in modo esplicito la memoria allocata con . Un blocco di memoria allocato dello stack non è soggetto a [Garbage Collection](../../../standard/garbage-collection/index.md) e non deve essere bloccato con [ `fixed` un'istruzione](../keywords/fixed-statement.md).

È possibile assegnare `stackalloc` il risultato di un'espressione a una variabile di uno dei seguenti tipi:

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

La quantità di memoria disponibile nello stack è limitata. Se si alloca troppa memoria <xref:System.StackOverflowException> nello stack, viene generata un'eccezione . Per evitare che, seguire le regole riportate di seguito:

- Limitare la quantità di `stackalloc`memoria allocata con:

  [!code-csharp[limit stackalloc](snippets/StackallocOperator.cs#LimitStackalloc)]

  Poiché la quantità di memoria disponibile nello stack dipende dall'ambiente in cui viene eseguito il codice, essere conservativi quando si definisce il valore limite effettivo.

- Evitare `stackalloc` di utilizzare loop interni. Allocare il blocco di memoria all'esterno di un ciclo e riutilizzarlo all'interno del ciclo.

Il contenuto della memoria appena allocata non è definito. È necessario inizializzarlo prima dell'uso. Ad esempio, è <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> possibile utilizzare il metodo che imposta `T`tutti gli elementi sul valore predefinito di tipo .

A partire dalla versione 7.3 di C, è possibile usare la sintassi dell'inizializzatore di matrice per definire il contenuto della memoria appena allocata. Nell'esempio seguente vengono illustrati vari modi per eseguire questa operazione.

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

In `stackalloc T[E]`expression `T` , deve essere `E` un tipo non [gestito](../builtin-types/unmanaged-types.md) e deve restituire un valore [int](../builtin-types/integral-numeric-types.md) non negativo.

## <a name="security"></a>Security

L'uso di `stackalloc` attiva automaticamente le funzionalità di rilevazione del sovraccarico del buffer in Common Language Runtime (CLR). Se viene rilevato un sovraccarico del buffer, il processo viene terminato il più rapidamente possibile per ridurre al minimo la possibilità che venga eseguito codice dannoso.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Relativa all'allocazione dello stack](~/_csharplang/spec/unsafe-code.md#stack-allocation) della specifica del [linguaggio C](~/_csharplang/spec/introduction.md) ' e la nota proposta di funzionalità Consenti [ `stackalloc` nei contesti annidati.](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Operatori C#](index.md)
- [Operatori relativi al puntatore](pointer-related-operators.md)
- [Tipi puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipi correlati alla memoria e agli intervalli](../../../standard/memory-and-spans/index.md)
- [Cosa fare e cosa non fare di stackalloc](https://vcsjones.dev/2020/02/24/stackalloc/)
