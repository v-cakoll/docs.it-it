---
title: Operatore -= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 598fd9db4262d0a33bf0408ebe9455760d5e4506
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603873"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="1755c-102">Operatore -= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1755c-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="1755c-103">Sottrae il valore di un'espressione dal valore di una variabile o proprietà e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="1755c-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1755c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1755c-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="1755c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1755c-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="1755c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1755c-106">Required.</span></span> <span data-ttu-id="1755c-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="1755c-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="1755c-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1755c-108">Required.</span></span> <span data-ttu-id="1755c-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="1755c-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1755c-110">Note</span><span class="sxs-lookup"><span data-stu-id="1755c-110">Remarks</span></span>  
 <span data-ttu-id="1755c-111">L'elemento sul lato sinistro del `-=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="1755c-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="1755c-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1755c-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="1755c-113">Il `-=` operatore sottrae prima il valore dell'espressione (sul lato destro dell'operatore) dal valore della variabile o proprietà (sul lato sinistro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="1755c-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="1755c-114">L'operatore assegna il risultato dell'operazione per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="1755c-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1755c-115">Overload</span><span class="sxs-lookup"><span data-stu-id="1755c-115">Overloading</span></span>  
 <span data-ttu-id="1755c-116">Il [-operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="1755c-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1755c-117">L'overload di `-` operatore influisce sul comportamento del `-=` operatore.</span><span class="sxs-lookup"><span data-stu-id="1755c-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="1755c-118">Se il codice utilizza `-=` in una classe o struttura che esegue l'overload `-`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="1755c-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1755c-119">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1755c-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1755c-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="1755c-120">Example</span></span>  
 <span data-ttu-id="1755c-121">L'esempio seguente usa il `-=` operatore per sottrarre uno `Integer` variabile da un'altra e assegnare il risultato alla variabile di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="1755c-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1755c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1755c-122">See Also</span></span>  
 [<span data-ttu-id="1755c-123">-(Operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1755c-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)  
 [<span data-ttu-id="1755c-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="1755c-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="1755c-125">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="1755c-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="1755c-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1755c-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="1755c-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="1755c-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="1755c-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="1755c-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
