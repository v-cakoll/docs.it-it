---
title: = Operatore (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 46dc9e6018cf2ae71f1fc6dc2b8f19c2f0aadb62
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="04479-102">Operatore = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04479-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="04479-103">Assegna un valore a una variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="04479-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04479-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04479-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="04479-105">Parti</span><span class="sxs-lookup"><span data-stu-id="04479-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="04479-106">Qualsiasi variabile modificabile o qualsiasi proprietà.</span><span class="sxs-lookup"><span data-stu-id="04479-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="04479-107">Qualsiasi valore letterale, costante o espressione.</span><span class="sxs-lookup"><span data-stu-id="04479-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04479-108">Note</span><span class="sxs-lookup"><span data-stu-id="04479-108">Remarks</span></span>  
 <span data-ttu-id="04479-109">L'elemento a sinistra del segno di uguale (`=`) può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="04479-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="04479-110">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="04479-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="04479-111">Il `=` operatore assegna il valore alla sua destra alla variabile o proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="04479-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04479-112">Il `=` operatore viene utilizzato anche come un operatore di confronto.</span><span class="sxs-lookup"><span data-stu-id="04479-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="04479-113">Per informazioni dettagliate, vedere [operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="04479-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="04479-114">Overload</span><span class="sxs-lookup"><span data-stu-id="04479-114">Overloading</span></span>  
 <span data-ttu-id="04479-115">Il `=` operatore può essere sottoposto a overload solo come operatore di confronto relazionale, non come un operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="04479-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="04479-116">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="04479-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04479-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="04479-117">Example</span></span>  
 <span data-ttu-id="04479-118">Nell'esempio seguente viene illustrato l'operatore di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="04479-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="04479-119">Il valore a destra viene assegnato alla variabile a sinistra.</span><span class="sxs-lookup"><span data-stu-id="04479-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 <span data-ttu-id="04479-120">[!code-vb[9 VbVbalrOperators](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="04479-120">[!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04479-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04479-121">See Also</span></span>  
 <span data-ttu-id="04479-122">[/ = (Operatore)](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="04479-122">[&= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span></span>  
<span data-ttu-id="04479-123"> [* = (Operatore)](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="04479-123"> [*= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span></span>  
<span data-ttu-id="04479-124"> [+ = Operatore](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="04479-124"> [+= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span></span>  
<span data-ttu-id="04479-125"> [-= Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="04479-125"> [-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span></span>  
<span data-ttu-id="04479-126"> [Operatore / = (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="04479-126"> [/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="04479-127"> [\\= Operatore](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="04479-127"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="04479-128"> [^ = (Operatore)](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="04479-128"> [^= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span></span>  
<span data-ttu-id="04479-129"> [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="04479-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="04479-130"> [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="04479-130"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="04479-131"> [Sola lettura](../../../visual-basic/language-reference/modifiers/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="04479-131"> [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) </span></span>  
<span data-ttu-id="04479-132"> [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span><span class="sxs-lookup"><span data-stu-id="04479-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span></span>

