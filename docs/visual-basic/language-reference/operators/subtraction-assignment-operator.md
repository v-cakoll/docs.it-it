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
ms.openlocfilehash: f857c8bf2f89120e047c49674ce9e8a3bff22f7d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701310"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="45d65-102">Operatore -= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45d65-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="45d65-103">Sottrae il valore di un'espressione dal valore di una variabile o di una proprietà e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="45d65-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45d65-104">Syntax</span></span>  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="45d65-105">Parti</span><span class="sxs-lookup"><span data-stu-id="45d65-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="45d65-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="45d65-106">Required.</span></span> <span data-ttu-id="45d65-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="45d65-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="45d65-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="45d65-108">Required.</span></span> <span data-ttu-id="45d65-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="45d65-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45d65-110">Note</span><span class="sxs-lookup"><span data-stu-id="45d65-110">Remarks</span></span>  
 <span data-ttu-id="45d65-111">L'elemento sul lato sinistro dell'operatore `-=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="45d65-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="45d65-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="45d65-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="45d65-113">L'operatore `-=` sottrae prima di tutto il valore dell'espressione (sul lato destro dell'operatore) dal valore della variabile o della proprietà (sul lato sinistro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="45d65-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="45d65-114">L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="45d65-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="45d65-115">Overload</span><span class="sxs-lookup"><span data-stu-id="45d65-115">Overloading</span></span>  
 <span data-ttu-id="45d65-116">L' [operatore-(Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="45d65-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="45d65-117">L'overload dell'operatore `-` influiscono sul comportamento dell'operatore `-=`.</span><span class="sxs-lookup"><span data-stu-id="45d65-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="45d65-118">Se il codice USA `-=` su una classe o una struttura che esegue l'overload `-`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="45d65-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="45d65-119">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="45d65-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45d65-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="45d65-120">Example</span></span>  
 <span data-ttu-id="45d65-121">Nell'esempio seguente viene usato l'operatore `-=` per sottrarre una variabile `Integer` da un'altra e assegnare il risultato alla seconda variabile.</span><span class="sxs-lookup"><span data-stu-id="45d65-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="45d65-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45d65-122">See also</span></span>

- [<span data-ttu-id="45d65-123">Operatore-(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45d65-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="45d65-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="45d65-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="45d65-125">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="45d65-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="45d65-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45d65-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="45d65-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="45d65-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="45d65-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="45d65-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
