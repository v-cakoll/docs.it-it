---
title: Clausola Skip While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 7f37a6fa1c9ba7fdf7978ac6853e4c2985bf72e7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004705"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="9619a-102">Clausola Skip While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9619a-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="9619a-103">Ignora gli elementi in una raccolta finché una condizione specificata è `true` e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="9619a-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9619a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9619a-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9619a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9619a-105">Parts</span></span>  
  
|<span data-ttu-id="9619a-106">Nome</span><span class="sxs-lookup"><span data-stu-id="9619a-106">Term</span></span>|<span data-ttu-id="9619a-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="9619a-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="9619a-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9619a-108">Required.</span></span> <span data-ttu-id="9619a-109">Espressione che rappresenta una condizione per cui verificare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="9619a-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="9619a-110">L'espressione deve restituire un valore `Boolean` o un equivalente funzionale, ad esempio un `Integer` da valutare come `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="9619a-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9619a-111">Note</span><span class="sxs-lookup"><span data-stu-id="9619a-111">Remarks</span></span>  
 <span data-ttu-id="9619a-112">La clausola `Skip While` ignora gli elementi dall'inizio di un risultato della query fino a quando il `expression` fornito restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="9619a-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="9619a-113">Dopo che `expression` restituisce `false`, la query restituisce tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="9619a-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="9619a-114">Il `expression` viene ignorato per i risultati rimanenti.</span><span class="sxs-lookup"><span data-stu-id="9619a-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="9619a-115">La clausola `Skip While` è diversa dalla clausola `Where` in quanto la clausola `Where` può essere usata per escludere tutti gli elementi da una query che non soddisfano una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="9619a-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="9619a-116">La clausola `Skip While` esclude gli elementi solo fino alla prima volta che la condizione non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="9619a-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="9619a-117">La clausola `Skip While` è particolarmente utile quando si utilizza un risultato di query ordinato.</span><span class="sxs-lookup"><span data-stu-id="9619a-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="9619a-118">È possibile ignorare un numero specifico di risultati dall'inizio di un risultato della query utilizzando la clausola `Skip`.</span><span class="sxs-lookup"><span data-stu-id="9619a-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9619a-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="9619a-119">Example</span></span>  
 <span data-ttu-id="9619a-120">Nell'esempio di codice seguente viene utilizzata la clausola `Skip While` per ignorare i risultati fino a quando non viene trovato il primo cliente del Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="9619a-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9619a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9619a-121">See also</span></span>

- [<span data-ttu-id="9619a-122">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9619a-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9619a-123">Query</span><span class="sxs-lookup"><span data-stu-id="9619a-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="9619a-124">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="9619a-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="9619a-125">Clausola From</span><span class="sxs-lookup"><span data-stu-id="9619a-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="9619a-126">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="9619a-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="9619a-127">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="9619a-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="9619a-128">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="9619a-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
