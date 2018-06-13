---
title: Clausola Skip (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 1810bf4a6573c6fa36f1d8149bf341d45cfd6f52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602827"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="b337b-102">Clausola Skip (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b337b-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="b337b-103">Ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="b337b-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b337b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b337b-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="b337b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b337b-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="b337b-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b337b-106">Required.</span></span> <span data-ttu-id="b337b-107">Un valore o un'espressione che restituisce il numero di elementi della sequenza da ignorare.</span><span class="sxs-lookup"><span data-stu-id="b337b-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b337b-108">Note</span><span class="sxs-lookup"><span data-stu-id="b337b-108">Remarks</span></span>  
 <span data-ttu-id="b337b-109">Il `Skip` clausola interrompe una query ignora gli elementi all'inizio di un elenco di risultati e restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="b337b-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="b337b-110">Il numero di elementi da ignorare è identificato dal `count` parametro.</span><span class="sxs-lookup"><span data-stu-id="b337b-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="b337b-111">È possibile utilizzare il `Skip` clausola con il `Take` clausola per restituire un intervallo di dati da qualsiasi segmento di una query.</span><span class="sxs-lookup"><span data-stu-id="b337b-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="b337b-112">A tale scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo per il `Take` clausola.</span><span class="sxs-lookup"><span data-stu-id="b337b-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="b337b-113">Quando si utilizza il `Skip` clausola in una query, è necessario anche per assicurarsi che i risultati vengono restituiti in un ordine, per consentire il `Skip` clausola per ignorare i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="b337b-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="b337b-114">Per ulteriori informazioni sull'ordinamento dei risultati della query, vedere [clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b337b-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="b337b-115">È possibile utilizzare il `SkipWhile` clausola per specificare che solo determinati elementi vengano ignorati, a seconda di una condizione fornita.</span><span class="sxs-lookup"><span data-stu-id="b337b-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b337b-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b337b-116">Example</span></span>  
 <span data-ttu-id="b337b-117">Nell'esempio di codice viene illustrato come utilizzare il `Skip` clausola con il `Take` clausola per restituire dati da una query in pagine.</span><span class="sxs-lookup"><span data-stu-id="b337b-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="b337b-118">Il `GetCustomers` funzione Usa il `Skip` clausola per ignorare i clienti nell'elenco finché l'iniziale fornito valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire da quel valore di indice.</span><span class="sxs-lookup"><span data-stu-id="b337b-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b337b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b337b-119">See Also</span></span>  
 [<span data-ttu-id="b337b-120">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b337b-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="b337b-121">Query</span><span class="sxs-lookup"><span data-stu-id="b337b-121">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="b337b-122">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="b337b-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="b337b-123">Clausola From</span><span class="sxs-lookup"><span data-stu-id="b337b-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="b337b-124">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="b337b-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="b337b-125">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="b337b-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="b337b-126">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="b337b-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
