---
title: Operatore *= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 47d3239af6ff24501e6babc23c0db4103c477796
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701060"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3a7ac-102">Operatore \*= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a7ac-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="3a7ac-103">Moltiplica il valore di una variabile o di una proprietà in base al valore di un'espressione e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a7ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a7ac-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3a7ac-105">Parti</span><span class="sxs-lookup"><span data-stu-id="3a7ac-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3a7ac-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-106">Required.</span></span> <span data-ttu-id="3a7ac-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3a7ac-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-108">Required.</span></span> <span data-ttu-id="3a7ac-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a7ac-110">Note</span><span class="sxs-lookup"><span data-stu-id="3a7ac-110">Remarks</span></span>  
 <span data-ttu-id="3a7ac-111">L'elemento sul lato sinistro dell'operatore `*=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3a7ac-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3a7ac-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3a7ac-113">L'operatore `*=` moltiplica prima di tutto il valore dell'espressione (sul lato destro dell'operatore) per il valore della variabile o della proprietà (sul lato sinistro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="3a7ac-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="3a7ac-114">L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3a7ac-115">Overload</span><span class="sxs-lookup"><span data-stu-id="3a7ac-115">Overloading</span></span>  
 <span data-ttu-id="3a7ac-116">L' [operatore \*](../../../visual-basic/language-reference/operators/multiplication-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3a7ac-117">L'overload dell'operatore `*` influiscono sul comportamento dell'operatore `*=`.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="3a7ac-118">Se il codice USA `*=` su una classe o una struttura che esegue l'overload `*`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3a7ac-119">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3a7ac-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a7ac-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a7ac-120">Example</span></span>  
 <span data-ttu-id="3a7ac-121">Nell'esempio seguente viene usato l'operatore `*=` per moltiplicare una variabile `Integer` per secondo e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="3a7ac-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="3a7ac-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a7ac-122">See also</span></span>

- [<span data-ttu-id="3a7ac-123">Operatore \*</span><span class="sxs-lookup"><span data-stu-id="3a7ac-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="3a7ac-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="3a7ac-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="3a7ac-125">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="3a7ac-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="3a7ac-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a7ac-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="3a7ac-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="3a7ac-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="3a7ac-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="3a7ac-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
