---
title: Operatore +=
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
ms.openlocfilehash: 31a6da163061b905b8ffddcfc4b44978f5cdd55e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350300"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d4cb2-102">Operatore += (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4cb2-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="d4cb2-103">Aggiunge il valore di un'espressione numerica al valore di una variabile o di una proprietà numerica e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="d4cb2-104">Può essere usato anche per concatenare un'espressione `String` a una variabile o una proprietà `String` e assegnare il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4cb2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4cb2-105">Syntax</span></span>  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="d4cb2-106">Parti</span><span class="sxs-lookup"><span data-stu-id="d4cb2-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="d4cb2-107">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-107">Required.</span></span> <span data-ttu-id="d4cb2-108">Qualsiasi variabile o proprietà numerica o `String`.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="d4cb2-109">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-109">Required.</span></span> <span data-ttu-id="d4cb2-110">Qualsiasi espressione numerica o `String`.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4cb2-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d4cb2-111">Remarks</span></span>  
 <span data-ttu-id="d4cb2-112">L'elemento sul lato sinistro dell'operatore `+=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d4cb2-113">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="d4cb2-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="d4cb2-114">L'operatore `+=` aggiunge il valore a destra alla variabile o alla proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="d4cb2-115">L'operatore `+=` può essere usato anche per concatenare l'espressione `String` a destra della variabile `String` o della proprietà a sinistra e assegnare il risultato alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4cb2-116">Quando si usa l'operatore di `+=`, potrebbe non essere possibile determinare se si verificherà la concatenazione dell'aggiunta o della stringa.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="d4cb2-117">Usare l'operatore `&=` per la concatenazione per eliminare l'ambiguità e per fornire codice autodocumentato.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="d4cb2-118">Questo operatore di assegnazione esegue in modo implicito le conversioni verso un tipo di ingrandimento ma non di restringimento se l'ambiente di compilazione impone una semantica rigida.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="d4cb2-119">Per ulteriori informazioni su queste conversioni, vedere la pagina relativa alle [conversioni](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)verso un tipo di dati più piccolo.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="d4cb2-120">Per ulteriori informazioni sulla semantica restrittiva e permissiva, vedere [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d4cb2-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="d4cb2-121">Se sono consentite semantiche permissive, l'operatore `+=` esegue in modo implicito una serie di conversioni di stringa e numeriche identiche a quelle eseguite dall'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="d4cb2-122">Per informazioni dettagliate su queste conversioni, vedere [operatore +](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d4cb2-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d4cb2-123">Overload</span><span class="sxs-lookup"><span data-stu-id="d4cb2-123">Overloading</span></span>  
 <span data-ttu-id="d4cb2-124">L'operatore `+` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d4cb2-125">L'overload dell'operatore `+` influiscono sul comportamento dell'operatore `+=`.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="d4cb2-126">Se il codice USA `+=` su una classe o una struttura che esegue l'overload di `+`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d4cb2-127">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d4cb2-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4cb2-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4cb2-128">Example</span></span>  
 <span data-ttu-id="d4cb2-129">Nell'esempio seguente viene usato l'operatore `+=` per combinare il valore di una variabile con un'altra.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="d4cb2-130">La prima parte USA `+=` con variabili numeriche per aggiungere un valore a un altro.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="d4cb2-131">La seconda parte USA `+=` con `String` variabili per concatenare un valore con un altro.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="d4cb2-132">In entrambi i casi, il risultato viene assegnato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="d4cb2-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="d4cb2-133">Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".</span><span class="sxs-lookup"><span data-stu-id="d4cb2-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cb2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4cb2-134">See also</span></span>

- [<span data-ttu-id="d4cb2-135">Operatore +</span><span class="sxs-lookup"><span data-stu-id="d4cb2-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="d4cb2-136">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="d4cb2-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="d4cb2-137">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="d4cb2-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="d4cb2-138">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="d4cb2-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="d4cb2-139">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4cb2-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d4cb2-140">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="d4cb2-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d4cb2-141">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="d4cb2-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
