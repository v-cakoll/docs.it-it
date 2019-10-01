---
title: '\=Operatore (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: d7b4a6946cc38984272a6b63e14e8c1db2825a5e
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700671"
---
# <a name="-operator"></a><span data-ttu-id="ab958-102">Operatore \\ =</span><span class="sxs-lookup"><span data-stu-id="ab958-102">\\= Operator</span></span>
<span data-ttu-id="ab958-103">Divide il valore di una variabile o di una proprietà in base al valore di un'espressione e assegna il risultato Integer alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="ab958-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab958-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab958-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ab958-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ab958-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ab958-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ab958-106">Required.</span></span> <span data-ttu-id="ab958-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="ab958-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="ab958-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ab958-108">Required.</span></span> <span data-ttu-id="ab958-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ab958-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab958-110">Note</span><span class="sxs-lookup"><span data-stu-id="ab958-110">Remarks</span></span>  
 <span data-ttu-id="ab958-111">L'elemento sul lato sinistro dell'operatore `\=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="ab958-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ab958-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ab958-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ab958-113">L'operatore `\=` divide il valore di una variabile o di una proprietà a sinistra del valore a destra e assegna il risultato Integer alla variabile o alla proprietà a sinistra</span><span class="sxs-lookup"><span data-stu-id="ab958-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="ab958-114">Per ulteriori informazioni sulla divisione di interi, vedere [\ operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ab958-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ab958-115">Overload</span><span class="sxs-lookup"><span data-stu-id="ab958-115">Overloading</span></span>  
 <span data-ttu-id="ab958-116">L'operatore `\` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="ab958-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ab958-117">L'overload dell'operatore `\` influiscono sul comportamento dell'operatore `\=`.</span><span class="sxs-lookup"><span data-stu-id="ab958-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="ab958-118">Se il codice USA `\=` su una classe o una struttura che esegue l'overload `\`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="ab958-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ab958-119">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ab958-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab958-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab958-120">Example</span></span>  
 <span data-ttu-id="ab958-121">Nell'esempio seguente viene usato l'operatore `\=` per dividere una variabile `Integer` per secondo e assegnare il risultato Integer alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="ab958-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="ab958-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab958-122">See also</span></span>

- [<span data-ttu-id="ab958-123">Operatore \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab958-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="ab958-124">Operatore/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab958-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="ab958-125">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="ab958-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="ab958-126">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="ab958-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="ab958-127">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab958-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ab958-128">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="ab958-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ab958-129">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="ab958-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
