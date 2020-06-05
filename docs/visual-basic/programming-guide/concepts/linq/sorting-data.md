---
title: Ordinamento dei dati
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: a5ccff745995ed7f41731cf98fb7c49d3247d994
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406794"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="b67fd-102">Ordinamento dei dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b67fd-102">Sorting Data (Visual Basic)</span></span>

<span data-ttu-id="b67fd-103">Un'operazione di ordinamento consente di ordinare gli elementi di una sequenza in base a uno o più attributi.</span><span class="sxs-lookup"><span data-stu-id="b67fd-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="b67fd-104">Il primo criterio di ordinamento consente di applicare un ordinamento principale agli elementi.</span><span class="sxs-lookup"><span data-stu-id="b67fd-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="b67fd-105">Specificando un secondo criterio di ordinamento, è possibile ordinare gli elementi all'interno di ogni gruppo di ordinamento principale.</span><span class="sxs-lookup"><span data-stu-id="b67fd-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>

<span data-ttu-id="b67fd-106">La figura seguente illustra i risultati di un'operazione di ordinamento alfabetico in una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="b67fd-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>

![Immagine che illustra un'operazione di ordinamento alfabetico.](./media/sorting-data/alphabetical-sort-operation.png)

<span data-ttu-id="b67fd-108">La sezione seguente elenca i metodi dell'operatore query standard che ordina i dati.</span><span class="sxs-lookup"><span data-stu-id="b67fd-108">The standard query operator methods that sort data are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="b67fd-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="b67fd-109">Methods</span></span>

|<span data-ttu-id="b67fd-110">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="b67fd-110">Method Name</span></span>|<span data-ttu-id="b67fd-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b67fd-111">Description</span></span>|<span data-ttu-id="b67fd-112">Visual Basic sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="b67fd-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="b67fd-113">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b67fd-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="b67fd-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="b67fd-114">OrderBy</span></span>|<span data-ttu-id="b67fd-115">Ordina i valori in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b67fd-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="b67fd-116">OrderByDescending</span></span>|<span data-ttu-id="b67fd-117">Ordina i valori in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b67fd-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="b67fd-118">ThenBy</span></span>|<span data-ttu-id="b67fd-119">Esegue un ordinamento secondario crescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b67fd-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="b67fd-120">ThenByDescending</span></span>|<span data-ttu-id="b67fd-121">Esegue un ordinamento secondario decrescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b67fd-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="b67fd-122">Reverse</span></span>|<span data-ttu-id="b67fd-123">Inverte l'ordine degli elementi in una Collection.</span><span class="sxs-lookup"><span data-stu-id="b67fd-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="b67fd-124">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="b67fd-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="b67fd-125">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="b67fd-125">Query Expression Syntax Examples</span></span>

### <a name="primary-sort-examples"></a><span data-ttu-id="b67fd-126">Esempi di ordinamento primario</span><span class="sxs-lookup"><span data-stu-id="b67fd-126">Primary Sort Examples</span></span>

#### <a name="primary-ascending-sort"></a><span data-ttu-id="b67fd-127">Ordinamento primario crescente</span><span class="sxs-lookup"><span data-stu-id="b67fd-127">Primary Ascending Sort</span></span>

<span data-ttu-id="b67fd-128">Nell'esempio seguente viene illustrato come usare la clausola `Order By` in una query LINQ per ordinare le stringhe in una matrice in base alla lunghezza di stringa, in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>

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

#### <a name="primary-descending-sort"></a><span data-ttu-id="b67fd-129">Ordinamento primario decrescente</span><span class="sxs-lookup"><span data-stu-id="b67fd-129">Primary Descending Sort</span></span>

<span data-ttu-id="b67fd-130">Nell'esempio seguente viene illustrato come usare la clausola `Order By Descending` in una query LINQ per ordinare le stringhe in base alla prima lettera, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>

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

### <a name="secondary-sort-examples"></a><span data-ttu-id="b67fd-131">Esempi di ordinamento secondario</span><span class="sxs-lookup"><span data-stu-id="b67fd-131">Secondary Sort Examples</span></span>

#### <a name="secondary-ascending-sort"></a><span data-ttu-id="b67fd-132">Ordinamento secondario crescente</span><span class="sxs-lookup"><span data-stu-id="b67fd-132">Secondary Ascending Sort</span></span>

<span data-ttu-id="b67fd-133">Nell'esempio seguente viene illustrato come usare la clausola `Order By` in una query LINQ per eseguire un ordinamento primario e secondario delle stringhe in una matrice.</span><span class="sxs-lookup"><span data-stu-id="b67fd-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="b67fd-134">Le stringhe vengono ordinate prima in base alla lunghezza e poi in base alla prima lettera della stringa, in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>

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

#### <a name="secondary-descending-sort"></a><span data-ttu-id="b67fd-135">Ordinamento secondario in ordine decrescente</span><span class="sxs-lookup"><span data-stu-id="b67fd-135">Secondary Descending Sort</span></span>

<span data-ttu-id="b67fd-136">L'esempio seguente illustra come usare la clausola `Order By Descending` in una query LINQ per eseguire un ordinamento primario, in ordine crescente, e un ordinamento secondario, in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="b67fd-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="b67fd-137">Le stringhe vengono ordinate principalmente in base alla lunghezza e poi in base alla prima lettera della stringa.</span><span class="sxs-lookup"><span data-stu-id="b67fd-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b67fd-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b67fd-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b67fd-139">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b67fd-139">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="b67fd-140">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="b67fd-140">Order By Clause</span></span>](../../../language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="b67fd-141">Procedura: Ordinare i risultati di query</span><span class="sxs-lookup"><span data-stu-id="b67fd-141">How to: Sort Query Results</span></span>](../../language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [<span data-ttu-id="b67fd-142">Procedura: ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b67fd-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
