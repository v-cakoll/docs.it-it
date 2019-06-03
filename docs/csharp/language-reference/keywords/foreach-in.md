---
title: Istruzione foreach in C#
ms.date: 05/17/2019
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 3fbaacb96be2714aaff49679836e5d2d4a3783da
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422475"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="c0f0f-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c0f0f-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="c0f0f-103">L'istruzione `foreach` esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="c0f0f-104">L'istruzione `foreach` non è limitata a questi tipi e può essere applicata a un'istanza di qualsiasi tipo che soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0f0f-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="c0f0f-105">include il metodo `GetEnumerator` pubblico senza parametri con tipo restituito classe, struct o interfaccia,</span><span class="sxs-lookup"><span data-stu-id="c0f0f-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="c0f0f-106">il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="c0f0f-107">A partire da C# 7.3, se la proprietà `Current` dell'enumeratore restituisce un [valore restituito di riferimento](ref.md#reference-return-values) (`ref T` dove `T` è il tipo dell'elemento della raccolta), è possibile dichiarare la variabile di iterazione con il modificatore `ref` o `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="c0f0f-108">In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="c0f0f-108">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="c0f0f-109">Si può uscire da un ciclo `foreach` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="c0f0f-109">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="c0f0f-110">Se l'istruzione `foreach` viene applicata a `null`, viene generata una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-110">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="c0f0f-111">Se la raccolta di origine dell'istruzione `foreach` è vuota, il corpo del ciclo `foreach` non viene eseguito e viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-111">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop is not executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="c0f0f-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="c0f0f-112">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="c0f0f-113">L'esempio seguente mostra l'utilizzo dell'istruzione `foreach` con un'istanza del tipo <xref:System.Collections.Generic.List%601> che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="c0f0f-113">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="c0f0f-114">L'esempio successivo usa l'istruzione `foreach` con un'istanza del tipo <xref:System.Span%601?displayProperty=nameWithType>, che non implementa alcuna interfaccia:</span><span class="sxs-lookup"><span data-stu-id="c0f0f-114">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="c0f0f-115">L'esempio seguente usa una variabile di iterazione `ref` per impostare il valore di ogni elemento in una matrice di stackalloc.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-115">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="c0f0f-116">La versione `ref readonly` esegue l'iterazione della raccolta per stampare tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-116">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="c0f0f-117">La dichiarazione `readonly` usa una dichiarazione di variabile locale implicita.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-117">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="c0f0f-118">Le dichiarazioni di variabili implicite possono essere usate con le dichiarazioni `ref` o `ref readonly`, così come le dichiarazioni di variabili tipizzate.</span><span class="sxs-lookup"><span data-stu-id="c0f0f-118">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="c0f0f-119">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c0f0f-119">C# language specification</span></span>

<span data-ttu-id="c0f0f-120">Per altre informazioni, vedere la sezione [L'istruzione foreach](~/_csharplang/spec/statements.md#the-foreach-statement) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0f0f-120">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0f0f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f0f-121">See also</span></span>

- [<span data-ttu-id="c0f0f-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c0f0f-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c0f0f-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0f0f-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c0f0f-124">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="c0f0f-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c0f0f-125">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="c0f0f-125">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="c0f0f-126">Istruzione For</span><span class="sxs-lookup"><span data-stu-id="c0f0f-126">for statement</span></span>](for.md)
