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
ms.openlocfilehash: ad74e3ebc947af4f36022be838b69df6ce24997a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840289"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c4ccf-102">Operatore = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4ccf-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="c4ccf-103">Assegna un valore a una variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4ccf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4ccf-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="c4ccf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c4ccf-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="c4ccf-106">Qualsiasi variabile scrivibile o qualsiasi proprietà.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="c4ccf-107">Qualsiasi valore letterale, costante o espressione.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4ccf-108">Note</span><span class="sxs-lookup"><span data-stu-id="c4ccf-108">Remarks</span></span>  
 <span data-ttu-id="c4ccf-109">L'elemento a sinistra del segno di uguale (`=`) può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="c4ccf-110">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="c4ccf-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="c4ccf-111">Il `=` operatore assegna il valore alla sua destra per la variabile o una proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4ccf-112">Il `=` operatore viene usato anche come un operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="c4ccf-113">Per informazioni dettagliate, vedere [gli operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c4ccf-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c4ccf-114">Overload</span><span class="sxs-lookup"><span data-stu-id="c4ccf-114">Overloading</span></span>  
 <span data-ttu-id="c4ccf-115">Il `=` operatore può essere sottoposto a overload solo come un operatore di confronto relazionale e non come un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="c4ccf-116">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c4ccf-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4ccf-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4ccf-117">Example</span></span>  
 <span data-ttu-id="c4ccf-118">Nell'esempio seguente viene illustrato l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="c4ccf-119">Il valore a destra viene assegnato alla variabile a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c4ccf-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c4ccf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4ccf-120">See also</span></span>

- [<span data-ttu-id="c4ccf-121">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="c4ccf-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="c4ccf-122">Operatore \*=</span><span class="sxs-lookup"><span data-stu-id="c4ccf-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="c4ccf-123">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="c4ccf-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="c4ccf-124">-= Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4ccf-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="c4ccf-125">/ = (Operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4ccf-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="c4ccf-126">\\= Operatore</span><span class="sxs-lookup"><span data-stu-id="c4ccf-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="c4ccf-127">Operatore ^=</span><span class="sxs-lookup"><span data-stu-id="c4ccf-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="c4ccf-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="c4ccf-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="c4ccf-129">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="c4ccf-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="c4ccf-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="c4ccf-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="c4ccf-131">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="c4ccf-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
