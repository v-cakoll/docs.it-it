---
title: foreach, in (Riferimenti per C#)
ms.date: 05/24/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: b6b7dc0a4d3970ddfbbb6635ccebbbd5b75671e4
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549382"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="68610-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="68610-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="68610-103">L'istruzione `foreach` esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68610-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="68610-104">L'istruzione `foreach` non è limitata a questi tipi e può essere applicata a un'istanza di qualsiasi tipo che soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68610-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="68610-105">include il metodo `GetEnumerator` pubblico senza parametri con tipo restituito classe, struct o interfaccia,</span><span class="sxs-lookup"><span data-stu-id="68610-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="68610-106">il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="68610-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="68610-107">In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando la parola chiave [break](break.md) o passare all'iterazione successiva nel ciclo con la parola chiave [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="68610-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span> <span data-ttu-id="68610-108">Si può uscire da un ciclo `foreach` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="68610-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="68610-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="68610-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="68610-110">L'esempio seguente mostra l'utilizzo dell'istruzione `foreach` con un'istanza del tipo <xref:System.Collections.Generic.List%601> che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="68610-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="68610-111">L'esempio successivo usa l'istruzione `foreach` con un'istanza del tipo <xref:System.Span%601?displayProperty=nameWithType>, che non implementa alcuna interfaccia:</span><span class="sxs-lookup"><span data-stu-id="68610-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="68610-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="68610-112">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="68610-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68610-113">See also</span></span>

[<span data-ttu-id="68610-114">Istruzione foreach (specifica del linguaggio C#)</span><span class="sxs-lookup"><span data-stu-id="68610-114">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="68610-115">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="68610-115">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="68610-116">for</span><span class="sxs-lookup"><span data-stu-id="68610-116">for</span></span>](for.md)  
[<span data-ttu-id="68610-117">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="68610-117">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="68610-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="68610-118">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="68610-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="68610-119">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="68610-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="68610-120">C# Programming Guide</span></span>](../../programming-guide/index.md)  