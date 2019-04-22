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
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842538"
---
# <a name="-operator"></a><span data-ttu-id="2314f-102">\\= Operatore</span><span class="sxs-lookup"><span data-stu-id="2314f-102">\\= Operator</span></span>
<span data-ttu-id="2314f-103">Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato di integer alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="2314f-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2314f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2314f-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2314f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2314f-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2314f-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2314f-106">Required.</span></span> <span data-ttu-id="2314f-107">Qualsiasi variabile numerica o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="2314f-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="2314f-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2314f-108">Required.</span></span> <span data-ttu-id="2314f-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="2314f-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2314f-110">Note</span><span class="sxs-lookup"><span data-stu-id="2314f-110">Remarks</span></span>  
 <span data-ttu-id="2314f-111">L'elemento sul lato sinistro del `\=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="2314f-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2314f-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="2314f-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2314f-113">Il `\=` operatore divide il valore di una variabile o proprietà alla sua sinistra per il valore alla sua destra e assegna il risultato di integer per la variabile o una proprietà alla sua sinistra</span><span class="sxs-lookup"><span data-stu-id="2314f-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="2314f-114">Per altre informazioni sulla divisione di interi, vedere [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2314f-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2314f-115">Overload</span><span class="sxs-lookup"><span data-stu-id="2314f-115">Overloading</span></span>  
 <span data-ttu-id="2314f-116">Il `\` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="2314f-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2314f-117">L'overload di `\` operatore influisce sul comportamento del `\=` operatore.</span><span class="sxs-lookup"><span data-stu-id="2314f-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="2314f-118">Se il codice usi `\=` in una classe o struttura che esegue l'overload `\`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="2314f-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2314f-119">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2314f-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2314f-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="2314f-120">Example</span></span>  
 <span data-ttu-id="2314f-121">L'esempio seguente usa il `\=` operatore per dividere un `Integer` variabile da un secondo e di assegnare l'intero risultato per la prima variabile.</span><span class="sxs-lookup"><span data-stu-id="2314f-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="2314f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2314f-122">See also</span></span>

- [<span data-ttu-id="2314f-123">\ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2314f-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="2314f-124">/ = (Operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2314f-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="2314f-125">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="2314f-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="2314f-126">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="2314f-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="2314f-127">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2314f-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2314f-128">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="2314f-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2314f-129">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="2314f-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
