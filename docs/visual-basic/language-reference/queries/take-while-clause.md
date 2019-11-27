---
title: Clausola Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347103"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="24d2c-102">Clausola Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24d2c-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="24d2c-103">Include gli elementi in una raccolta finché una condizione specificata è `true` e quindi ignora gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="24d2c-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24d2c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24d2c-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="24d2c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="24d2c-105">Parts</span></span>  
  
|<span data-ttu-id="24d2c-106">Termine</span><span class="sxs-lookup"><span data-stu-id="24d2c-106">Term</span></span>|<span data-ttu-id="24d2c-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="24d2c-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="24d2c-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="24d2c-108">Required.</span></span> <span data-ttu-id="24d2c-109">Espressione che rappresenta una condizione per cui verificare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="24d2c-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="24d2c-110">L'espressione deve restituire un valore `Boolean` o un equivalente funzionale, ad esempio un `Integer` da valutare come `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="24d2c-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24d2c-111">Note</span><span class="sxs-lookup"><span data-stu-id="24d2c-111">Remarks</span></span>  
 <span data-ttu-id="24d2c-112">La clausola `Take While` include gli elementi dall'inizio di un risultato della query fino a quando l'`expression` fornito non restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="24d2c-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="24d2c-113">Quando il `expression` restituisce `false`, la query ignorerà tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="24d2c-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="24d2c-114">Il `expression` viene ignorato per i risultati rimanenti.</span><span class="sxs-lookup"><span data-stu-id="24d2c-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="24d2c-115">La clausola `Take While` differisce dalla clausola `Where` in quanto la clausola `Where` può essere utilizzata per includere tutti gli elementi di una query che soddisfano una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="24d2c-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="24d2c-116">La clausola `Take While` include gli elementi solo fino alla prima volta che la condizione non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="24d2c-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="24d2c-117">La clausola `Take While` è particolarmente utile quando si utilizza un risultato di query ordinato.</span><span class="sxs-lookup"><span data-stu-id="24d2c-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24d2c-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="24d2c-118">Example</span></span>  
 <span data-ttu-id="24d2c-119">Nell'esempio di codice seguente viene utilizzata la clausola `Take While` per recuperare i risultati fino a quando non viene trovato il primo cliente senza ordini.</span><span class="sxs-lookup"><span data-stu-id="24d2c-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="24d2c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24d2c-120">See also</span></span>

- [<span data-ttu-id="24d2c-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24d2c-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="24d2c-122">Query</span><span class="sxs-lookup"><span data-stu-id="24d2c-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="24d2c-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="24d2c-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="24d2c-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="24d2c-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="24d2c-125">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="24d2c-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="24d2c-126">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="24d2c-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="24d2c-127">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="24d2c-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
