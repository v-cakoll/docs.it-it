---
title: '\=(Operatore)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ba74f7a433687b306e8b4273f3a2a6d60583396
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator"></a><span data-ttu-id="4033d-102">\\= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="4033d-102">\\= Operator</span></span>
<span data-ttu-id="4033d-103">Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato di tipo integer per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="4033d-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4033d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4033d-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="4033d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4033d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4033d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4033d-106">Required.</span></span> <span data-ttu-id="4033d-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="4033d-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="4033d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4033d-108">Required.</span></span> <span data-ttu-id="4033d-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4033d-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4033d-110">Note</span><span class="sxs-lookup"><span data-stu-id="4033d-110">Remarks</span></span>  
 <span data-ttu-id="4033d-111">L'elemento sul lato sinistro del `\=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="4033d-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4033d-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4033d-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="4033d-113">Il `\=` operatore divide il valore di una variabile o proprietà alla sua sinistra per il valore alla sua destra e assegna il risultato di tipo integer per la variabile o proprietà alla sua sinistra</span><span class="sxs-lookup"><span data-stu-id="4033d-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="4033d-114">Per ulteriori informazioni sulla divisione di integer, vedere [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4033d-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4033d-115">Overload</span><span class="sxs-lookup"><span data-stu-id="4033d-115">Overloading</span></span>  
 <span data-ttu-id="4033d-116">Il `\` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="4033d-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4033d-117">L'overload di `\` operatore influisce sul comportamento del `\=` operatore.</span><span class="sxs-lookup"><span data-stu-id="4033d-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="4033d-118">Se il codice utilizza `\=` in una classe o struttura che esegue l'overload `\`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="4033d-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4033d-119">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4033d-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4033d-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="4033d-120">Example</span></span>  
 <span data-ttu-id="4033d-121">L'esempio seguente usa il `\=` operatore per dividere una `Integer` variabile da un secondo e assegnare l'intero risultato per la prima variabile.</span><span class="sxs-lookup"><span data-stu-id="4033d-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4033d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4033d-122">See Also</span></span>  
 [<span data-ttu-id="4033d-123">\ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4033d-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="4033d-124">/ = (Operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4033d-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="4033d-125">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="4033d-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="4033d-126">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="4033d-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="4033d-127">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4033d-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="4033d-128">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="4033d-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="4033d-129">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="4033d-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
