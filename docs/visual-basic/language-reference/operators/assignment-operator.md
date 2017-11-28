---
title: Operatore = (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 230005640b2b494e5413b14ba13a7cb82ee9f22b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="24ae6-102">Operatore = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24ae6-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="24ae6-103">Assegna un valore a una variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="24ae6-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ae6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24ae6-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="24ae6-105">Parti</span><span class="sxs-lookup"><span data-stu-id="24ae6-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="24ae6-106">Qualsiasi variabile modificabile o qualsiasi proprietà.</span><span class="sxs-lookup"><span data-stu-id="24ae6-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="24ae6-107">Qualsiasi valore letterale costante o espressione.</span><span class="sxs-lookup"><span data-stu-id="24ae6-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24ae6-108">Note</span><span class="sxs-lookup"><span data-stu-id="24ae6-108">Remarks</span></span>  
 <span data-ttu-id="24ae6-109">L'elemento a sinistra del segno di uguale (`=`) può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="24ae6-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="24ae6-110">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="24ae6-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="24ae6-111">Il `=` operatore assegna il valore alla sua destra alla variabile o proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="24ae6-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24ae6-112">Il `=` operatore viene inoltre utilizzato come operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="24ae6-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="24ae6-113">Per informazioni dettagliate, vedere [gli operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="24ae6-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="24ae6-114">Overload</span><span class="sxs-lookup"><span data-stu-id="24ae6-114">Overloading</span></span>  
 <span data-ttu-id="24ae6-115">Il `=` operatore può essere sottoposto a overload solo come operatore di confronto relazionale, non come un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="24ae6-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="24ae6-116">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="24ae6-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24ae6-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="24ae6-117">Example</span></span>  
 <span data-ttu-id="24ae6-118">Nell'esempio seguente viene illustrato l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="24ae6-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="24ae6-119">Il valore a destra viene assegnato alla variabile a sinistra.</span><span class="sxs-lookup"><span data-stu-id="24ae6-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="24ae6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24ae6-120">See Also</span></span>  
 [<span data-ttu-id="24ae6-121">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="24ae6-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="24ae6-122">Operatore *=</span><span class="sxs-lookup"><span data-stu-id="24ae6-122">*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="24ae6-123">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="24ae6-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="24ae6-124">-= Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24ae6-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [<span data-ttu-id="24ae6-125">/ = (Operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24ae6-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="24ae6-126">\\= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="24ae6-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="24ae6-127">Operatore ^=</span><span class="sxs-lookup"><span data-stu-id="24ae6-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="24ae6-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="24ae6-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="24ae6-129">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="24ae6-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="24ae6-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="24ae6-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="24ae6-131">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="24ae6-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
