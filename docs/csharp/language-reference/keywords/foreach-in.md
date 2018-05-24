---
title: foreach, in (Riferimenti per C#)
ms.date: 10/11/2017
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: c0b1481988a2e3199fc6d06ca30cb5194ab2f44c
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2018
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="cae84-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cae84-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="cae84-103">L'istruzione `foreach` ripete un gruppo di istruzioni incorporate per ciascun elemento di una matrice o di una raccolta di oggetti che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cae84-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="cae84-104">L'[istruzione foreach](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement) viene usata per eseguire l'iterazione della raccolta e ottenere le informazioni desiderate. Per evitare effetti indesiderati, non deve tuttavia essere usata per aggiungere o rimuovere elementi dalla raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="cae84-104">The [foreach statement](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement) is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="cae84-105">Se è necessario aggiungere o rimuovere elementi dalla raccolta di origine, usare il ciclo [for](for.md).</span><span class="sxs-lookup"><span data-stu-id="cae84-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="cae84-106">L'esecuzione delle istruzioni incorporate viene ripetuta per ogni elemento nella matrice o nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="cae84-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="cae84-107">Quando l'iterazione è stata completata per tutti gli elementi nella raccolta, il controllo viene trasferito alla prima istruzione che segue il blocco `foreach`.</span><span class="sxs-lookup"><span data-stu-id="cae84-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="cae84-108">In un punto qualsiasi all'interno del blocco `foreach` è possibile uscire dal ciclo usando la parola chiave [break](break.md) o passare all'iterazione successiva nel ciclo con la parola chiave [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="cae84-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="cae84-109">È anche possibile uscire da un ciclo `foreach` tramite le istruzioni [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="cae84-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="cae84-110">Per altre informazioni sulla parola chiave `foreach` e per esempi di codice, vedere gli argomenti riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="cae84-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="cae84-111">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="cae84-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="cae84-112">Procedura: Accedere a una classe Collection con foreach</span><span class="sxs-lookup"><span data-stu-id="cae84-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="cae84-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="cae84-113">Example</span></span>

<span data-ttu-id="cae84-114">Il codice seguente illustra tre esempi:</span><span class="sxs-lookup"><span data-stu-id="cae84-114">The following code shows three examples:</span></span>

> [!TIP]
> <span data-ttu-id="cae84-115">È possibile modificare gli esempi per sperimentare con la sintassi e provare utilizzi diversi più simili al proprio caso d'uso.</span><span class="sxs-lookup"><span data-stu-id="cae84-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="cae84-116">Premere "Esegui" per eseguire il codice, quindi apportare le modifiche e premere di nuovo "Esegui".</span><span class="sxs-lookup"><span data-stu-id="cae84-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="cae84-117">Un ciclo `foreach` tipico che visualizza il contenuto di una matrice di numeri interi</span><span class="sxs-lookup"><span data-stu-id="cae84-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="cae84-118">Un ciclo [for](../../../csharp/language-reference/keywords/for.md) che esegue la stessa operazione</span><span class="sxs-lookup"><span data-stu-id="cae84-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="cae84-119">Un ciclo `foreach` che gestisce un conteggio del numero di elementi nella matrice</span><span class="sxs-lookup"><span data-stu-id="cae84-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="cae84-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cae84-120">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cae84-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cae84-121">See Also</span></span>  

[<span data-ttu-id="cae84-122">Istruzione foreach (specifica del linguaggio C#)</span><span class="sxs-lookup"><span data-stu-id="cae84-122">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)

[<span data-ttu-id="cae84-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cae84-123">C# Reference</span></span>](../index.md)

[<span data-ttu-id="cae84-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cae84-124">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="cae84-125">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="cae84-125">C# Keywords</span></span>](index.md)

[<span data-ttu-id="cae84-126">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="cae84-126">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="cae84-127">for</span><span class="sxs-lookup"><span data-stu-id="cae84-127">for</span></span>](for.md)
