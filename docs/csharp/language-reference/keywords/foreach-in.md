---
title: foreach, in (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aed1d4f086f0b1334df750fd912d20d66326a043
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="e6734-102">foreach, in (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e6734-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="e6734-103">L'istruzione `foreach` ripete un gruppo di istruzioni incorporate per ciascun elemento di una matrice o di una raccolta di oggetti che implementa l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=fullName> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e6734-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface.</span></span> <span data-ttu-id="e6734-104">L'istruzione `foreach` viene usata per eseguire l'iterazione della raccolta e ottenere le informazioni desiderate. Per evitare effetti indesiderati, non deve tuttavia essere usata per aggiungere o rimuovere elementi dalla raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="e6734-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="e6734-105">Se è necessario aggiungere o rimuovere elementi dalla raccolta di origine, usare il ciclo [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="e6734-105">If you need to add or remove items from the source collection, use a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span>  
  
 <span data-ttu-id="e6734-106">L'esecuzione delle istruzioni incorporate viene ripetuta per ogni elemento nella matrice o nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e6734-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="e6734-107">Quando l'iterazione è stata completata per tutti gli elementi nella raccolta, il controllo viene trasferito alla prima istruzione che segue il blocco `foreach`.</span><span class="sxs-lookup"><span data-stu-id="e6734-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>  
  
 <span data-ttu-id="e6734-108">In un punto qualsiasi all'interno del blocco `foreach` è possibile uscire dal ciclo usando la parola chiave [break](../../../csharp/language-reference/keywords/break.md) o passare all'iterazione successiva nel ciclo con la parola chiave [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="e6734-108">At any point within the `foreach` block, you can break out of the loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or step to the next iteration in the loop by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span>  
  
 <span data-ttu-id="e6734-109">È anche possibile uscire da un ciclo `foreach` tramite le istruzioni [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="e6734-109">A `foreach` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
 <span data-ttu-id="e6734-110">Per altre informazioni sulla parola chiave `foreach` e per esempi di codice, vedere gli argomenti riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="e6734-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  
  
 [<span data-ttu-id="e6734-111">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="e6734-111">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [<span data-ttu-id="e6734-112">Procedura: Accedere a una classe Collection con foreach</span><span class="sxs-lookup"><span data-stu-id="e6734-112">How to: Access a Collection Class with foreach</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a><span data-ttu-id="e6734-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6734-113">Example</span></span>  
 <span data-ttu-id="e6734-114">Il codice seguente illustra tre esempi:</span><span class="sxs-lookup"><span data-stu-id="e6734-114">The following code shows three examples:</span></span>  
  
-   <span data-ttu-id="e6734-115">Un ciclo `foreach` tipico che visualizza il contenuto di una matrice di numeri interi</span><span class="sxs-lookup"><span data-stu-id="e6734-115">a typical `foreach` loop that displays the contents of an array of integers</span></span>  
  
-   <span data-ttu-id="e6734-116">Un ciclo [for](../../../csharp/language-reference/keywords/for.md) che esegue la stessa operazione</span><span class="sxs-lookup"><span data-stu-id="e6734-116">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>  
  
-   <span data-ttu-id="e6734-117">Un ciclo `foreach` che gestisce un conteggio del numero di elementi nella matrice</span><span class="sxs-lookup"><span data-stu-id="e6734-117">a `foreach` loop that maintains a count of the number of elements in the array</span></span>  
  
 <span data-ttu-id="e6734-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6734-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e6734-119">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e6734-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6734-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6734-120">See Also</span></span>  
 <span data-ttu-id="e6734-121">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6734-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e6734-122">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6734-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e6734-123">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6734-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e6734-124">[Istruzioni di iterazione](../../../csharp/language-reference/keywords/iteration-statements.md) </span><span class="sxs-lookup"><span data-stu-id="e6734-124">[Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md) </span></span>  
 [<span data-ttu-id="e6734-125">for</span><span class="sxs-lookup"><span data-stu-id="e6734-125">for</span></span>](../../../csharp/language-reference/keywords/for.md)

