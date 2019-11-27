---
title: Clausola Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349639"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="bc01f-102">Clausola Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc01f-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="bc01f-103">Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="bc01f-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc01f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc01f-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="bc01f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="bc01f-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="bc01f-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="bc01f-106">Required.</span></span> <span data-ttu-id="bc01f-107">Valore o espressione che restituisce il numero di elementi della sequenza da restituire.</span><span class="sxs-lookup"><span data-stu-id="bc01f-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc01f-108">Note</span><span class="sxs-lookup"><span data-stu-id="bc01f-108">Remarks</span></span>  
 <span data-ttu-id="bc01f-109">La clausola `Take` fa in modo che una query includa un numero specificato di elementi contigui dall'inizio di un elenco di risultati.</span><span class="sxs-lookup"><span data-stu-id="bc01f-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="bc01f-110">Il numero di elementi da includere è specificato dal parametro `count`.</span><span class="sxs-lookup"><span data-stu-id="bc01f-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="bc01f-111">È possibile utilizzare la clausola `Take` con la clausola `Skip` per restituire un intervallo di dati da qualsiasi segmento di una query.</span><span class="sxs-lookup"><span data-stu-id="bc01f-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="bc01f-112">A tale scopo, passare l'indice del primo elemento dell'intervallo alla clausola `Skip` e la dimensione dell'intervallo alla clausola `Take`.</span><span class="sxs-lookup"><span data-stu-id="bc01f-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="bc01f-113">In questo caso, è necessario specificare la clausola `Take` dopo la clausola `Skip`.</span><span class="sxs-lookup"><span data-stu-id="bc01f-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="bc01f-114">Quando si utilizza la clausola `Take` in una query, potrebbe essere necessario verificare che i risultati vengano restituiti in un ordine che consenta alla clausola `Take` di includere i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="bc01f-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="bc01f-115">Per ulteriori informazioni sull'ordinamento dei risultati di query, vedere [clausola ORDER BY](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="bc01f-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="bc01f-116">È possibile utilizzare la clausola `TakeWhile` per specificare che vengano restituiti solo determinati elementi, a seconda della condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="bc01f-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc01f-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc01f-117">Example</span></span>  
 <span data-ttu-id="bc01f-118">Nell'esempio di codice seguente viene utilizzata la clausola `Take` insieme alla clausola `Skip` per restituire dati da una query in pagine.</span><span class="sxs-lookup"><span data-stu-id="bc01f-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="bc01f-119">La funzione GetCustomers usa la clausola `Skip` per ignorare i clienti nell'elenco fino al valore di indice iniziale fornito e usa la clausola `Take` per restituire una pagina di clienti a partire da tale valore di indice.</span><span class="sxs-lookup"><span data-stu-id="bc01f-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bc01f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc01f-120">See also</span></span>

- [<span data-ttu-id="bc01f-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc01f-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="bc01f-122">Query</span><span class="sxs-lookup"><span data-stu-id="bc01f-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="bc01f-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="bc01f-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="bc01f-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="bc01f-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="bc01f-125">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="bc01f-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="bc01f-126">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="bc01f-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="bc01f-127">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="bc01f-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
