---
title: Scrivere query LINQ in C#
description: Come si scrivono le query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: f3efbfd232bd7e19d3db56289f57724c71dca064
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="0b1c9-104">Scrivere query LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="0b1c9-104">Write LINQ queries in C#</span></span>

<span data-ttu-id="0b1c9-105">Questo argomento illustra i tre modi in cui è possibile scrivere una query LINQ in C#:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-105">This topic shows the three ways in which you can write a LINQ query in C#:</span></span>  
  
1.  <span data-ttu-id="0b1c9-106">Usare la sintassi di query.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-106">Use query syntax.</span></span>  
  
2.  <span data-ttu-id="0b1c9-107">Usare la sintassi di metodo.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-107">Use method syntax.</span></span>  
  
3.  <span data-ttu-id="0b1c9-108">Usare una combinazione di sintassi di query e sintassi di metodo.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-108">Use a combination of query syntax and method syntax.</span></span>  
  
 <span data-ttu-id="0b1c9-109">Gli esempi seguenti illustrano alcune semplici query LINQ usando ogni approccio indicato sopra.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-109">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="0b1c9-110">In generale, la regola è usare (1) ogni volta che è possibile e usare (2) e (3) ogni volta che è necessario.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-110">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b1c9-111">Queste query operano su raccolte in memoria semplici, tuttavia, la sintassi di base è identica a quella usata in LINQ to Entities e LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-111">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b1c9-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b1c9-112">Example</span></span>  
  
## <a name="query-syntax"></a><span data-ttu-id="0b1c9-113">Sintassi di query</span><span class="sxs-lookup"><span data-stu-id="0b1c9-113">Query syntax</span></span>  
 <span data-ttu-id="0b1c9-114">Il metodo consigliato per scrivere la maggior parte delle query è usare la *sintassi di query* per creare *espressioni di query*.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-114">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="0b1c9-115">Nell'esempio seguente sono riportate tre espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-115">The following example shows three query expressions.</span></span> <span data-ttu-id="0b1c9-116">La prima espressione di query dimostra in che modo si filtrano o si limitano i risultati applicando le condizioni con una clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-116">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="0b1c9-117">Restituisce tutti gli elementi nella sequenza di origine i cui valori sono maggiori di 7 o minori di 3.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-117">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="0b1c9-118">La seconda espressione illustra come ordinare i risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-118">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="0b1c9-119">La terza espressione illustra come raggruppare i risultati in base a una chiave.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-119">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="0b1c9-120">Questa query restituisce due gruppi in base alla prima lettera della parola.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-120">This query returns two groups based on the first letter of the word.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#5](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]  
  
 <span data-ttu-id="0b1c9-121">Si noti che il tipo delle query è <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-121">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="0b1c9-122">Tutte queste query potrebbero essere scritte usando `var` come indicato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-122">All of these queries could be written using `var` as shown in the following example:</span></span>  
  
 `var query = from num in numbers...`  
  
 <span data-ttu-id="0b1c9-123">In ognuno degli esempi precedenti le query non vengono effettivamente eseguite finché non si esegue l'iterazione della variabile di query in un'istruzione `foreach` o un'altra istruzione.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-123">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="0b1c9-124">Per altre informazioni, vedere l'[introduzione alle query LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0b1c9-124">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b1c9-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b1c9-125">Example</span></span>  
  
## <a name="method-syntax"></a><span data-ttu-id="0b1c9-126">Sintassi di metodo</span><span class="sxs-lookup"><span data-stu-id="0b1c9-126">Method syntax</span></span>  
 <span data-ttu-id="0b1c9-127">Alcune operazioni di query devono essere espresse come una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-127">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="0b1c9-128">I più comuni di tali metodi sono quelli che restituiscono valori numerici singleton, ad esempio <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> e così via.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-128">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="0b1c9-129">Questi metodi devono sempre essere chiamati per ultimi in una query poiché rappresentano solo un singolo valore e non possono essere usati come origine per un'operazione di query aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-129">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="0b1c9-130">Nell'esempio seguente viene illustrata una chiamata al metodo in un'espressione di query:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-130">The following example shows a method call in a query expression:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#6](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="0b1c9-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b1c9-131">Example</span></span>  
 <span data-ttu-id="0b1c9-132">Se il metodo usa i parametri Action o Func, questi vengono specificati sotto forma di espressione [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-132">If the method has  Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#7](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]  
  
 <span data-ttu-id="0b1c9-133">Nelle query precedenti solo la query n. 4 viene immediatamente eseguita.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-133">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="0b1c9-134">Ciò è dovuto al fatto che viene restituito un valore singolo invece di una raccolta <xref:System.Collections.Generic.IEnumerable%601> generica.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-134">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="0b1c9-135">Il metodo stesso deve usare `foreach` per calcolare il proprio valore.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-135">The method itself has to use `foreach` in order to compute its value.</span></span>  
  
 <span data-ttu-id="0b1c9-136">Ognuna delle query precedenti può essere scritta usando la tipizzazione implicita con [var](../language-reference/keywords/var.md), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-136">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#8](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="0b1c9-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b1c9-137">Example</span></span>  
  
## <a name="mixed-query-and-method-syntax"></a><span data-ttu-id="0b1c9-138">Sintassi di query e di metodo mista</span><span class="sxs-lookup"><span data-stu-id="0b1c9-138">Mixed query and method syntax</span></span>  
 <span data-ttu-id="0b1c9-139">In questo esempio viene illustrato come usare la sintassi di metodo per i risultati di una clausola di query.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-139">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="0b1c9-140">È sufficiente racchiudere l'espressione di query tra parentesi e quindi applicare l'operatore punto e chiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-140">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="0b1c9-141">Nell'esempio seguente la query n. 7 restituisce un conteggio dei numeri il cui valore è compreso tra 3 e 7.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-141">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="0b1c9-142">In generale, tuttavia, è preferibile usare una seconda variabile per archiviare il risultato della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-142">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="0b1c9-143">In questo modo è meno probabile che si crei confusione con i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-143">In this manner, the query is less likely to be confused with the results of the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#9](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]  
  
 <span data-ttu-id="0b1c9-144">Poiché la query n. 7 restituisce un singolo valore e non una raccolta, la query viene eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-144">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>  
  
 <span data-ttu-id="0b1c9-145">La query precedente può essere scritta usando la tipizzazione implicita con `var`, come segue:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-145">The previous query can be written by using implicit typing with `var`, as follows:</span></span>  
  
```csharp  
var numCount = (from num in numbers...  
```  
  
 <span data-ttu-id="0b1c9-146">Può essere scritta nella sintassi di metodo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-146">It can be written in method syntax as follows:</span></span>  
  
```csharp  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 <span data-ttu-id="0b1c9-147">Può essere scritta usando la tipizzazione esplicita, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-147">It can be written by using explicit typing, as follows:</span></span>  
  
```csharp  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b1c9-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b1c9-148">See Also</span></span>  
  <span data-ttu-id="0b1c9-149">[Procedura dettagliata: scrittura di query in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="0b1c9-149">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 [<span data-ttu-id="0b1c9-150">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="0b1c9-150">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="0b1c9-151">Clausola where</span><span class="sxs-lookup"><span data-stu-id="0b1c9-151">where clause</span></span>](../language-reference/keywords/where-clause.md)
