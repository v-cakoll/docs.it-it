---
title: '\= Operatore (Visual Basic)'
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
ms.openlocfilehash: bcfc59efda0627f83713fe9ada24cedc20d823e3
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2018
ms.locfileid: "39198208"
---
# <a name="-operator"></a><span data-ttu-id="a4773-102">\\= Operatore</span><span class="sxs-lookup"><span data-stu-id="a4773-102">\\= Operator</span></span>
<span data-ttu-id="a4773-103">Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato di integer alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="a4773-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4773-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4773-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a4773-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a4773-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a4773-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a4773-106">Required.</span></span> <span data-ttu-id="a4773-107">Qualsiasi variabile numerica o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="a4773-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a4773-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a4773-108">Required.</span></span> <span data-ttu-id="a4773-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="a4773-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4773-110">Note</span><span class="sxs-lookup"><span data-stu-id="a4773-110">Remarks</span></span>  
 <span data-ttu-id="a4773-111">L'elemento sul lato sinistro del `\=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="a4773-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a4773-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a4773-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a4773-113">Il `\=` operatore divide il valore di una variabile o proprietà alla sua sinistra per il valore alla sua destra e assegna il risultato di integer per la variabile o una proprietà alla sua sinistra</span><span class="sxs-lookup"><span data-stu-id="a4773-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="a4773-114">Per altre informazioni sulla divisione di interi, vedere [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a4773-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a4773-115">Overload</span><span class="sxs-lookup"><span data-stu-id="a4773-115">Overloading</span></span>  
 <span data-ttu-id="a4773-116">Il `\` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="a4773-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a4773-117">L'overload di `\` operatore influisce sul comportamento del `\=` operatore.</span><span class="sxs-lookup"><span data-stu-id="a4773-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="a4773-118">Se il codice usi `\=` in una classe o struttura che esegue l'overload `\`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="a4773-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a4773-119">Per altre informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a4773-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4773-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4773-120">Example</span></span>  
 <span data-ttu-id="a4773-121">L'esempio seguente usa il `\=` operatore per dividere un `Integer` variabile da un secondo e di assegnare l'intero risultato per la prima variabile.</span><span class="sxs-lookup"><span data-stu-id="a4773-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a4773-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4773-122">See Also</span></span>  
 [<span data-ttu-id="a4773-123">\ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4773-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="a4773-124">/ = (Operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4773-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="a4773-125">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="a4773-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="a4773-126">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="a4773-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="a4773-127">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a4773-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a4773-128">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="a4773-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a4773-129">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="a4773-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
