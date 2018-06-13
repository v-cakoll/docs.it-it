---
title: Scrivere query LINQ in C#
description: Come si scrivono le query.
ms.date: 12/1/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: a9683dbf3c4101829054477824ccc7135f20f535
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288837"
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="f14fd-103">Scrivere query LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="f14fd-103">Write LINQ queries in C#</span></span>

<span data-ttu-id="f14fd-104">Questo argomento illustra i tre modi in cui è possibile scrivere una query LINQ in C#:</span><span class="sxs-lookup"><span data-stu-id="f14fd-104">This topic shows the three ways in which you can write a LINQ query in C#:</span></span>  
  
1.  <span data-ttu-id="f14fd-105">Usare la sintassi di query.</span><span class="sxs-lookup"><span data-stu-id="f14fd-105">Use query syntax.</span></span>  
  
2.  <span data-ttu-id="f14fd-106">Usare la sintassi di metodo.</span><span class="sxs-lookup"><span data-stu-id="f14fd-106">Use method syntax.</span></span>  
  
3.  <span data-ttu-id="f14fd-107">Usare una combinazione di sintassi di query e sintassi di metodo.</span><span class="sxs-lookup"><span data-stu-id="f14fd-107">Use a combination of query syntax and method syntax.</span></span>  
  
 <span data-ttu-id="f14fd-108">Gli esempi seguenti illustrano alcune semplici query LINQ usando ogni approccio indicato sopra.</span><span class="sxs-lookup"><span data-stu-id="f14fd-108">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="f14fd-109">In generale, la regola è usare (1) ogni volta che è possibile e usare (2) e (3) ogni volta che è necessario.</span><span class="sxs-lookup"><span data-stu-id="f14fd-109">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f14fd-110">Queste query operano su raccolte in memoria semplici, tuttavia, la sintassi di base è identica a quella usata in LINQ to Entities e LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="f14fd-110">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f14fd-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f14fd-111">Example</span></span>  
  
