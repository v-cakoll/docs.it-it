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
ms.openlocfilehash: 2705b61f4ebc839a9db98f037f303b4df78bbe5f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976213"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="74621-102">Clausola Take (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74621-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="74621-103">Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="74621-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74621-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74621-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="74621-105">Parti</span><span class="sxs-lookup"><span data-stu-id="74621-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="74621-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="74621-106">Required.</span></span> <span data-ttu-id="74621-107">Un valore o un'espressione che restituisce il numero di elementi della sequenza da restituire.</span><span class="sxs-lookup"><span data-stu-id="74621-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74621-108">Note</span><span class="sxs-lookup"><span data-stu-id="74621-108">Remarks</span></span>  
 <span data-ttu-id="74621-109">Il `Take` clausola provoca una query includere un numero specificato di elementi contigui dall'inizio di un elenco di risultati.</span><span class="sxs-lookup"><span data-stu-id="74621-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="74621-110">Viene specificato il numero di elementi da includere per il `count` parametro.</span><span class="sxs-lookup"><span data-stu-id="74621-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="74621-111">È possibile usare la `Take` clausola con il `Skip` clausola per restituire un intervallo di dati da qualsiasi segmento di una query.</span><span class="sxs-lookup"><span data-stu-id="74621-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="74621-112">A questo scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo dal `Take` clausola.</span><span class="sxs-lookup"><span data-stu-id="74621-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="74621-113">In questo caso, il `Take` clausola deve essere specificata dopo il `Skip` clausola.</span><span class="sxs-lookup"><span data-stu-id="74621-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="74621-114">Quando si usa la `Take` clausola in una query, è necessario anche assicurarsi che i risultati vengono restituiti in un ordine che consentirà di `Take` clausola per includere i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="74621-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="74621-115">Per altre informazioni su come ordinare i risultati della query, vedere [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="74621-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="74621-116">È possibile usare il `TakeWhile` clausola per specificare che vengano restituiti solo determinati elementi, in base a una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="74621-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74621-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="74621-117">Example</span></span>  
 <span data-ttu-id="74621-118">Il codice seguente viene illustrato come utilizzare il `Take` clausola insieme al `Skip` clausola per restituire i dati da una query nelle pagine.</span><span class="sxs-lookup"><span data-stu-id="74621-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="74621-119">La funzione GetCustomers utilizza il `Skip` clausola per ignorare i clienti nell'elenco fino a quando il valore iniziale specificato valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire dal valore di indice specificato.</span><span class="sxs-lookup"><span data-stu-id="74621-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="74621-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74621-120">See also</span></span>
- [<span data-ttu-id="74621-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74621-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="74621-122">Query</span><span class="sxs-lookup"><span data-stu-id="74621-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="74621-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="74621-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="74621-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="74621-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="74621-125">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="74621-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="74621-126">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="74621-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="74621-127">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="74621-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
