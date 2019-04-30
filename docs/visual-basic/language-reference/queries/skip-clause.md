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
ms.openlocfilehash: db2d79596895505ddaa7778e831082a94c7ad44e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945249"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="a589c-102">Clausola Skip (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a589c-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="a589c-103">Ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a589c-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a589c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a589c-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="a589c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a589c-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="a589c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a589c-106">Required.</span></span> <span data-ttu-id="a589c-107">Un valore o un'espressione che restituisce il numero di elementi della sequenza da ignorare.</span><span class="sxs-lookup"><span data-stu-id="a589c-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a589c-108">Note</span><span class="sxs-lookup"><span data-stu-id="a589c-108">Remarks</span></span>  
 <span data-ttu-id="a589c-109">Il `Skip` clausola provoca una query ignorare gli elementi all'inizio di un elenco dei risultati e restituire gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a589c-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="a589c-110">Il numero di elementi da ignorare è identificato dal `count` parametro.</span><span class="sxs-lookup"><span data-stu-id="a589c-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="a589c-111">È possibile usare la `Skip` clausola con il `Take` clausola per restituire un intervallo di dati da qualsiasi segmento di una query.</span><span class="sxs-lookup"><span data-stu-id="a589c-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="a589c-112">A questo scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo dal `Take` clausola.</span><span class="sxs-lookup"><span data-stu-id="a589c-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="a589c-113">Quando si usa la `Skip` clausola in una query, è necessario anche assicurarsi che i risultati vengono restituiti in un ordine che consentirà di `Skip` clausola per ignorare i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="a589c-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="a589c-114">Per altre informazioni su come ordinare i risultati della query, vedere [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a589c-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="a589c-115">È possibile usare il `SkipWhile` clausola per specificare che solo alcuni elementi vengono ignorati, a seconda di una condizione fornita.</span><span class="sxs-lookup"><span data-stu-id="a589c-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a589c-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a589c-116">Example</span></span>  
 <span data-ttu-id="a589c-117">Il codice seguente viene illustrato come utilizzare il `Skip` clausola insieme al `Take` clausola per restituire i dati da una query nelle pagine.</span><span class="sxs-lookup"><span data-stu-id="a589c-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="a589c-118">Il `GetCustomers` funzione Usa le `Skip` clausola per ignorare i clienti nell'elenco fino a quando il valore iniziale specificato valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire dal valore di indice specificato.</span><span class="sxs-lookup"><span data-stu-id="a589c-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a589c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a589c-119">See also</span></span>

- [<span data-ttu-id="a589c-120">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a589c-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a589c-121">Query</span><span class="sxs-lookup"><span data-stu-id="a589c-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a589c-122">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="a589c-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="a589c-123">Clausola From</span><span class="sxs-lookup"><span data-stu-id="a589c-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="a589c-124">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="a589c-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="a589c-125">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="a589c-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="a589c-126">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="a589c-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
