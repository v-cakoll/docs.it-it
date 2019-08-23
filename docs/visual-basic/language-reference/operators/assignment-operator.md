---
title: Operatore = (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: d260dffb7175e9dddcbf9acb75415f5f973727e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962012"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d646b-102">Operatore = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d646b-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="d646b-103">Assegna un valore a una variabile o a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d646b-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d646b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d646b-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="d646b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d646b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="d646b-106">Qualsiasi variabile scrivibile o qualsiasi proprietà.</span><span class="sxs-lookup"><span data-stu-id="d646b-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="d646b-107">Qualsiasi valore letterale, costante o espressione.</span><span class="sxs-lookup"><span data-stu-id="d646b-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d646b-108">Note</span><span class="sxs-lookup"><span data-stu-id="d646b-108">Remarks</span></span>  
 <span data-ttu-id="d646b-109">L'elemento sul lato sinistro del segno di uguale (`=`) può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="d646b-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d646b-110">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="d646b-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="d646b-111">L' `=` operatore assegna il valore a destra alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d646b-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d646b-112">L' `=` operatore viene utilizzato anche come operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="d646b-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="d646b-113">Per informazioni dettagliate, vedere [operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d646b-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d646b-114">Overload</span><span class="sxs-lookup"><span data-stu-id="d646b-114">Overloading</span></span>  
 <span data-ttu-id="d646b-115">È `=` possibile eseguire l'overload dell'operatore solo come operatore di confronto relazionale, non come operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d646b-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="d646b-116">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d646b-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d646b-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="d646b-117">Example</span></span>  
 <span data-ttu-id="d646b-118">Nell'esempio seguente viene illustrato l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d646b-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="d646b-119">Il valore a destra viene assegnato alla variabile a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d646b-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="d646b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d646b-120">See also</span></span>

- [<span data-ttu-id="d646b-121">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="d646b-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="d646b-122">Operatore \*=</span><span class="sxs-lookup"><span data-stu-id="d646b-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="d646b-123">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="d646b-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="d646b-124">Operatore-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d646b-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="d646b-125">Operatore/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d646b-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="d646b-126">\\= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="d646b-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="d646b-127">Operatore ^=</span><span class="sxs-lookup"><span data-stu-id="d646b-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="d646b-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="d646b-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="d646b-129">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="d646b-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="d646b-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="d646b-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="d646b-131">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="d646b-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
