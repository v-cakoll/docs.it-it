---
title: Operatore ^= (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="99339-102">Operatore ^= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99339-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="99339-103">Genera il valore di una variabile o proprietà alla potenza di un'espressione e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="99339-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99339-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99339-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="99339-105">Parti</span><span class="sxs-lookup"><span data-stu-id="99339-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="99339-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="99339-106">Required.</span></span> <span data-ttu-id="99339-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="99339-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="99339-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="99339-108">Required.</span></span> <span data-ttu-id="99339-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="99339-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99339-110">Note</span><span class="sxs-lookup"><span data-stu-id="99339-110">Remarks</span></span>  
 <span data-ttu-id="99339-111">L'elemento sul lato sinistro del `^=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="99339-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="99339-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="99339-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="99339-113">Il `^=` operatore genera prima il valore della variabile o proprietà (sul lato sinistro dell'operatore) alla potenza del valore dell'espressione (sul lato destro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="99339-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="99339-114">L'operatore assegna il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="99339-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="99339-115">Visual Basic esegue sempre elevamento a potenza nel [tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="99339-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="99339-116">Gli operandi di tipo diverso vengono convertiti in `Double`, e il risultato è sempre `Double`.</span><span class="sxs-lookup"><span data-stu-id="99339-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="99339-117">Il valore di `expression` può essere frazionario, negativo o entrambi.</span><span class="sxs-lookup"><span data-stu-id="99339-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="99339-118">Overload</span><span class="sxs-lookup"><span data-stu-id="99339-118">Overloading</span></span>  
 <span data-ttu-id="99339-119">Il [^ operatore](../../../visual-basic/language-reference/operators/exponentiation-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="99339-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="99339-120">L'overload di `^` operatore influisce sul comportamento del `^=` operatore.</span><span class="sxs-lookup"><span data-stu-id="99339-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="99339-121">Se il codice utilizza `^=` in una classe o struttura che esegue l'overload `^`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="99339-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="99339-122">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="99339-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99339-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="99339-123">Example</span></span>  
 <span data-ttu-id="99339-124">L'esempio seguente usa il `^=` operatore per generare il valore di una `Integer` variabile alla potenza di una seconda variabile e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="99339-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="99339-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99339-125">See Also</span></span>  
 [<span data-ttu-id="99339-126">Operatore ^</span><span class="sxs-lookup"><span data-stu-id="99339-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [<span data-ttu-id="99339-127">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="99339-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="99339-128">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="99339-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="99339-129">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99339-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="99339-130">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="99339-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="99339-131">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="99339-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
