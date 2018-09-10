---
title: Istruzione foreach in C#
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: d84c68eb102d55b31ba20a6b6b5c01b96963924d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405850"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="47718-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="47718-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="47718-103">L'istruzione `foreach` esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47718-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="47718-104">L'istruzione `foreach` non è limitata a questi tipi e può essere applicata a un'istanza di qualsiasi tipo che soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47718-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="47718-105">include il metodo `GetEnumerator` pubblico senza parametri con tipo restituito classe, struct o interfaccia,</span><span class="sxs-lookup"><span data-stu-id="47718-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="47718-106">il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="47718-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="47718-107">In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="47718-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="47718-108">Si può uscire da un ciclo `foreach` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="47718-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="47718-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="47718-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="47718-110">L'esempio seguente mostra l'utilizzo dell'istruzione `foreach` con un'istanza del tipo <xref:System.Collections.Generic.List%601> che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="47718-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="47718-111">L'esempio successivo usa l'istruzione `foreach` con un'istanza del tipo <xref:System.Span%601?displayProperty=nameWithType>, che non implementa alcuna interfaccia:</span><span class="sxs-lookup"><span data-stu-id="47718-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="47718-112">A partire da C# 7.3, se la proprietà `Current` dell'enumeratore restituisce un [valore restituito di riferimento](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T` dove `T` è il tipo dell'elemento della raccolta), è possibile dichiarare la variabile di iterazione con il modificatore `ref` o `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="47718-112">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span> <span data-ttu-id="47718-113">L'esempio seguente usa una variabile di iterazione `ref` per impostare il valore di ogni elemento in una matrice di stackalloc.</span><span class="sxs-lookup"><span data-stu-id="47718-113">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="47718-114">La versione `ref readonly` esegue l'iterazione della raccolta per stampare tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="47718-114">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="47718-115">La dichiarazione `readonly` usa una dichiarazione di variabile locale implicita.</span><span class="sxs-lookup"><span data-stu-id="47718-115">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="47718-116">Le dichiarazioni di variabili implicite possono essere usate con le dichiarazioni `ref` o `ref readonly`, così come le dichiarazioni di variabili tipizzate.</span><span class="sxs-lookup"><span data-stu-id="47718-116">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="47718-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="47718-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="47718-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47718-118">See also</span></span>

- [<span data-ttu-id="47718-119">Istruzione foreach (specifica del linguaggio C#)</span><span class="sxs-lookup"><span data-stu-id="47718-119">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)
- [<span data-ttu-id="47718-120">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="47718-120">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="47718-121">for</span><span class="sxs-lookup"><span data-stu-id="47718-121">for</span></span>](for.md)
- [<span data-ttu-id="47718-122">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="47718-122">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="47718-123">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="47718-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="47718-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="47718-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47718-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="47718-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
