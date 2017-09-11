---
title: Clausola where (Riferimento C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
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
ms.openlocfilehash: 97d7c16d6bf8048e621141fff52a47907881fd2f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="where-clause-c-reference"></a><span data-ttu-id="e25d5-102">Clausola where (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="e25d5-102">where clause (C# Reference)</span></span>
<span data-ttu-id="e25d5-103">La clausola `where` viene usata in un'espressione di query per specificare quali elementi dell'origine dati verranno restituiti nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="e25d5-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="e25d5-104">Viene applicata una condizione booleana (*predicato*) a ogni elemento di origine (a cui fa riferimento la variabile di intervallo) e viene restituita quella per cui la condizione specificata è vera.</span><span class="sxs-lookup"><span data-stu-id="e25d5-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="e25d5-105">Una singola espressione di query può contenere più clausole `where` e una singola clausola può contenere più sottoespressioni di predicato.</span><span class="sxs-lookup"><span data-stu-id="e25d5-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25d5-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e25d5-106">Example</span></span>  
 <span data-ttu-id="e25d5-107">Nell'esempio seguente la clausola `where` esclude tutti i numeri tranne quelli minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="e25d5-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="e25d5-108">Se si rimuove la clausola `where`, vengono restituiti tutti i numeri dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e25d5-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="e25d5-109">L'espressione `num < 5` è il predicato che viene applicato a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="e25d5-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 <span data-ttu-id="e25d5-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e25d5-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25d5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e25d5-111">Example</span></span>  
 <span data-ttu-id="e25d5-112">In una singola clausola `where` è possibile specificare tutti i predicati necessari usando gli operatori [ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) e [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e25d5-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="e25d5-113">Nell'esempio seguente la query specifica due predicati per selezionare solo i numeri pari minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="e25d5-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 <span data-ttu-id="e25d5-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e25d5-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25d5-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="e25d5-115">Example</span></span>  
 <span data-ttu-id="e25d5-116">Una clausola `where` può contenere uno o più metodi che restituiscono valori booleani.</span><span class="sxs-lookup"><span data-stu-id="e25d5-116">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="e25d5-117">Nell'esempio seguente la clausola `where` usa un metodo per determinare se il valore corrente della variabile di intervallo è pari o dispari.</span><span class="sxs-lookup"><span data-stu-id="e25d5-117">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 <span data-ttu-id="e25d5-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e25d5-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e25d5-119">Note</span><span class="sxs-lookup"><span data-stu-id="e25d5-119">Remarks</span></span>  
 <span data-ttu-id="e25d5-120">La clausola `where` è un meccanismo di filtro.</span><span class="sxs-lookup"><span data-stu-id="e25d5-120">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="e25d5-121">Può essere posizionata praticamente ovunque in un'espressione di query, ma non può essere la prima o l'ultima clausola.</span><span class="sxs-lookup"><span data-stu-id="e25d5-121">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="e25d5-122">Una clausola `where` la può apparire prima o dopo una clausola [group](../../../csharp/language-reference/keywords/group-clause.md) a seconda se gli elementi di origine devono essere filtrati prima o dopo essere stati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="e25d5-122">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="e25d5-123">Se un predicato specificato non è valido per gli elementi nell'origine dati, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e25d5-123">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="e25d5-124">Questo è uno dei vantaggi del controllo efficace del tipo offerto da [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e25d5-124">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="e25d5-125">In fase di compilazione, la parola chiave `where` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.Where%2A> dell'operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="e25d5-125">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25d5-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e25d5-126">See Also</span></span>  
 <span data-ttu-id="e25d5-127">[Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="e25d5-127">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="e25d5-128">[Clausola from](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="e25d5-128">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="e25d5-129">[Clausola select](../../../csharp/language-reference/keywords/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="e25d5-129">[select clause](../../../csharp/language-reference/keywords/select-clause.md) </span></span>  
 <span data-ttu-id="e25d5-130">[Filtraggio dei dati](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span><span class="sxs-lookup"><span data-stu-id="e25d5-130">[Filtering Data](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span></span>  
 <span data-ttu-id="e25d5-131">[Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="e25d5-131">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="e25d5-132">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="e25d5-132">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

