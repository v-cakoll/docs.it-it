---
title: Operatore += (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: f12a0560d984f871110c02f1df2c2ec42b68809b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604016"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="06022-102">Operatore += (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06022-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="06022-103">Aggiunge il valore di un'espressione numerica per il valore di una proprietà o una variabile numerica e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="06022-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="06022-104">Può essere utilizzato anche per concatenare un `String` espressione da un `String` variabile o proprietà e assegnare il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="06022-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06022-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06022-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="06022-106">Parti</span><span class="sxs-lookup"><span data-stu-id="06022-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="06022-107">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="06022-107">Required.</span></span> <span data-ttu-id="06022-108">Qualsiasi numerica o `String` variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="06022-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="06022-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="06022-109">Required.</span></span> <span data-ttu-id="06022-110">Qualsiasi numerica o `String` espressione.</span><span class="sxs-lookup"><span data-stu-id="06022-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06022-111">Note</span><span class="sxs-lookup"><span data-stu-id="06022-111">Remarks</span></span>  
 <span data-ttu-id="06022-112">L'elemento sul lato sinistro del `+=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="06022-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="06022-113">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="06022-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="06022-114">Il `+=` operatore aggiunge il valore alla sua destra alla variabile o proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="06022-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="06022-115">Il `+=` operatore può essere utilizzato anche per concatenare il `String` espressione alla sua destra per il `String` variabile o proprietà relativi a sinistra e assegnare il risultato alla variabile o proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="06022-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06022-116">Quando si utilizza il `+=` operatore, potrebbe non essere in grado di determinare se verrà eseguita la concatenazione di addizione o stringa.</span><span class="sxs-lookup"><span data-stu-id="06022-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="06022-117">Utilizzare il `&=` operatore per la concatenazione per evitare ambiguità e fornire codice autodocumentato.</span><span class="sxs-lookup"><span data-stu-id="06022-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="06022-118">L'operatore di assegnazione esegue, in modo implicito, ma non le conversioni di restrizione se l'ambiente di compilazione viene applicata una semantica di ampliamento.</span><span class="sxs-lookup"><span data-stu-id="06022-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="06022-119">Per ulteriori informazioni sulle conversioni, vedere [conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="06022-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="06022-120">Per ulteriori informazioni sulla semantica rigida e permissiva, vedere [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="06022-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="06022-121">Se la semantica permissiva è consentita, la `+=` operatore esegue in modo implicito una serie di conversioni di stringa e numerici identiche a quelli eseguiti dal `+` operatore.</span><span class="sxs-lookup"><span data-stu-id="06022-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="06022-122">Per informazioni dettagliate su queste conversioni, vedere [+ (operatore)](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="06022-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="06022-123">Overload</span><span class="sxs-lookup"><span data-stu-id="06022-123">Overloading</span></span>  
 <span data-ttu-id="06022-124">Il `+` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="06022-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="06022-125">L'overload di `+` operatore influisce sul comportamento del `+=` operatore.</span><span class="sxs-lookup"><span data-stu-id="06022-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="06022-126">Se il codice utilizza `+=` in una classe o struttura che esegue l'overload `+`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="06022-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="06022-127">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="06022-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06022-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="06022-128">Example</span></span>  
 <span data-ttu-id="06022-129">L'esempio seguente usa il `+=` operatore per combinare il valore di una variabile con un altro.</span><span class="sxs-lookup"><span data-stu-id="06022-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="06022-130">La prima parte Usa `+=` con le variabili numeriche per aggiungere un valore a un altro.</span><span class="sxs-lookup"><span data-stu-id="06022-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="06022-131">Utilizza la seconda parte `+=` con `String` variabili per concatenare due valori con un altro.</span><span class="sxs-lookup"><span data-stu-id="06022-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="06022-132">In entrambi i casi, il risultato viene assegnato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="06022-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 <span data-ttu-id="06022-133">Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".</span><span class="sxs-lookup"><span data-stu-id="06022-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06022-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06022-134">See Also</span></span>  
 [<span data-ttu-id="06022-135">Operatore +</span><span class="sxs-lookup"><span data-stu-id="06022-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [<span data-ttu-id="06022-136">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="06022-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="06022-137">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="06022-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="06022-138">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="06022-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="06022-139">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06022-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="06022-140">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="06022-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="06022-141">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="06022-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
