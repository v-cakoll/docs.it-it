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
ms.openlocfilehash: 4b6133efdbd9c46ab85201ad454671e5538b6a81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359580"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="a7372-102">Clausola Take While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7372-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="a7372-103">Include gli elementi in una raccolta finché una condizione specificata è `true` e quindi ignora gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a7372-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7372-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7372-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a7372-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a7372-105">Parts</span></span>  
  
|<span data-ttu-id="a7372-106">Termine</span><span class="sxs-lookup"><span data-stu-id="a7372-106">Term</span></span>|<span data-ttu-id="a7372-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7372-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="a7372-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a7372-108">Required.</span></span> <span data-ttu-id="a7372-109">Espressione che rappresenta una condizione per cui verificare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="a7372-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="a7372-110">L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un oggetto `Integer` da valutare come `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a7372-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7372-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="a7372-111">Remarks</span></span>  
 <span data-ttu-id="a7372-112">La `Take While` clausola include gli elementi dall'inizio di un risultato della query fino a quando l'oggetto specificato `expression` restituisce `false` .</span><span class="sxs-lookup"><span data-stu-id="a7372-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="a7372-113">Una volta `expression` restituiti `false` , la query ignorerà tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a7372-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="a7372-114">`expression`Viene ignorato per i risultati rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a7372-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="a7372-115">La clausola è `Take While` diversa dalla `Where` clausola in quanto la `Where` clausola può essere utilizzata per includere tutti gli elementi di una query che soddisfano una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="a7372-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="a7372-116">La `Take While` clausola include gli elementi solo fino alla prima volta che la condizione non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="a7372-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="a7372-117">La `Take While` clausola è particolarmente utile quando si lavora con un risultato di query ordinato.</span><span class="sxs-lookup"><span data-stu-id="a7372-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7372-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7372-118">Example</span></span>  
 <span data-ttu-id="a7372-119">Nell'esempio di codice seguente viene utilizzata la `Take While` clausola per recuperare i risultati fino a quando non viene trovato il primo cliente senza ordini.</span><span class="sxs-lookup"><span data-stu-id="a7372-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a7372-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7372-120">See also</span></span>

- [<span data-ttu-id="a7372-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7372-121">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a7372-122">Query</span><span class="sxs-lookup"><span data-stu-id="a7372-122">Queries</span></span>](index.md)
- [<span data-ttu-id="a7372-123">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="a7372-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="a7372-124">Clausola from</span><span class="sxs-lookup"><span data-stu-id="a7372-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="a7372-125">Clausola Take</span><span class="sxs-lookup"><span data-stu-id="a7372-125">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="a7372-126">Clausola Skip While</span><span class="sxs-lookup"><span data-stu-id="a7372-126">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="a7372-127">Clausola WHERE</span><span class="sxs-lookup"><span data-stu-id="a7372-127">Where Clause</span></span>](where-clause.md)
