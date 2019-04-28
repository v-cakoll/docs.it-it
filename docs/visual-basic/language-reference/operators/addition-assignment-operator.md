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
ms.openlocfilehash: 4b8f36397d0f52866ebe9fa188d6b163364aeffc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608333"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a2120-102">Operatore += (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2120-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="a2120-103">Aggiunge il valore di un'espressione numerica per il valore di una proprietà o variabile numerica e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="a2120-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="a2120-104">Può anche essere utilizzato per concatenare un' `String` espressione da un `String` variabile o proprietà e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="a2120-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2120-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2120-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a2120-106">Parti</span><span class="sxs-lookup"><span data-stu-id="a2120-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a2120-107">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2120-107">Required.</span></span> <span data-ttu-id="a2120-108">Qualsiasi numerica o `String` variabile o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="a2120-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a2120-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a2120-109">Required.</span></span> <span data-ttu-id="a2120-110">Qualsiasi numerica o `String` espressione.</span><span class="sxs-lookup"><span data-stu-id="a2120-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2120-111">Note</span><span class="sxs-lookup"><span data-stu-id="a2120-111">Remarks</span></span>  
 <span data-ttu-id="a2120-112">L'elemento sul lato sinistro del `+=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="a2120-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a2120-113">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a2120-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a2120-114">Il `+=` operatore aggiunge il valore alla sua destra per la variabile o una proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="a2120-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="a2120-115">Il `+=` operatore può essere utilizzato anche per concatenare le `String` espressione alla sua destra per il `String` variabile o proprietà a sinistra e le assegna il risultato alla variabile o una proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="a2120-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2120-116">Quando si usa il `+=` operatore, potrebbe non essere in grado di determinare se verrà eseguita la concatenazione di aggiunta o la stringa.</span><span class="sxs-lookup"><span data-stu-id="a2120-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="a2120-117">Usare il `&=` operatore per la concatenazione per evitare ambiguità e fornire codice autodocumentato.</span><span class="sxs-lookup"><span data-stu-id="a2120-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="a2120-118">L'operatore di assegnazione esegue in modo implicito di ampliamento ma non delle conversioni di narrowing se l'ambiente di compilazione impone la semantica rigorosa.</span><span class="sxs-lookup"><span data-stu-id="a2120-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="a2120-119">Per altre informazioni sulle conversioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="a2120-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="a2120-120">Per altre informazioni sulla semantica rigida e permissiva, vedere [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a2120-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="a2120-121">Se la semantica permissiva è consentita, il `+=` operatore esegue in modo implicito una serie di conversioni di stringa e numeriche identiche a quelli eseguiti dal `+` operatore.</span><span class="sxs-lookup"><span data-stu-id="a2120-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="a2120-122">Per informazioni dettagliate su queste conversioni, vedere [operatore +](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a2120-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a2120-123">Overload</span><span class="sxs-lookup"><span data-stu-id="a2120-123">Overloading</span></span>  
 <span data-ttu-id="a2120-124">Il `+` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="a2120-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a2120-125">L'overload di `+` operatore influisce sul comportamento del `+=` operatore.</span><span class="sxs-lookup"><span data-stu-id="a2120-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="a2120-126">Se il codice usi `+=` in una classe o struttura che esegue l'overload `+`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="a2120-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a2120-127">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a2120-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2120-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2120-128">Example</span></span>  
 <span data-ttu-id="a2120-129">L'esempio seguente usa il `+=` operatore combinare il valore di una variabile con un altro.</span><span class="sxs-lookup"><span data-stu-id="a2120-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="a2120-130">La prima parte Usa `+=` alle variabili numeriche per aggiungere un valore a un altro.</span><span class="sxs-lookup"><span data-stu-id="a2120-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="a2120-131">Usa la seconda parte `+=` con `String` variabili per concatenare due valori con un altro.</span><span class="sxs-lookup"><span data-stu-id="a2120-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="a2120-132">In entrambi i casi, il risultato viene assegnato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="a2120-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="a2120-133">Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".</span><span class="sxs-lookup"><span data-stu-id="a2120-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2120-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2120-134">See also</span></span>

- [<span data-ttu-id="a2120-135">Operatore +</span><span class="sxs-lookup"><span data-stu-id="a2120-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="a2120-136">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="a2120-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="a2120-137">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="a2120-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="a2120-138">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="a2120-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="a2120-139">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a2120-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a2120-140">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="a2120-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a2120-141">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="a2120-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