## <a name="query-syntax"></a><span data-ttu-id="f14fd-112">Sintassi di query</span><span class="sxs-lookup"><span data-stu-id="f14fd-112">Query syntax</span></span>  
 <span data-ttu-id="f14fd-113">Il metodo consigliato per scrivere la maggior parte delle query è usare la *sintassi di query* per creare *espressioni di query*.</span><span class="sxs-lookup"><span data-stu-id="f14fd-113">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="f14fd-114">Nell'esempio seguente sono riportate tre espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="f14fd-114">The following example shows three query expressions.</span></span> <span data-ttu-id="f14fd-115">La prima espressione di query dimostra in che modo si filtrano o si limitano i risultati applicando le condizioni con una clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="f14fd-115">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="f14fd-116">Restituisce tutti gli elementi nella sequenza di origine i cui valori sono maggiori di 7 o minori di 3.</span><span class="sxs-lookup"><span data-stu-id="f14fd-116">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="f14fd-117">La seconda espressione illustra come ordinare i risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="f14fd-117">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="f14fd-118">La terza espressione illustra come raggruppare i risultati in base a una chiave.</span><span class="sxs-lookup"><span data-stu-id="f14fd-118">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="f14fd-119">Questa query restituisce due gruppi in base alla prima lettera della parola.</span><span class="sxs-lookup"><span data-stu-id="f14fd-119">This query returns two groups based on the first letter of the word.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#5](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]  
  
 <span data-ttu-id="f14fd-120">Si noti che il tipo delle query è <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="f14fd-120">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="f14fd-121">Tutte queste query potrebbero essere scritte usando `var` come indicato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f14fd-121">All of these queries could be written using `var` as shown in the following example:</span></span>  
  
 `var query = from num in numbers...`  
  
 <span data-ttu-id="f14fd-122">In ognuno degli esempi precedenti le query non vengono effettivamente eseguite finché non si esegue l'iterazione della variabile di query in un'istruzione `foreach` o un'altra istruzione.</span><span class="sxs-lookup"><span data-stu-id="f14fd-122">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="f14fd-123">Per altre informazioni, vedere l'[introduzione alle query LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f14fd-123">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f14fd-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="f14fd-124">Example</span></span>  
  
## <a name="method-syntax"></a><span data-ttu-id="f14fd-125">Sintassi di metodo</span><span class="sxs-lookup"><span data-stu-id="f14fd-125">Method syntax</span></span>  
 <span data-ttu-id="f14fd-126">Alcune operazioni di query devono essere espresse come una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="f14fd-126">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="f14fd-127">I più comuni di tali metodi sono quelli che restituiscono valori numerici singleton, ad esempio <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> e così via.</span><span class="sxs-lookup"><span data-stu-id="f14fd-127">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="f14fd-128">Questi metodi devono sempre essere chiamati per ultimi in una query poiché rappresentano solo un singolo valore e non possono essere usati come origine per un'operazione di query aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="f14fd-128">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="f14fd-129">Nell'esempio seguente viene illustrata una chiamata al metodo in un'espressione di query:</span><span class="sxs-lookup"><span data-stu-id="f14fd-129">The following example shows a method call in a query expression:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#6](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="f14fd-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="f14fd-130">Example</span></span>  
 <span data-ttu-id="f14fd-131">Se il metodo usa i parametri Action o Func, questi vengono specificati sotto forma di espressione [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f14fd-131">If the method has  Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#7](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]  
  
 <span data-ttu-id="f14fd-132">Nelle query precedenti solo la query n. 4 viene immediatamente eseguita.</span><span class="sxs-lookup"><span data-stu-id="f14fd-132">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="f14fd-133">Ciò è dovuto al fatto che viene restituito un valore singolo invece di una raccolta <xref:System.Collections.Generic.IEnumerable%601> generica.</span><span class="sxs-lookup"><span data-stu-id="f14fd-133">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="f14fd-134">Il metodo stesso deve usare `foreach` per calcolare il proprio valore.</span><span class="sxs-lookup"><span data-stu-id="f14fd-134">The method itself has to use `foreach` in order to compute its value.</span></span>  
  
 <span data-ttu-id="f14fd-135">Ognuna delle query precedenti può essere scritta usando la tipizzazione implicita con [var](../language-reference/keywords/var.md), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f14fd-135">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#8](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="f14fd-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="f14fd-136">Example</span></span>  
  
## <a name="mixed-query-and-method-syntax"></a><span data-ttu-id="f14fd-137">Sintassi di query e di metodo mista</span><span class="sxs-lookup"><span data-stu-id="f14fd-137">Mixed query and method syntax</span></span>  
 <span data-ttu-id="f14fd-138">In questo esempio viene illustrato come usare la sintassi di metodo per i risultati di una clausola di query.</span><span class="sxs-lookup"><span data-stu-id="f14fd-138">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="f14fd-139">È sufficiente racchiudere l'espressione di query tra parentesi e quindi applicare l'operatore punto e chiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="f14fd-139">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="f14fd-140">Nell'esempio seguente la query n. 7 restituisce un conteggio dei numeri il cui valore è compreso tra 3 e 7.</span><span class="sxs-lookup"><span data-stu-id="f14fd-140">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="f14fd-141">In generale, tuttavia, è preferibile usare una seconda variabile per archiviare il risultato della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="f14fd-141">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="f14fd-142">In questo modo è meno probabile che si crei confusione con i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="f14fd-142">In this manner, the query is less likely to be confused with the results of the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#9](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]  
  
 <span data-ttu-id="f14fd-143">Poiché la query n. 7 restituisce un singolo valore e non una raccolta, la query viene eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="f14fd-143">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>  
  
 <span data-ttu-id="f14fd-144">La query precedente può essere scritta usando la tipizzazione implicita con `var`, come segue:</span><span class="sxs-lookup"><span data-stu-id="f14fd-144">The previous query can be written by using implicit typing with `var`, as follows:</span></span>  
  
```csharp  
var numCount = (from num in numbers...  
```  
  
 <span data-ttu-id="f14fd-145">Può essere scritta nella sintassi di metodo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f14fd-145">It can be written in method syntax as follows:</span></span>  
  
```csharp  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 <span data-ttu-id="f14fd-146">Può essere scritta usando la tipizzazione esplicita, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f14fd-146">It can be written by using explicit typing, as follows:</span></span>  
  
```csharp  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## <a name="see-also"></a><span data-ttu-id="f14fd-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f14fd-147">See Also</span></span>  
  <span data-ttu-id="f14fd-148">[Procedura dettagliata: scrittura di query in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f14fd-148">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 [<span data-ttu-id="f14fd-149">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="f14fd-149">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="f14fd-150">Clausola where</span><span class="sxs-lookup"><span data-stu-id="f14fd-150">where clause</span></span>](../language-reference/keywords/where-clause.md)
