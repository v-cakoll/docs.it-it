---
title: Istruzione foreach in C#
ms.date: 06/03/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 1645a246c9feee2a92c0d4e4bbeda47f0afde7d9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401888"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="677c7-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="677c7-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="677c7-103">L'istruzione `foreach` esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="677c7-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="677c7-104">L' `foreach` istruzione non è limitata a tali tipi e può essere applicata a un'istanza di qualsiasi tipo che soddisfi le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="677c7-104">The `foreach` statement isn't limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="677c7-105">include il metodo `GetEnumerator` pubblico senza parametri con tipo restituito classe, struct o interfaccia,</span><span class="sxs-lookup"><span data-stu-id="677c7-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="677c7-106">il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="677c7-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="677c7-107">Nella maggior parte degli usi, `foreach` scorre un' `IEnumerable<T>` espressione in cui ogni elemento è di tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="677c7-107">In most uses, `foreach` iterates an `IEnumerable<T>` expression where each element is of type `T`.</span></span> <span data-ttu-id="677c7-108">Tuttavia, gli elementi possono essere di qualsiasi tipo con una conversione implicita o esplicita dal tipo della `Current` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="677c7-108">However, the elements may be any type that has an implicit or explicit conversion from the type of the `Current` property.</span></span> <span data-ttu-id="677c7-109">Se la `Current` proprietà restituisce `SomeType` , il tipo degli elementi può essere:</span><span class="sxs-lookup"><span data-stu-id="677c7-109">If the `Current` property returns `SomeType`, the type of the elements may be:</span></span>

- <span data-ttu-id="677c7-110">Qualsiasi classe di base di `SomeType` .</span><span class="sxs-lookup"><span data-stu-id="677c7-110">Any of the base classes of `SomeType`.</span></span>
- <span data-ttu-id="677c7-111">Qualsiasi interfaccia implementata da `SomeType` .</span><span class="sxs-lookup"><span data-stu-id="677c7-111">Any of the interfaces implemented by `SomeType`.</span></span>

<span data-ttu-id="677c7-112">Inoltre, se `SomeType` è un oggetto `class` o `interface` e Not `sealed` , il tipo di elementi può includere:</span><span class="sxs-lookup"><span data-stu-id="677c7-112">Furthermore, if `SomeType` is a `class` or an `interface` and not `sealed`, the type of elements may include:</span></span>

- <span data-ttu-id="677c7-113">Qualsiasi tipo derivato da `SomeType` .</span><span class="sxs-lookup"><span data-stu-id="677c7-113">Any type derived from `SomeType`.</span></span>
- <span data-ttu-id="677c7-114">Qualsiasi interfaccia arbitraria.</span><span class="sxs-lookup"><span data-stu-id="677c7-114">Any arbitrary interface.</span></span> <span data-ttu-id="677c7-115">Qualsiasi interfaccia è consentita perché qualsiasi interfaccia può essere implementata da una classe derivata da o da implementare `SomeType` .</span><span class="sxs-lookup"><span data-stu-id="677c7-115">Any interface is allowed because any interface may be implemented by a class derived from or implementing `SomeType`.</span></span>

<span data-ttu-id="677c7-116">È possibile dichiarare la variabile di iterazione usando qualsiasi tipo corrispondente alle regole precedenti.</span><span class="sxs-lookup"><span data-stu-id="677c7-116">You may declare the iteration variable using any type that matches the preceding rules.</span></span> <span data-ttu-id="677c7-117">Se la conversione da `SomeType` al tipo della variabile di iterazione richiede un cast esplicito, tale operazione può generare un'operazione <xref:System.InvalidCastException> quando la conversione non riesce.</span><span class="sxs-lookup"><span data-stu-id="677c7-117">If the conversion from `SomeType` to the type of the iteration variable requires an explicit cast, that operation may throw an <xref:System.InvalidCastException> when the conversion fails.</span></span>

