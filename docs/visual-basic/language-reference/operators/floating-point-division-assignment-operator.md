---
title: Operatore /= (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94448856072a949582e64577287134c4b975bfec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3bbdf-102">Operatore /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bbdf-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="3bbdf-103">Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato a virgola mobile per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bbdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3bbdf-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3bbdf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="3bbdf-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3bbdf-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-106">Required.</span></span> <span data-ttu-id="3bbdf-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3bbdf-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-108">Required.</span></span> <span data-ttu-id="3bbdf-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bbdf-110">Note</span><span class="sxs-lookup"><span data-stu-id="3bbdf-110">Remarks</span></span>  
 <span data-ttu-id="3bbdf-111">L'elemento sul lato sinistro del `/=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3bbdf-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3bbdf-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3bbdf-113">Il `/=` operatore divide innanzitutto il valore della variabile o proprietà (sul lato sinistro dell'operatore di) per il valore dell'espressione (sul lato destro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="3bbdf-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="3bbdf-114">L'operatore assegna quindi il risultato dell'operazione a virgola mobile per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="3bbdf-115">Questa istruzione assegna un `Double` valore alla variabile o una proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="3bbdf-116">Se `Option Strict` è `On`, `variableorproperty` deve essere un `Double`.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="3bbdf-117">Se `Option Strict` è `Off`, Visual Basic esegue una conversione implicita e assegna il valore risultante `variableorproperty`, con un messaggio di errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="3bbdf-118">Per ulteriori informazioni, vedere [conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3bbdf-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3bbdf-119">Overload</span><span class="sxs-lookup"><span data-stu-id="3bbdf-119">Overloading</span></span>  
 <span data-ttu-id="3bbdf-120">Il [/ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3bbdf-121">L'overload di `/` operatore influisce sul comportamento del `/=` operatore.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="3bbdf-122">Se il codice utilizza `/=` in una classe o struttura che esegue l'overload `/`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3bbdf-123">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3bbdf-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bbdf-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="3bbdf-124">Example</span></span>  
 <span data-ttu-id="3bbdf-125">L'esempio seguente usa il `/=` operatore per dividere una `Integer` variabile da un secondo e assegnare il quoziente alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="3bbdf-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3bbdf-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bbdf-126">See Also</span></span>  
 [<span data-ttu-id="3bbdf-127">/ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bbdf-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="3bbdf-128">\\= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="3bbdf-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="3bbdf-129">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="3bbdf-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="3bbdf-130">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="3bbdf-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="3bbdf-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3bbdf-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="3bbdf-132">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="3bbdf-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="3bbdf-133">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="3bbdf-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
