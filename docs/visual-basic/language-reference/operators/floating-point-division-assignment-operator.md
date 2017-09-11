---
title: Operatore / = (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./=
dev_langs:
- VB
helpviewer_keywords:
- assignment statements, compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
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
ms.openlocfilehash: e877e98104b5c9fd679485b50a88943fac80a696
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3340b-102">Operatore /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3340b-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="3340b-103">Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato a virgola mobile e la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="3340b-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3340b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3340b-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3340b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="3340b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3340b-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3340b-106">Required.</span></span> <span data-ttu-id="3340b-107">Qualsiasi variabile numerica o proprietà.</span><span class="sxs-lookup"><span data-stu-id="3340b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3340b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3340b-108">Required.</span></span> <span data-ttu-id="3340b-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="3340b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3340b-110">Note</span><span class="sxs-lookup"><span data-stu-id="3340b-110">Remarks</span></span>  
 <span data-ttu-id="3340b-111">L'elemento sul lato sinistro del `/=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="3340b-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3340b-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3340b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3340b-113">Il `/=` operatore divide innanzitutto il valore della variabile o proprietà (sul lato sinistro dell'operatore) per il valore dell'espressione (sul lato destro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="3340b-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="3340b-114">L'operatore quindi assegna il risultato dell'operazione a virgola mobile per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="3340b-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="3340b-115">Questa istruzione assegna un `Double` valore alla variabile o proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="3340b-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="3340b-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span><span class="sxs-lookup"><span data-stu-id="3340b-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="3340b-117">Se `Option Strict` è `Off`, Visual Basic esegue una conversione implicita e assegna il valore risultante a `variableorproperty`, con un messaggio di errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3340b-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="3340b-118">Per ulteriori informazioni, vedere [conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3340b-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3340b-119">Overload</span><span class="sxs-lookup"><span data-stu-id="3340b-119">Overloading</span></span>  
 <span data-ttu-id="3340b-120">Il [/ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) può essere *overload*, il che significa che una classe o struttura possibile ridefinire il comportamento quando un operando specifica il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="3340b-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3340b-121">L'overload di `/` operatore influisce sul comportamento di `/=` operatore.</span><span class="sxs-lookup"><span data-stu-id="3340b-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="3340b-122">Se il codice utilizza `/=` in una classe o struttura che esegue l'overload `/`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="3340b-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3340b-123">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3340b-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3340b-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="3340b-124">Example</span></span>  
 <span data-ttu-id="3340b-125">Nell'esempio seguente viene utilizzata la `/=` operatore per dividere una `Integer` variabile da un secondo e di assegnare il quoziente alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="3340b-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 <span data-ttu-id="3340b-126">[!code-vb[VbVbalrOperators n.&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3340b-126">[!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3340b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3340b-127">See Also</span></span>  
 <span data-ttu-id="3340b-128">[/ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="3340b-128">[/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span></span>  
<span data-ttu-id="3340b-129"> [\\= Operatore](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="3340b-129"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="3340b-130"> [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="3340b-130"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="3340b-131"> [Aritmetici (operatori)](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="3340b-131"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="3340b-132"> [Precedenza tra operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="3340b-132"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="3340b-133"> [Elencata degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="3340b-133"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="3340b-134"> [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="3340b-134"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

