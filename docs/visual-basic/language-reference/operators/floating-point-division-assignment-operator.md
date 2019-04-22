---
title: Operatore /= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: d9d3fa021654d3be1b9d304beb83caa737660264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813990"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b5ffd-102">Operatore /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5ffd-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="b5ffd-103">Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato a virgola mobile e la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5ffd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5ffd-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b5ffd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b5ffd-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="b5ffd-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-106">Required.</span></span> <span data-ttu-id="b5ffd-107">Qualsiasi variabile numerica o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="b5ffd-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-108">Required.</span></span> <span data-ttu-id="b5ffd-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5ffd-110">Note</span><span class="sxs-lookup"><span data-stu-id="b5ffd-110">Remarks</span></span>  
 <span data-ttu-id="b5ffd-111">L'elemento sul lato sinistro del `/=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b5ffd-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="b5ffd-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b5ffd-113">Il `/=` operatore divide innanzitutto il valore della variabile o proprietà (sul lato sinistro dell'operatore) per il valore dell'espressione (sul lato destro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="b5ffd-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="b5ffd-114">L'operatore assegna quindi il risultato dell'operazione a virgola mobile e per la variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="b5ffd-115">Questa istruzione assegna un `Double` valore alla variabile o proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="b5ffd-116">Se `Option Strict` viene `On`, `variableorproperty` deve essere un `Double`.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="b5ffd-117">Se `Option Strict` viene `Off`, Visual Basic esegue una conversione implicita e assegna il valore risultante a `variableorproperty`, con un messaggio di errore in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="b5ffd-118">Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5ffd-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b5ffd-119">Overload</span><span class="sxs-lookup"><span data-stu-id="b5ffd-119">Overloading</span></span>  
 <span data-ttu-id="b5ffd-120">Il [/ operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b5ffd-121">L'overload di `/` operatore influisce sul comportamento del `/=` operatore.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="b5ffd-122">Se il codice usi `/=` in una classe o struttura che esegue l'overload `/`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b5ffd-123">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b5ffd-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5ffd-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5ffd-124">Example</span></span>  
 <span data-ttu-id="b5ffd-125">L'esempio seguente usa il `/=` operatore per dividere un `Integer` variabile da un secondo e di assegnare il quoziente per la prima variabile.</span><span class="sxs-lookup"><span data-stu-id="b5ffd-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b5ffd-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5ffd-126">See also</span></span>

- [<span data-ttu-id="b5ffd-127">/ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5ffd-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="b5ffd-128">\\= Operatore</span><span class="sxs-lookup"><span data-stu-id="b5ffd-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="b5ffd-129">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="b5ffd-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="b5ffd-130">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="b5ffd-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="b5ffd-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5ffd-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b5ffd-132">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="b5ffd-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b5ffd-133">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="b5ffd-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
