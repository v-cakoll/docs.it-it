---
title: Clausola Skip
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 427d14453260a54bd3f2ab9a8ac75dedacd291f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359658"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="7ad86-102">Clausola Skip (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ad86-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="7ad86-103">Ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7ad86-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ad86-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="7ad86-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7ad86-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="7ad86-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7ad86-106">Required.</span></span> <span data-ttu-id="7ad86-107">Valore o espressione che restituisce il numero di elementi della sequenza da ignorare.</span><span class="sxs-lookup"><span data-stu-id="7ad86-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ad86-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="7ad86-108">Remarks</span></span>  
 <span data-ttu-id="7ad86-109">La `Skip` clausola fa in modo che una query ignori gli elementi all'inizio di un elenco di risultati e restituisca gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="7ad86-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="7ad86-110">Il numero di elementi da ignorare è identificato dal `count` parametro.</span><span class="sxs-lookup"><span data-stu-id="7ad86-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="7ad86-111">È possibile utilizzare la `Skip` clausola con la `Take` clausola per restituire un intervallo di dati da qualsiasi segmento di una query.</span><span class="sxs-lookup"><span data-stu-id="7ad86-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="7ad86-112">A tale scopo, passare l'indice del primo elemento dell'intervallo alla `Skip` clausola e la dimensione dell'intervallo alla `Take` clausola.</span><span class="sxs-lookup"><span data-stu-id="7ad86-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="7ad86-113">Quando si utilizza la `Skip` clausola in una query, potrebbe essere necessario assicurarsi che i risultati vengano restituiti in un ordine che consentirà alla `Skip` clausola di ignorare i risultati desiderati.</span><span class="sxs-lookup"><span data-stu-id="7ad86-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="7ad86-114">Per ulteriori informazioni sull'ordinamento dei risultati di query, vedere [clausola ORDER BY](order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7ad86-114">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="7ad86-115">È possibile usare la `SkipWhile` clausola per specificare che solo determinati elementi vengono ignorati, a seconda della condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="7ad86-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ad86-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ad86-116">Example</span></span>  
 <span data-ttu-id="7ad86-117">Nell'esempio di codice seguente viene utilizzata la `Skip` clausola insieme alla `Take` clausola per restituire dati da una query in pagine.</span><span class="sxs-lookup"><span data-stu-id="7ad86-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="7ad86-118">La `GetCustomers` funzione utilizza la `Skip` clausola per ignorare i clienti nell'elenco fino al valore di indice iniziale fornito e utilizza la `Take` clausola per restituire una pagina di clienti a partire da tale valore di indice.</span><span class="sxs-lookup"><span data-stu-id="7ad86-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7ad86-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ad86-119">See also</span></span>

- [<span data-ttu-id="7ad86-120">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ad86-120">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="7ad86-121">Query</span><span class="sxs-lookup"><span data-stu-id="7ad86-121">Queries</span></span>](index.md)
- [<span data-ttu-id="7ad86-122">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="7ad86-122">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="7ad86-123">Clausola from</span><span class="sxs-lookup"><span data-stu-id="7ad86-123">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="7ad86-124">Clausola Order By</span><span class="sxs-lookup"><span data-stu-id="7ad86-124">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="7ad86-125">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="7ad86-125">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="7ad86-126">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="7ad86-126">Take Clause</span></span>](take-clause.md)
