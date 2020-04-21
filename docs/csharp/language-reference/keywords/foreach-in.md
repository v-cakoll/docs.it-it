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
ms.openlocfilehash: 188d909fd33b14755d9b121953b1fa434ecf536d
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738810"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="2a214-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2a214-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="2a214-103">L'istruzione `foreach` esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2a214-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="2a214-104">L'istruzione `foreach` non è limitata a questi tipi e può essere applicata a un'istanza di qualsiasi tipo che soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a214-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="2a214-105">include il metodo `GetEnumerator` pubblico senza parametri con tipo restituito classe, struct o interfaccia,</span><span class="sxs-lookup"><span data-stu-id="2a214-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="2a214-106">il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="2a214-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="2a214-107">A partire dalla versione 7.3 di `Current` C, se la `T` proprietà dell'enumeratore restituisce un valore restituito `ref` di `ref readonly` [riferimento](ref.md#reference-return-values) (dove`ref T` è il tipo dell'elemento della raccolta), è possibile dichiarare la variabile di iterazione con il modificatore o .</span><span class="sxs-lookup"><span data-stu-id="2a214-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="2a214-108">A partire dalla versione 8.0 di C, l'operatore `await` può essere applicato all'istruzione `foreach` quando il tipo di raccolta implementa l'interfaccia. <xref:System.Collections.Generic.IAsyncEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="2a214-108">Beginning with C# 8.0, the `await` operator may be applied to the `foreach` statement when the collection type implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="2a214-109">Ogni iterazione del ciclo può essere sospesa mentre l'elemento successivo viene recuperato in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="2a214-109">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="2a214-110">Per impostazione predefinita, gli elementi di flusso vengono elaborati nel contesto acquisito.</span><span class="sxs-lookup"><span data-stu-id="2a214-110">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="2a214-111">Se si desidera disabilitare l'acquisizione del contesto, utilizzare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2a214-111">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="2a214-112">Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere l'articolo [sull'utilizzo del modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2a214-112">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="2a214-113">In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="2a214-113">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="2a214-114">È inoltre possibile `foreach` uscire da un ciclo mediante le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="2a214-114">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="2a214-115">Se l'istruzione `foreach` viene applicata a `null`, viene generata una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="2a214-115">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="2a214-116">Se la raccolta `foreach` di origine dell'istruzione `foreach` è vuota, il corpo del ciclo non viene eseguito e ignorato.</span><span class="sxs-lookup"><span data-stu-id="2a214-116">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="2a214-117">Esempi</span><span class="sxs-lookup"><span data-stu-id="2a214-117">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="2a214-118">L'esempio seguente mostra l'utilizzo dell'istruzione `foreach` con un'istanza del tipo <xref:System.Collections.Generic.List%601> che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="2a214-118">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="2a214-119">L'esempio successivo usa l'istruzione `foreach` con un'istanza del tipo <xref:System.Span%601?displayProperty=nameWithType>, che non implementa alcuna interfaccia:</span><span class="sxs-lookup"><span data-stu-id="2a214-119">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="2a214-120">L'esempio seguente usa una variabile di iterazione `ref` per impostare il valore di ogni elemento in una matrice di stackalloc.</span><span class="sxs-lookup"><span data-stu-id="2a214-120">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="2a214-121">La versione `ref readonly` esegue l'iterazione della raccolta per stampare tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="2a214-121">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="2a214-122">La dichiarazione `readonly` usa una dichiarazione di variabile locale implicita.</span><span class="sxs-lookup"><span data-stu-id="2a214-122">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="2a214-123">Le dichiarazioni di variabili implicite possono essere usate con le dichiarazioni `ref` o `ref readonly`, così come le dichiarazioni di variabili tipizzate.</span><span class="sxs-lookup"><span data-stu-id="2a214-123">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

<span data-ttu-id="2a214-124">L'esempio `await foreach` seguente usa per scorrere una raccolta che genera ogni elemento in modo asincrono:The following example uses to iterate a collection that generates each element asynchronously:</span><span class="sxs-lookup"><span data-stu-id="2a214-124">The following example uses `await foreach` to iterate a collection that generates each element asynchronously:</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#AwaitForeach)]

## <a name="c-language-specification"></a><span data-ttu-id="2a214-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2a214-125">C# language specification</span></span>

<span data-ttu-id="2a214-126">Per altre informazioni, vedere la sezione [L'istruzione foreach](~/_csharplang/spec/statements.md#the-foreach-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="2a214-126">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a214-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a214-127">See also</span></span>

- [<span data-ttu-id="2a214-128">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="2a214-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2a214-129">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="2a214-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2a214-130">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="2a214-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2a214-131">Utilizzo di foreach con array</span><span class="sxs-lookup"><span data-stu-id="2a214-131">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="2a214-132">per istruzione</span><span class="sxs-lookup"><span data-stu-id="2a214-132">for statement</span></span>](for.md)
