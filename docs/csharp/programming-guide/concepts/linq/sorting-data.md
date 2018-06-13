---
title: Ordinamento dei dati (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 6e223ecbfc68e904762bff998b3bd37f88607f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332559"
---
# <a name="sorting-data-c"></a><span data-ttu-id="fedea-102">Ordinamento dei dati (C#)</span><span class="sxs-lookup"><span data-stu-id="fedea-102">Sorting Data (C#)</span></span>
<span data-ttu-id="fedea-103">Un'operazione di ordinamento consente di ordinare gli elementi di una sequenza in base a uno o più attributi.</span><span class="sxs-lookup"><span data-stu-id="fedea-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="fedea-104">Il primo criterio di ordinamento consente di applicare un ordinamento principale agli elementi.</span><span class="sxs-lookup"><span data-stu-id="fedea-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="fedea-105">Specificando un secondo criterio di ordinamento, è possibile ordinare gli elementi all'interno di ogni gruppo di ordinamento principale.</span><span class="sxs-lookup"><span data-stu-id="fedea-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="fedea-106">La figura seguente illustra i risultati di un'operazione di ordinamento alfabetico in una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="fedea-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="fedea-107">![Operazione di ordinamento LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="fedea-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="fedea-108">La sezione seguente elenca i metodi dell'operatore query standard che ordina i dati.</span><span class="sxs-lookup"><span data-stu-id="fedea-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fedea-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="fedea-109">Methods</span></span>  
  
|<span data-ttu-id="fedea-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="fedea-110">Method Name</span></span>|<span data-ttu-id="fedea-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fedea-111">Description</span></span>|<span data-ttu-id="fedea-112">Sintassi di espressione della query C#</span><span class="sxs-lookup"><span data-stu-id="fedea-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="fedea-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="fedea-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="fedea-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="fedea-114">OrderBy</span></span>|<span data-ttu-id="fedea-115">Ordina i valori in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fedea-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="fedea-116">OrderByDescending</span></span>|<span data-ttu-id="fedea-117">Ordina i valori in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fedea-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="fedea-118">ThenBy</span></span>|<span data-ttu-id="fedea-119">Esegue un ordinamento secondario crescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fedea-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="fedea-120">ThenByDescending</span></span>|<span data-ttu-id="fedea-121">Esegue un ordinamento secondario decrescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fedea-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="fedea-122">Reverse</span></span>|<span data-ttu-id="fedea-123">Inverte l'ordine degli elementi in una Collection.</span><span class="sxs-lookup"><span data-stu-id="fedea-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="fedea-124">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="fedea-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="fedea-125">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="fedea-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="fedea-126">Esempi di ordinamento primario</span><span class="sxs-lookup"><span data-stu-id="fedea-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="fedea-127">Ordinamento primario crescente</span><span class="sxs-lookup"><span data-stu-id="fedea-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="fedea-128">Nell'esempio seguente viene illustrato come usare la clausola `orderby` in una query LINQ per ordinare le stringhe in una matrice in base alla lunghezza di stringa, in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="fedea-129">Ordinamento primario decrescente</span><span class="sxs-lookup"><span data-stu-id="fedea-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="fedea-130">Nell'esempio seguente viene illustrato come usare la clausola `orderby``descending` in una query LINQ per ordinare le stringhe in base alla prima lettera, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-130">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="fedea-131">Esempi di ordinamento secondario</span><span class="sxs-lookup"><span data-stu-id="fedea-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="fedea-132">Ordinamento secondario crescente</span><span class="sxs-lookup"><span data-stu-id="fedea-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="fedea-133">Nell'esempio seguente viene illustrato come usare la clausola `orderby` in una query LINQ per eseguire un ordinamento primario e secondario delle stringhe in una matrice.</span><span class="sxs-lookup"><span data-stu-id="fedea-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="fedea-134">Le stringhe vengono ordinate prima in base alla lunghezza e poi in base alla prima lettera della stringa, in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="fedea-135">Ordinamento secondario in ordine decrescente</span><span class="sxs-lookup"><span data-stu-id="fedea-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="fedea-136">L'esempio seguente illustra come usare la clausola `orderby``descending` in una query LINQ per eseguire un ordinamento primario, in ordine crescente, e un ordinamento secondario, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="fedea-136">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="fedea-137">Le stringhe vengono ordinate principalmente in base alla lunghezza e poi in base alla prima lettera della stringa.</span><span class="sxs-lookup"><span data-stu-id="fedea-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="fedea-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fedea-138">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="fedea-139">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="fedea-139">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="fedea-140">Clausola orderby</span><span class="sxs-lookup"><span data-stu-id="fedea-140">orderby clause</span></span>](../../../../csharp/language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="fedea-141">Procedura: Ordinare i risultati di una clausola join</span><span class="sxs-lookup"><span data-stu-id="fedea-141">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
 [<span data-ttu-id="fedea-142">Procedura: Ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fedea-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
