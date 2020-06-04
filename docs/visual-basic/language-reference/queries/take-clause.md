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
ms.openlocfilehash: 25dd06905525a96bc1504f033eb4f19af6d454a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359632"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="baf48-102">Clausola Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baf48-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="baf48-103">Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="baf48-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="baf48-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="baf48-105">Parti</span><span class="sxs-lookup"><span data-stu-id="baf48-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="baf48-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="baf48-106">Required.</span></span> <span data-ttu-id="baf48-107">Valore o espressione che restituisce il numero di elementi della sequenza da restituire.</span><span class="sxs-lookup"><span data-stu-id="baf48-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baf48-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="baf48-108">Remarks</span></span>  
 <span data-ttu-id="baf48-109">La `Take` clausola fa in modo che una query includa un numero specificato di elementi contigui dall'inizio di un elenco di risultati.</span><span class="sxs-lookup"><span data-stu-id="baf48-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="baf48-110">Il numero di elementi da includere è specificato dal `count` parametro.</span><span class="sxs-lookup"><span data-stu-id="baf48-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="baf48-111">È possibile utilizzare la `Take` clausola con la `Skip` clausola per restituire un intervallo di dati da qualsiasi segmento di una query.</span><span class="sxs-lookup"><span data-stu-id="baf48-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="baf48-112">A tale scopo, passare l'indice del primo elemento dell'intervallo alla `Skip` clausola e la dimensione dell'intervallo alla `Take` clausola.</span><span class="sxs-lookup"><span data-stu-id="baf48-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="baf48-113">In questo caso, la `Take` clausola deve essere specificata dopo la `Skip` clausola.</span><span class="sxs-lookup"><span data-stu-id="baf48-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="baf48-114">Quando si utilizza la `Take` clausola in una query, potrebbe essere necessario assicurarsi che i risultati vengano restituiti in un ordine che consenta alla `Take` clausola di includere i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="baf48-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="baf48-115">Per ulteriori informazioni sull'ordinamento dei risultati di query, vedere [clausola ORDER BY](order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="baf48-115">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="baf48-116">È possibile utilizzare la `TakeWhile` clausola per specificare che vengano restituiti solo determinati elementi, a seconda della condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="baf48-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baf48-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="baf48-117">Example</span></span>  
 <span data-ttu-id="baf48-118">Nell'esempio di codice seguente viene utilizzata la `Take` clausola insieme alla `Skip` clausola per restituire dati da una query in pagine.</span><span class="sxs-lookup"><span data-stu-id="baf48-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="baf48-119">La funzione GetCustomers utilizza la `Skip` clausola per ignorare i clienti nell'elenco fino al valore di indice iniziale fornito e utilizza la `Take` clausola per restituire una pagina di clienti a partire da tale valore di indice.</span><span class="sxs-lookup"><span data-stu-id="baf48-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="baf48-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baf48-120">See also</span></span>

- [<span data-ttu-id="baf48-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="baf48-121">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="baf48-122">Query</span><span class="sxs-lookup"><span data-stu-id="baf48-122">Queries</span></span>](index.md)
- [<span data-ttu-id="baf48-123">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="baf48-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="baf48-124">Clausola from</span><span class="sxs-lookup"><span data-stu-id="baf48-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="baf48-125">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="baf48-125">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="baf48-126">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="baf48-126">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="baf48-127">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="baf48-127">Skip Clause</span></span>](skip-clause.md)
