---
title: Operatore ^= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 571ef26eb188d9044ec8f6c8e6e4b490780f17a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603496"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5b8a3-102">Operatore ^= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b8a3-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="5b8a3-103">Genera il valore di una variabile o proprietà alla potenza di un'espressione e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b8a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b8a3-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5b8a3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5b8a3-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5b8a3-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-106">Required.</span></span> <span data-ttu-id="5b8a3-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="5b8a3-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-108">Required.</span></span> <span data-ttu-id="5b8a3-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b8a3-110">Note</span><span class="sxs-lookup"><span data-stu-id="5b8a3-110">Remarks</span></span>  
 <span data-ttu-id="5b8a3-111">L'elemento sul lato sinistro del `^=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5b8a3-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="5b8a3-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="5b8a3-113">Il `^=` operatore genera prima il valore della variabile o proprietà (sul lato sinistro dell'operatore) alla potenza del valore dell'espressione (sul lato destro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="5b8a3-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="5b8a3-114">L'operatore assegna il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="5b8a3-115">Visual Basic esegue sempre elevamento a potenza nel [tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="5b8a3-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="5b8a3-116">Gli operandi di tipo diverso vengono convertiti in `Double`, e il risultato è sempre `Double`.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="5b8a3-117">Il valore di `expression` può essere frazionario, negativo o entrambi.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5b8a3-118">Overload</span><span class="sxs-lookup"><span data-stu-id="5b8a3-118">Overloading</span></span>  
 <span data-ttu-id="5b8a3-119">Il [^ operatore](../../../visual-basic/language-reference/operators/exponentiation-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5b8a3-120">L'overload di `^` operatore influisce sul comportamento del `^=` operatore.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="5b8a3-121">Se il codice utilizza `^=` in una classe o struttura che esegue l'overload `^`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5b8a3-122">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5b8a3-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b8a3-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b8a3-123">Example</span></span>  
 <span data-ttu-id="5b8a3-124">L'esempio seguente usa il `^=` operatore per generare il valore di una `Integer` variabile alla potenza di una seconda variabile e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="5b8a3-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5b8a3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b8a3-125">See Also</span></span>  
 [<span data-ttu-id="5b8a3-126">Operatore ^</span><span class="sxs-lookup"><span data-stu-id="5b8a3-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [<span data-ttu-id="5b8a3-127">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="5b8a3-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="5b8a3-128">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="5b8a3-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="5b8a3-129">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b8a3-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5b8a3-130">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="5b8a3-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5b8a3-131">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="5b8a3-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
