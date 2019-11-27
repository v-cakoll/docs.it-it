---
title: Operatore ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5e8fc2b64b9e7c33483612071d338a0ee22768
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331302"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="4d515-102">Operatore ^= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d515-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="4d515-103">Genera il valore di una variabile o di una proprietà alla potenza di un'espressione e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="4d515-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d515-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d515-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="4d515-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4d515-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4d515-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4d515-106">Required.</span></span> <span data-ttu-id="4d515-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="4d515-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="4d515-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4d515-108">Required.</span></span> <span data-ttu-id="4d515-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4d515-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d515-110">Note</span><span class="sxs-lookup"><span data-stu-id="4d515-110">Remarks</span></span>  
 <span data-ttu-id="4d515-111">L'elemento sul lato sinistro dell'operatore `^=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="4d515-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4d515-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4d515-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="4d515-113">L'operatore `^=` prima di tutto genera il valore della variabile o della proprietà (sul lato sinistro dell'operatore) alla potenza del valore dell'espressione (sul lato destro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="4d515-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="4d515-114">L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="4d515-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="4d515-115">Visual Basic esegue sempre l'elevamento a potenza nel [tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="4d515-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="4d515-116">Gli operandi di qualsiasi tipo diverso vengono convertiti in `Double`e il risultato è sempre `Double`.</span><span class="sxs-lookup"><span data-stu-id="4d515-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="4d515-117">Il valore di `expression` può essere frazionario, negativo o entrambi.</span><span class="sxs-lookup"><span data-stu-id="4d515-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4d515-118">Overload</span><span class="sxs-lookup"><span data-stu-id="4d515-118">Overloading</span></span>  
 <span data-ttu-id="4d515-119">L' [operatore ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="4d515-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4d515-120">L'overload dell'operatore `^` influiscono sul comportamento dell'operatore `^=`.</span><span class="sxs-lookup"><span data-stu-id="4d515-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="4d515-121">Se il codice USA `^=` su una classe o una struttura che esegue l'overload di `^`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="4d515-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4d515-122">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4d515-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d515-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d515-123">Example</span></span>  
 <span data-ttu-id="4d515-124">Nell'esempio seguente viene usato l'operatore `^=` per aumentare il valore di una variabile `Integer` alla potenza di una seconda variabile e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="4d515-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="4d515-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d515-125">See also</span></span>

- [<span data-ttu-id="4d515-126">Operatore ^</span><span class="sxs-lookup"><span data-stu-id="4d515-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="4d515-127">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="4d515-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="4d515-128">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="4d515-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="4d515-129">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d515-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4d515-130">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="4d515-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4d515-131">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="4d515-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
