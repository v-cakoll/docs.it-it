---
title: Clausola Take (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 0dddb411af1b4ee269e091c07553a94589d90b2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604029"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="63ecb-102">Clausola Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63ecb-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="63ecb-103">Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="63ecb-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ecb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63ecb-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="63ecb-105">Parti</span><span class="sxs-lookup"><span data-stu-id="63ecb-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="63ecb-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="63ecb-106">Required.</span></span> <span data-ttu-id="63ecb-107">Un valore o un'espressione che restituisce il numero di elementi della sequenza da restituire.</span><span class="sxs-lookup"><span data-stu-id="63ecb-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ecb-108">Note</span><span class="sxs-lookup"><span data-stu-id="63ecb-108">Remarks</span></span>  
 <span data-ttu-id="63ecb-109">Il `Take` clausola interrompe una query includere un numero specificato di elementi contigui dall'inizio di un elenco di risultati.</span><span class="sxs-lookup"><span data-stu-id="63ecb-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="63ecb-110">Da cui viene specificato il numero di elementi da includere il `count` parametro.</span><span class="sxs-lookup"><span data-stu-id="63ecb-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="63ecb-111">È possibile utilizzare il `Take` clausola con il `Skip` clausola per restituire un intervallo di dati da qualsiasi segmento di una query.</span><span class="sxs-lookup"><span data-stu-id="63ecb-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="63ecb-112">A tale scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo per il `Take` clausola.</span><span class="sxs-lookup"><span data-stu-id="63ecb-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="63ecb-113">In questo caso, il `Take` clausola deve essere specificata dopo il `Skip` clausola.</span><span class="sxs-lookup"><span data-stu-id="63ecb-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="63ecb-114">Quando si utilizza il `Take` clausola in una query, è necessario anche per assicurarsi che i risultati vengono restituiti in un ordine, per consentire il `Take` clausola per includere i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="63ecb-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="63ecb-115">Per ulteriori informazioni sull'ordinamento dei risultati della query, vedere [clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="63ecb-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="63ecb-116">È possibile utilizzare il `TakeWhile` clausola per specificare che vengano restituiti solo determinati elementi, a seconda di una condizione fornita.</span><span class="sxs-lookup"><span data-stu-id="63ecb-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63ecb-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="63ecb-117">Example</span></span>  
 <span data-ttu-id="63ecb-118">Nell'esempio di codice viene illustrato come utilizzare il `Take` clausola con il `Skip` clausola per restituire dati da una query in pagine.</span><span class="sxs-lookup"><span data-stu-id="63ecb-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="63ecb-119">La funzione GetCustomers utilizza il `Skip` clausola per ignorare i clienti nell'elenco finché l'iniziale fornito valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire da quel valore di indice.</span><span class="sxs-lookup"><span data-stu-id="63ecb-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="63ecb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63ecb-120">See Also</span></span>  
 [<span data-ttu-id="63ecb-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63ecb-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="63ecb-122">Query</span><span class="sxs-lookup"><span data-stu-id="63ecb-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="63ecb-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="63ecb-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="63ecb-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="63ecb-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="63ecb-125">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="63ecb-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="63ecb-126">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="63ecb-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="63ecb-127">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="63ecb-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
