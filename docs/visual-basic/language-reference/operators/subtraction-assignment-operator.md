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
ms.openlocfilehash: be1ff4f10f6b30d8448d2441ee3ad2c1e2f80e2d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815901"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="fe631-102">Operatore -= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe631-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="fe631-103">Sottrae il valore di un'espressione rispetto a quello di una proprietà o variabile e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="fe631-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe631-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe631-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="fe631-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fe631-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="fe631-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe631-106">Required.</span></span> <span data-ttu-id="fe631-107">Qualsiasi variabile numerica o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="fe631-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="fe631-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe631-108">Required.</span></span> <span data-ttu-id="fe631-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="fe631-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe631-110">Note</span><span class="sxs-lookup"><span data-stu-id="fe631-110">Remarks</span></span>  
 <span data-ttu-id="fe631-111">L'elemento sul lato sinistro del `-=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="fe631-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="fe631-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="fe631-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="fe631-113">Il `-=` operatore sottrae prima il valore dell'espressione (sul lato destro dell'operatore) dal valore della variabile o proprietà (sul lato sinistro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="fe631-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="fe631-114">L'operatore assegna il risultato dell'operazione per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="fe631-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fe631-115">Overload</span><span class="sxs-lookup"><span data-stu-id="fe631-115">Overloading</span></span>  
 <span data-ttu-id="fe631-116">Il [-operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="fe631-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fe631-117">L'overload di `-` operatore influisce sul comportamento del `-=` operatore.</span><span class="sxs-lookup"><span data-stu-id="fe631-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="fe631-118">Se il codice usi `-=` in una classe o struttura che esegue l'overload `-`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="fe631-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fe631-119">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fe631-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe631-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe631-120">Example</span></span>  
 <span data-ttu-id="fe631-121">L'esempio seguente usa il `-=` operatore per sottrarre uno `Integer` da un'altra variabile e assegna il risultato alla variabile di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="fe631-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="fe631-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe631-122">See also</span></span>

- [<span data-ttu-id="fe631-123">-Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe631-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="fe631-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="fe631-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="fe631-125">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="fe631-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="fe631-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe631-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fe631-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="fe631-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fe631-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="fe631-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
