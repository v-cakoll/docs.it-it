---
title: Clausola where (Riferimento C#)
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: bc040e17f5c612b9fc43a9ef24fb6f15f0942b8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284303"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="c1fab-102">Clausola where (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="c1fab-102">where clause (C# Reference)</span></span>
<span data-ttu-id="c1fab-103">La clausola `where` viene usata in un'espressione di query per specificare quali elementi dell'origine dati verranno restituiti nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="c1fab-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="c1fab-104">Viene applicata una condizione booleana (*predicato*) a ogni elemento di origine (a cui fa riferimento la variabile di intervallo) e viene restituita quella per cui la condizione specificata è vera.</span><span class="sxs-lookup"><span data-stu-id="c1fab-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="c1fab-105">Una singola espressione di query può contenere più clausole `where` e una singola clausola può contenere più sottoespressioni di predicato.</span><span class="sxs-lookup"><span data-stu-id="c1fab-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1fab-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1fab-106">Example</span></span>  
 <span data-ttu-id="c1fab-107">Nell'esempio seguente la clausola `where` esclude tutti i numeri tranne quelli minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="c1fab-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="c1fab-108">Se si rimuove la clausola `where`, vengono restituiti tutti i numeri dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c1fab-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="c1fab-109">L'espressione `num < 5` è il predicato che viene applicato a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="c1fab-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="c1fab-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1fab-110">Example</span></span>  
 <span data-ttu-id="c1fab-111">In una singola clausola `where` è possibile specificare tutti i predicati necessari usando gli operatori [ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) e [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c1fab-111">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="c1fab-112">Nell'esempio seguente la query specifica due predicati per selezionare solo i numeri pari minori di cinque.</span><span class="sxs-lookup"><span data-stu-id="c1fab-112">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="c1fab-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1fab-113">Example</span></span>  
 <span data-ttu-id="c1fab-114">Una clausola `where` può contenere uno o più metodi che restituiscono valori booleani.</span><span class="sxs-lookup"><span data-stu-id="c1fab-114">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="c1fab-115">Nell'esempio seguente la clausola `where` usa un metodo per determinare se il valore corrente della variabile di intervallo è pari o dispari.</span><span class="sxs-lookup"><span data-stu-id="c1fab-115">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="c1fab-116">Note</span><span class="sxs-lookup"><span data-stu-id="c1fab-116">Remarks</span></span>  
 <span data-ttu-id="c1fab-117">La clausola `where` è un meccanismo di filtro.</span><span class="sxs-lookup"><span data-stu-id="c1fab-117">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="c1fab-118">Può essere posizionata praticamente ovunque in un'espressione di query, ma non può essere la prima o l'ultima clausola.</span><span class="sxs-lookup"><span data-stu-id="c1fab-118">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="c1fab-119">Una clausola `where` la può apparire prima o dopo una clausola [group](../../../csharp/language-reference/keywords/group-clause.md) a seconda se gli elementi di origine devono essere filtrati prima o dopo essere stati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="c1fab-119">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="c1fab-120">Se un predicato specificato non è valido per gli elementi nell'origine dati, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c1fab-120">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="c1fab-121">Questo è uno dei vantaggi del controllo efficace del tipo offerto da [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1fab-121">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="c1fab-122">In fase di compilazione, la parola chiave `where` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.Where%2A> dell'operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="c1fab-122">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fab-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1fab-123">See Also</span></span>  
 [<span data-ttu-id="c1fab-124">Parole chiave di query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="c1fab-124">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="c1fab-125">Clausola from</span><span class="sxs-lookup"><span data-stu-id="c1fab-125">from clause</span></span>](../../../csharp/language-reference/keywords/from-clause.md)  
 [<span data-ttu-id="c1fab-126">Clausola select</span><span class="sxs-lookup"><span data-stu-id="c1fab-126">select clause</span></span>](../../../csharp/language-reference/keywords/select-clause.md)  
 [<span data-ttu-id="c1fab-127">Filtraggio dei dati</span><span class="sxs-lookup"><span data-stu-id="c1fab-127">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)  
 [<span data-ttu-id="c1fab-128">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="c1fab-128">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="c1fab-129">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="c1fab-129">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
