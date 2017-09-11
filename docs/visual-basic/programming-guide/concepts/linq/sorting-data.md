---
title: Ordinamento dei dati (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1870d401ffdeeb2452ace1b74a8fb70e19c9b9ed
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="c5253-102">Ordinamento dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5253-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="c5253-103">Un'operazione di ordinamento Ordina gli elementi di una sequenza in base a uno o più attributi.</span><span class="sxs-lookup"><span data-stu-id="c5253-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="c5253-104">Il primo criterio di ordinamento consente di applicare un ordinamento principale agli elementi.</span><span class="sxs-lookup"><span data-stu-id="c5253-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="c5253-105">Specificando un secondo criterio di ordinamento, è possibile ordinare gli elementi all'interno di ogni gruppo di ordinamento principale.</span><span class="sxs-lookup"><span data-stu-id="c5253-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="c5253-106">Nella figura seguente mostra i risultati di un'operazione di ordinamento alfabetico su una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="c5253-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="c5253-107">![Operazione di ordinamento LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="c5253-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="c5253-108">Nella sezione seguente sono elencati i metodi dell'operatore query standard che ordinano i dati.</span><span class="sxs-lookup"><span data-stu-id="c5253-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5253-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="c5253-109">Methods</span></span>  
  
|<span data-ttu-id="c5253-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="c5253-110">Method Name</span></span>|<span data-ttu-id="c5253-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5253-111">Description</span></span>|<span data-ttu-id="c5253-112">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5253-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="c5253-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c5253-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="c5253-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="c5253-114">OrderBy</span></span>|<span data-ttu-id="c5253-115">Ordina i valori in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-115">Sorts values in ascending order.</span></span>|`Order By`|<span data-ttu-id="c5253-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c5253-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="c5253-118">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="c5253-118">OrderByDescending</span></span>|<span data-ttu-id="c5253-119">Ordina i valori in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-119">Sorts values in descending order.</span></span>|`Order By … Descending`|<span data-ttu-id="c5253-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c5253-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="c5253-122">ThenBy</span><span class="sxs-lookup"><span data-stu-id="c5253-122">ThenBy</span></span>|<span data-ttu-id="c5253-123">Esegue un ordinamento secondario in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-123">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<span data-ttu-id="c5253-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c5253-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="c5253-126">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="c5253-126">ThenByDescending</span></span>|<span data-ttu-id="c5253-127">Esegue un ordinamento secondario in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-127">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<span data-ttu-id="c5253-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c5253-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="c5253-130">Reverse</span><span class="sxs-lookup"><span data-stu-id="c5253-130">Reverse</span></span>|<span data-ttu-id="c5253-131">Inverte l'ordine degli elementi in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="c5253-131">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="c5253-132">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="c5253-132">Not applicable.</span></span>|<span data-ttu-id="c5253-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c5253-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c5253-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="c5253-135">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="c5253-135">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="c5253-136">Esempi di ordinamento principale</span><span class="sxs-lookup"><span data-stu-id="c5253-136">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="c5253-137">Ordinamento crescente principale</span><span class="sxs-lookup"><span data-stu-id="c5253-137">Primary Ascending Sort</span></span>  
 <span data-ttu-id="c5253-138">Nell'esempio seguente viene illustrato come utilizzare il `Order By` clausola in una query LINQ per ordinare le stringhe in una matrice in base alla lunghezza di stringa, in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-138">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
' quick  
' brown  
' jumps  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="c5253-139">Ordinamento decrescente principale</span><span class="sxs-lookup"><span data-stu-id="c5253-139">Primary Descending Sort</span></span>  
 <span data-ttu-id="c5253-140">Nell'esempio seguente viene illustrato come utilizzare il `Order By Descending` clausola in una query LINQ per ordinare le stringhe in base alla prima lettera, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-140">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' quick  
' jumps  
' fox  
' brown  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="c5253-141">Esempi di ordinamento secondaria</span><span class="sxs-lookup"><span data-stu-id="c5253-141">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="c5253-142">Ordinamento crescente secondario</span><span class="sxs-lookup"><span data-stu-id="c5253-142">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="c5253-143">Nell'esempio seguente viene illustrato come utilizzare il `Order By` clausola in una query LINQ per eseguire un ordinamento primario e secondario delle stringhe in una matrice.</span><span class="sxs-lookup"><span data-stu-id="c5253-143">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="c5253-144">Le stringhe vengono ordinate principalmente dalla lunghezza e poi in base alla prima lettera della stringa, in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-144">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1)   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' brown  
' jumps  
' quick  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="c5253-145">Ordinamento decrescente secondario</span><span class="sxs-lookup"><span data-stu-id="c5253-145">Secondary Descending Sort</span></span>  
 <span data-ttu-id="c5253-146">Nell'esempio seguente viene illustrato come utilizzare il `Order By Descending` clausola in una query LINQ per eseguire un ordinamento principale, in ordine crescente e un ordinamento secondario, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="c5253-146">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="c5253-147">Le stringhe vengono ordinate principalmente dalla lunghezza e poi in base alla prima lettera della stringa.</span><span class="sxs-lookup"><span data-stu-id="c5253-147">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' quick  
' jumps  
' brown  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5253-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5253-148">See Also</span></span>  
 <span data-ttu-id="c5253-149"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="c5253-149"><xref:System.Linq></span></span>   
<span data-ttu-id="c5253-150"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="c5253-150"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="c5253-151"> [Clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="c5253-151"> [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="c5253-152"> [Procedura: ordinare i risultati della Query](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="c5253-152"> [How to: Sort Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="c5253-153"> [Procedura: ordinare o filtrare i dati di testo da qualsiasi parola o campo (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="c5253-153"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
