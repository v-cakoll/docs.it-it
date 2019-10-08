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
ms.openlocfilehash: fe6ee470698504bc0434930cc9aa6de712e04254
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004683"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="814bf-102">Clausola Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="814bf-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="814bf-103">Include gli elementi in una raccolta finché una condizione specificata è `true` e quindi ignora gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="814bf-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="814bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="814bf-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="814bf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="814bf-105">Parts</span></span>  
  
|<span data-ttu-id="814bf-106">Nome</span><span class="sxs-lookup"><span data-stu-id="814bf-106">Term</span></span>|<span data-ttu-id="814bf-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="814bf-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="814bf-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="814bf-108">Required.</span></span> <span data-ttu-id="814bf-109">Espressione che rappresenta una condizione per cui verificare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="814bf-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="814bf-110">L'espressione deve restituire un valore `Boolean` o un equivalente funzionale, ad esempio un `Integer` da valutare come `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="814bf-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="814bf-111">Note</span><span class="sxs-lookup"><span data-stu-id="814bf-111">Remarks</span></span>  
 <span data-ttu-id="814bf-112">La clausola `Take While` include gli elementi dall'inizio di un risultato della query fino a quando il `expression` fornito restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="814bf-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="814bf-113">Dopo che `expression` restituisce `false`, la query ignorerà tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="814bf-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="814bf-114">Il `expression` viene ignorato per i risultati rimanenti.</span><span class="sxs-lookup"><span data-stu-id="814bf-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="814bf-115">La clausola `Take While` è diversa dalla clausola `Where` in quanto la clausola `Where` può essere utilizzata per includere tutti gli elementi di una query che soddisfano una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="814bf-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="814bf-116">La clausola `Take While` include gli elementi solo fino alla prima volta che la condizione non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="814bf-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="814bf-117">La clausola `Take While` è particolarmente utile quando si utilizza un risultato di query ordinato.</span><span class="sxs-lookup"><span data-stu-id="814bf-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="814bf-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="814bf-118">Example</span></span>  
 <span data-ttu-id="814bf-119">Nell'esempio di codice seguente viene utilizzata la clausola `Take While` per recuperare i risultati fino a quando non viene trovato il primo cliente senza ordini.</span><span class="sxs-lookup"><span data-stu-id="814bf-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="814bf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="814bf-120">See also</span></span>

- [<span data-ttu-id="814bf-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="814bf-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="814bf-122">Query</span><span class="sxs-lookup"><span data-stu-id="814bf-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="814bf-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="814bf-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="814bf-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="814bf-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="814bf-125">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="814bf-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="814bf-126">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="814bf-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="814bf-127">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="814bf-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
