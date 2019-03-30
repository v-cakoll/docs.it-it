---
title: Operazioni di aggregazione (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 5d8e5c589b19527062f7752b2f795c8396683bbd
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675640"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="21299-102">Operazioni di aggregazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21299-102">Aggregation Operations (Visual Basic)</span></span>
<span data-ttu-id="21299-103">Un'operazione di aggregazione calcola un singolo valore da una raccolta di valori.</span><span class="sxs-lookup"><span data-stu-id="21299-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="21299-104">Un esempio di operazione di aggregazione è rappresentato dal calcolo della temperatura media giornaliera dai valori della temperatura giornaliera di un mese.</span><span class="sxs-lookup"><span data-stu-id="21299-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="21299-105">La figura seguente illustra i risultati di due operazioni di aggregazione diverse in una sequenza di numeri.</span><span class="sxs-lookup"><span data-stu-id="21299-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="21299-106">La prima operazione somma i numeri.</span><span class="sxs-lookup"><span data-stu-id="21299-106">The first operation sums the numbers.</span></span> <span data-ttu-id="21299-107">La seconda operazione restituisce il valore massimo nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="21299-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![Figura che illustra operazioni di aggregazione LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="21299-109">La sezione seguente elenca i metodi degli operatori di query standard che eseguono operazioni di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="21299-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21299-110">Metodi</span><span class="sxs-lookup"><span data-stu-id="21299-110">Methods</span></span>  
  
|<span data-ttu-id="21299-111">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="21299-111">Method Name</span></span>|<span data-ttu-id="21299-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21299-112">Description</span></span>|<span data-ttu-id="21299-113">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21299-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="21299-114">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="21299-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="21299-115">Aggregate</span><span class="sxs-lookup"><span data-stu-id="21299-115">Aggregate</span></span>|<span data-ttu-id="21299-116">Esegue un'operazione di aggregazione personalizzata sui valori di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="21299-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="21299-117">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="21299-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21299-118">Media</span><span class="sxs-lookup"><span data-stu-id="21299-118">Average</span></span>|<span data-ttu-id="21299-119">Calcola il valore medio di una raccolta di valori.</span><span class="sxs-lookup"><span data-stu-id="21299-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21299-120">Conteggio</span><span class="sxs-lookup"><span data-stu-id="21299-120">Count</span></span>|<span data-ttu-id="21299-121">Conta gli elementi in una raccolta e, facoltativamente, solo gli elementi che soddisfano una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="21299-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21299-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="21299-122">LongCount</span></span>|<span data-ttu-id="21299-123">Conta gli elementi in una raccolta di grandi dimensioni e, facoltativamente, solo gli elementi che soddisfano una funzione di predicato.</span><span class="sxs-lookup"><span data-stu-id="21299-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21299-124">Max</span><span class="sxs-lookup"><span data-stu-id="21299-124">Max</span></span>|<span data-ttu-id="21299-125">Determina il valore massimo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="21299-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21299-126">Min</span><span class="sxs-lookup"><span data-stu-id="21299-126">Min</span></span>|<span data-ttu-id="21299-127">Determina il valore minimo in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="21299-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21299-128">Sum</span><span class="sxs-lookup"><span data-stu-id="21299-128">Sum</span></span>|<span data-ttu-id="21299-129">Calcola la somma dei valori in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="21299-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="21299-130">Esempi di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="21299-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="21299-131">Media</span><span class="sxs-lookup"><span data-stu-id="21299-131">Average</span></span>  
 <span data-ttu-id="21299-132">Il codice seguente viene illustrato come utilizzare il `Aggregate Into Average` clausola in Visual Basic per calcolare la temperatura media in una matrice di numeri che rappresentano le temperature.</span><span class="sxs-lookup"><span data-stu-id="21299-132">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="21299-133">Conteggio</span><span class="sxs-lookup"><span data-stu-id="21299-133">Count</span></span>  
 <span data-ttu-id="21299-134">Il codice seguente viene illustrato come utilizzare il `Aggregate Into Count` clausola in Visual Basic per contare il numero di valori in una matrice che sono maggiori o uguali a 80.</span><span class="sxs-lookup"><span data-stu-id="21299-134">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="21299-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="21299-135">LongCount</span></span>  
 <span data-ttu-id="21299-136">Il codice seguente viene illustrato come utilizzare il `Aggregate Into LongCount` clausola per contare il numero di valori in una matrice.</span><span class="sxs-lookup"><span data-stu-id="21299-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="21299-137">Max</span><span class="sxs-lookup"><span data-stu-id="21299-137">Max</span></span>  
 <span data-ttu-id="21299-138">Il codice seguente viene illustrato come utilizzare il `Aggregate Into Max` clausola per la quale calcolare la temperatura massima in una matrice di numeri che rappresentano le temperature.</span><span class="sxs-lookup"><span data-stu-id="21299-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="21299-139">Min</span><span class="sxs-lookup"><span data-stu-id="21299-139">Min</span></span>  
 <span data-ttu-id="21299-140">Il codice seguente viene illustrato come utilizzare il `Aggregate Into Min` clausola per la quale calcolare la temperatura minima in una matrice di numeri che rappresentano le temperature.</span><span class="sxs-lookup"><span data-stu-id="21299-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="21299-141">Sum</span><span class="sxs-lookup"><span data-stu-id="21299-141">Sum</span></span>  
 <span data-ttu-id="21299-142">Il codice seguente viene illustrato come utilizzare il `Aggregate Into Sum` clausola per calcolare l'importo di spesa totale da una matrice di valori che rappresentano le spese.</span><span class="sxs-lookup"><span data-stu-id="21299-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="21299-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21299-143">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="21299-144">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21299-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="21299-145">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="21299-145">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="21299-146">Procedura: Calcolare i valori di colonna in un File di testo CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21299-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [<span data-ttu-id="21299-147">Procedura: Conteggio, somma o Media di dati</span><span class="sxs-lookup"><span data-stu-id="21299-147">How to: Count, Sum, or Average Data</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [<span data-ttu-id="21299-148">Procedura: Trovare il valore minimo o massimo in un risultato di Query</span><span class="sxs-lookup"><span data-stu-id="21299-148">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [<span data-ttu-id="21299-149">Procedura: Eseguire una query per i File più grande o in un albero di Directory (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21299-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="21299-150">Procedura: Eseguire una query per il numero totale di byte in un Set di cartelle (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21299-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
