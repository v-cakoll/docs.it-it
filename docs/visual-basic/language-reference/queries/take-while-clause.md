---
title: Clausola Take While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 3dfb70066d88683e60f3bf4199441ab3024ef36c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565111"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="19a22-102">Clausola Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19a22-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="19a22-103">Include gli elementi in una raccolta finché una condizione specificata è `true` e quindi ignora gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="19a22-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19a22-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="19a22-105">Parti</span><span class="sxs-lookup"><span data-stu-id="19a22-105">Parts</span></span>  
  
|<span data-ttu-id="19a22-106">Termine</span><span class="sxs-lookup"><span data-stu-id="19a22-106">Term</span></span>|<span data-ttu-id="19a22-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="19a22-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="19a22-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="19a22-108">Required.</span></span> <span data-ttu-id="19a22-109">Un'espressione che rappresenta una condizione di test per gli elementi.</span><span class="sxs-lookup"><span data-stu-id="19a22-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="19a22-110">L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un `Integer` deve essere valutata come un `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="19a22-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19a22-111">Note</span><span class="sxs-lookup"><span data-stu-id="19a22-111">Remarks</span></span>  
 <span data-ttu-id="19a22-112">Il `Take While` clausola include gli elementi dall'inizio del risultato della query finché l'oggetto fornito `expression` restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="19a22-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="19a22-113">Dopo il `expression` restituisce `false`, la query ignora tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="19a22-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="19a22-114">Il `expression` viene ignorato per i risultati rimanenti.</span><span class="sxs-lookup"><span data-stu-id="19a22-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="19a22-115">Il `Take While` clausola differisce dal `Where` clausola in quanto il `Where` clausola può essere utilizzata per includere tutti gli elementi da una query che soddisfano una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="19a22-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="19a22-116">Il `Take While` clausola include gli elementi solo fino al primo non viene soddisfatta la condizione.</span><span class="sxs-lookup"><span data-stu-id="19a22-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="19a22-117">Il `Take While` clausola è particolarmente utile quando si lavora con un risultato della query ordinati.</span><span class="sxs-lookup"><span data-stu-id="19a22-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19a22-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="19a22-118">Example</span></span>  
 <span data-ttu-id="19a22-119">Il codice seguente viene illustrato come utilizzare il `Take While` clausola per recuperare i risultati fino a quando non viene trovato il primo dei clienti senza ordini.</span><span class="sxs-lookup"><span data-stu-id="19a22-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="19a22-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19a22-120">See also</span></span>
- [<span data-ttu-id="19a22-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19a22-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="19a22-122">Query</span><span class="sxs-lookup"><span data-stu-id="19a22-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="19a22-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="19a22-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="19a22-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="19a22-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="19a22-125">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="19a22-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="19a22-126">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="19a22-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="19a22-127">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="19a22-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