<span data-ttu-id="677c7-118">A partire da C# 7,3, se la proprietà dell'enumeratore `Current` restituisce un [valore restituito di riferimento](ref.md#reference-return-values) ( `ref T` dove `T` è il tipo dell'elemento dell'insieme), è possibile dichiarare la variabile di iterazione con il `ref` `ref readonly` modificatore o.</span><span class="sxs-lookup"><span data-stu-id="677c7-118">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="677c7-119">A partire da C# 8,0, l' `await` operatore può essere applicato all' `foreach` istruzione quando il tipo di raccolta implementa l' <xref:System.Collections.Generic.IAsyncEnumerable%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="677c7-119">Beginning with C# 8.0, the `await` operator may be applied to the `foreach` statement when the collection type implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="677c7-120">Ogni iterazione del ciclo può essere sospesa mentre l'elemento successivo viene recuperato in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="677c7-120">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="677c7-121">Per impostazione predefinita, gli elementi del flusso vengono elaborati nel contesto acquisito.</span><span class="sxs-lookup"><span data-stu-id="677c7-121">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="677c7-122">Se si desidera disabilitare l'acquisizione del contesto, utilizzare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="677c7-122">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="677c7-123">Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere l'articolo sull' [utilizzo del modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="677c7-123">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="677c7-124">In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="677c7-124">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="677c7-125">È anche possibile uscire `foreach` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="677c7-125">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="677c7-126">Se l'istruzione `foreach` viene applicata a `null`, viene generata una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="677c7-126">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="677c7-127">Se la raccolta di origine dell' `foreach` istruzione è vuota, il corpo del `foreach` ciclo non viene eseguito e ignorato.</span><span class="sxs-lookup"><span data-stu-id="677c7-127">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="677c7-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="677c7-128">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="677c7-129">L'esempio seguente mostra l'utilizzo dell'istruzione `foreach` con un'istanza del tipo <xref:System.Collections.Generic.List%601> che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="677c7-129">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="677c7-130">L'esempio successivo usa l'istruzione `foreach` con un'istanza del tipo <xref:System.Span%601?displayProperty=nameWithType>, che non implementa alcuna interfaccia:</span><span class="sxs-lookup"><span data-stu-id="677c7-130">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="677c7-131">L'esempio seguente usa una variabile di iterazione `ref` per impostare il valore di ogni elemento in una matrice di stackalloc.</span><span class="sxs-lookup"><span data-stu-id="677c7-131">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="677c7-132">La versione `ref readonly` esegue l'iterazione della raccolta per stampare tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="677c7-132">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="677c7-133">La dichiarazione `readonly` usa una dichiarazione di variabile locale implicita.</span><span class="sxs-lookup"><span data-stu-id="677c7-133">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="677c7-134">Le dichiarazioni di variabili implicite possono essere usate con le dichiarazioni `ref` o `ref readonly`, così come le dichiarazioni di variabili tipizzate.</span><span class="sxs-lookup"><span data-stu-id="677c7-134">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="677c7-135">Nell'esempio seguente viene usato `await foreach` per eseguire l'iterazione di una raccolta che genera ogni elemento in modo asincrono:</span><span class="sxs-lookup"><span data-stu-id="677c7-135">The following example uses `await foreach` to iterate a collection that generates each element asynchronously:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach"  :::

## <a name="c-language-specification"></a><span data-ttu-id="677c7-136">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="677c7-136">C# language specification</span></span>

<span data-ttu-id="677c7-137">Per altre informazioni, vedere la sezione [L'istruzione foreach](~/_csharplang/spec/statements.md#the-foreach-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="677c7-137">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="677c7-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="677c7-138">See also</span></span>

- [<span data-ttu-id="677c7-139">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="677c7-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="677c7-140">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="677c7-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="677c7-141">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="677c7-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="677c7-142">Utilizzo di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="677c7-142">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="677c7-143">Istruzione for</span><span class="sxs-lookup"><span data-stu-id="677c7-143">for statement</span></span>](for.md)
