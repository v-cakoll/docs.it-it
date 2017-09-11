---
title: -= Operatore (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.-=
dev_langs:
- VB
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements, compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
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
ms.openlocfilehash: 694033ec89e32b5fdba4092bd60292af536f58dd
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="--operator-visual-basic"></a><span data-ttu-id="327d5-102">Operatore -= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="327d5-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="327d5-103">Sottrae il valore di un'espressione dal valore di una variabile o proprietà e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="327d5-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="327d5-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="327d5-105">Parti</span><span class="sxs-lookup"><span data-stu-id="327d5-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="327d5-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="327d5-106">Required.</span></span> <span data-ttu-id="327d5-107">Qualsiasi variabile numerica o proprietà.</span><span class="sxs-lookup"><span data-stu-id="327d5-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="327d5-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="327d5-108">Required.</span></span> <span data-ttu-id="327d5-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="327d5-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="327d5-110">Note</span><span class="sxs-lookup"><span data-stu-id="327d5-110">Remarks</span></span>  
 <span data-ttu-id="327d5-111">L'elemento sul lato sinistro del `-=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="327d5-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="327d5-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="327d5-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="327d5-113">Il `-=` operatore sottrae prima il valore dell'espressione (sul lato destro dell'operatore) dal valore della variabile o proprietà (sul lato sinistro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="327d5-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="327d5-114">L'operatore quindi assegna il risultato dell'operazione per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="327d5-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="327d5-115">Overload</span><span class="sxs-lookup"><span data-stu-id="327d5-115">Overloading</span></span>  
 <span data-ttu-id="327d5-116">Il [-operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) può essere *overload*, il che significa che una classe o struttura possibile ridefinire il comportamento quando un operando specifica il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="327d5-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="327d5-117">L'overload di `-` operatore influisce sul comportamento di `-=` operatore.</span><span class="sxs-lookup"><span data-stu-id="327d5-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="327d5-118">Se il codice utilizza `-=` in una classe o struttura che esegue l'overload `-`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="327d5-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="327d5-119">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="327d5-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="327d5-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="327d5-120">Example</span></span>  
 <span data-ttu-id="327d5-121">Nell'esempio seguente viene utilizzata la `-=` operatore per sottrarre uno `Integer` da un'altra variabile e assegnare il risultato alla variabile di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="327d5-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 <span data-ttu-id="327d5-122">[!code-vb[VbVbalrOperators&#11;](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="327d5-122">[!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327d5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="327d5-123">See Also</span></span>  
 <span data-ttu-id="327d5-124">[-Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span><span class="sxs-lookup"><span data-stu-id="327d5-124">[- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span></span>  
<span data-ttu-id="327d5-125"> [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="327d5-125"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="327d5-126"> [Aritmetici (operatori)](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="327d5-126"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="327d5-127"> [Precedenza tra operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="327d5-127"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="327d5-128"> [Elencata degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="327d5-128"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="327d5-129"> [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="327d5-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

