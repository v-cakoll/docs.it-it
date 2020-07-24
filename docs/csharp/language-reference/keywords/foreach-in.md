---
title: Istruzione foreach in C#
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 4af431d29e538c1516efeaad3008eaa3b2229ece
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104236"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="a4ec1-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a4ec1-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="a4ec1-103">L' `foreach` istruzione esegue un'istruzione o un blocco di istruzioni per ogni elemento in un'istanza del tipo che implementa l' <xref:System.Collections.IEnumerable?displayProperty=nameWithType> <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia o, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="a4ec1-104">L' `foreach` istruzione non è limitata a tali tipi.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-104">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="a4ec1-105">È possibile usarlo con un'istanza di qualsiasi tipo che soddisfi le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-105">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="a4ec1-106">un tipo ha il metodo pubblico senza parametri il `GetEnumerator` cui tipo restituito è una classe, uno struct o un tipo di interfaccia,</span><span class="sxs-lookup"><span data-stu-id="a4ec1-106">a type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="a4ec1-107">il tipo restituito del metodo `GetEnumerator` include la proprietà `Current` pubblica e il metodo `MoveNext` pubblico senza parametri con tipo restituito <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-107">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="a4ec1-108">Nell'esempio seguente viene utilizzata l' `foreach` istruzione con un'istanza del <xref:System.Span%601?displayProperty=nameWithType> tipo, che non implementa alcuna interfaccia:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-108">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="a4ec1-109">A partire da C# 7,3, se la proprietà dell'enumeratore `Current` restituisce un [valore restituito di riferimento](ref.md#reference-return-values) ( `ref T` dove `T` è il tipo di un elemento della raccolta), è possibile dichiarare una variabile di iterazione con il `ref` `ref readonly` modificatore o, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-109">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="a4ec1-110">A partire da C# 8,0, è possibile usare l' `await foreach` istruzione per utilizzare un flusso asincrono di dati, ovvero il tipo di raccolta che implementa l' <xref:System.Collections.Generic.IAsyncEnumerable%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-110">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="a4ec1-111">Ogni iterazione del ciclo può essere sospesa mentre l'elemento successivo viene recuperato in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-111">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="a4ec1-112">Nell'esempio seguente viene illustrato come utilizzare l' `await foreach` istruzione:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-112">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="a4ec1-113">Per impostazione predefinita, gli elementi del flusso vengono elaborati nel contesto acquisito.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-113">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="a4ec1-114">Se si desidera disabilitare l'acquisizione del contesto, utilizzare il <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-114">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="a4ec1-115">Per ulteriori informazioni sui contesti di sincronizzazione e sull'acquisizione del contesto corrente, vedere [utilizzo del modello asincrono basato su attività](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="a4ec1-115">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="a4ec1-116">Per ulteriori informazioni sui flussi asincroni, vedere la sezione relativa ai [flussi asincroni](../../whats-new/csharp-8.md#asynchronous-streams) nell'articolo [novità di C# 8,0](../../whats-new/csharp-8.md) .</span><span class="sxs-lookup"><span data-stu-id="a4ec1-116">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="a4ec1-117">In un punto qualsiasi all'interno del blocco dell'istruzione `foreach` è possibile uscire dal ciclo usando l'istruzione [break](break.md) o passare all'iterazione successiva nel ciclo con l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="a4ec1-117">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="a4ec1-118">È anche possibile uscire `foreach` da un ciclo tramite le istruzioni [goto](goto.md), [return](return.md)o [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="a4ec1-118">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="a4ec1-119">Se l'istruzione `foreach` viene applicata a `null`, viene generata una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-119">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="a4ec1-120">Se la raccolta di origine dell' `foreach` istruzione è vuota, il corpo del `foreach` ciclo non viene eseguito e ignorato.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-120">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="a4ec1-121">Tipo di una variabile di iterazione</span><span class="sxs-lookup"><span data-stu-id="a4ec1-121">Type of an iteration variable</span></span>

<span data-ttu-id="a4ec1-122">È possibile usare la `var` parola chiave per consentire al compilatore di dedurre il tipo di una variabile di iterazione nell' `foreach` istruzione, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-122">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="a4ec1-123">È anche possibile specificare in modo esplicito il tipo di una variabile di iterazione, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-123">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="a4ec1-124">Nel form precedente, il tipo `T` di un elemento della raccolta deve essere convertibile in modo implicito o esplicito nel tipo `V` di una variabile di iterazione.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-124">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="a4ec1-125">Se una conversione esplicita da `T` a `V` non riesce in fase di esecuzione, l' `foreach` istruzione genera un'eccezione <xref:System.InvalidCastException> .</span><span class="sxs-lookup"><span data-stu-id="a4ec1-125">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="a4ec1-126">Se, ad esempio, `T` è un tipo di classe non sealed, `V` può essere qualsiasi tipo di interfaccia, anche quello che `T` non implementa.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-126">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="a4ec1-127">In fase di esecuzione, il tipo di un elemento della raccolta può essere quello che deriva da `T` e implementa effettivamente `V` .</span><span class="sxs-lookup"><span data-stu-id="a4ec1-127">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="a4ec1-128">In caso contrario, <xref:System.InvalidCastException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-128">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a4ec1-129">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a4ec1-129">C# language specification</span></span>

<span data-ttu-id="a4ec1-130">Per altre informazioni, vedere la sezione [L'istruzione foreach](~/_csharplang/spec/statements.md#the-foreach-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a4ec1-130">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4ec1-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4ec1-131">See also</span></span>

- [<span data-ttu-id="a4ec1-132">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="a4ec1-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a4ec1-133">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="a4ec1-133">C# keywords</span></span>](index.md)
- [<span data-ttu-id="a4ec1-134">Utilizzo di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="a4ec1-134">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="a4ec1-135">Istruzione for</span><span class="sxs-lookup"><span data-stu-id="a4ec1-135">for statement</span></span>](for.md)
