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
ms.openlocfilehash: f615df50643912beb12eb89d80b922fc30a3e6df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944478"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="0f144-102">Operatore += (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f144-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="0f144-103">Aggiunge il valore di un'espressione numerica al valore di una variabile o di una proprietà numerica e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f144-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="0f144-104">Può essere usato anche per concatenare `String` un'espressione a `String` una variabile o a una proprietà e assegnare il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f144-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f144-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f144-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0f144-106">Parti</span><span class="sxs-lookup"><span data-stu-id="0f144-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="0f144-107">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="0f144-107">Required.</span></span> <span data-ttu-id="0f144-108">Qualsiasi proprietà o `String` variabile numerica.</span><span class="sxs-lookup"><span data-stu-id="0f144-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="0f144-109">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="0f144-109">Required.</span></span> <span data-ttu-id="0f144-110">Qualsiasi espressione o `String` numerica.</span><span class="sxs-lookup"><span data-stu-id="0f144-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f144-111">Note</span><span class="sxs-lookup"><span data-stu-id="0f144-111">Remarks</span></span>  
 <span data-ttu-id="0f144-112">L'elemento sul lato sinistro dell' `+=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="0f144-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="0f144-113">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="0f144-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="0f144-114">L' `+=` operatore aggiunge il valore a destra alla variabile o alla proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0f144-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="0f144-115">L' `+=` operatore può essere usato anche per concatenare `String` l'espressione a destra della `String` variabile o della proprietà a sinistra e assegnare il risultato alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="0f144-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f144-116">Quando si utilizza l' `+=` operatore, potrebbe non essere possibile determinare se si verificherà l'aggiunta o la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="0f144-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="0f144-117">Usare l' `&=` operatore per la concatenazione per eliminare l'ambiguità e per fornire codice autodocumentato.</span><span class="sxs-lookup"><span data-stu-id="0f144-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="0f144-118">Questo operatore di assegnazione esegue in modo implicito le conversioni verso un tipo di ingrandimento ma non di restringimento se l'ambiente di compilazione impone una semantica rigida.</span><span class="sxs-lookup"><span data-stu-id="0f144-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="0f144-119">Per ulteriori informazioni su queste conversioni, vedere la pagina relativa alle conversioni verso un tipo di dati più [piccolo](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="0f144-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="0f144-120">Per ulteriori informazioni sulla semantica restrittiva e permissiva, vedere [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f144-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="0f144-121">Se sono consentite semantiche permissive, l' `+=` operatore esegue `+` in modo implicito una serie di conversioni di stringa e numeriche identiche a quelle eseguite dall'operatore.</span><span class="sxs-lookup"><span data-stu-id="0f144-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="0f144-122">Per informazioni dettagliate su queste conversioni, vedere [operatore +](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0f144-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0f144-123">Overload</span><span class="sxs-lookup"><span data-stu-id="0f144-123">Overloading</span></span>  
 <span data-ttu-id="0f144-124">L' `+` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="0f144-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0f144-125">L'overload dell' `+` operatore influiscono sul comportamento `+=` dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="0f144-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="0f144-126">Se il codice usa `+=` su una classe o una struttura che esegue l' `+`overload di, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="0f144-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0f144-127">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0f144-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f144-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f144-128">Example</span></span>  
 <span data-ttu-id="0f144-129">Nell'esempio seguente viene usato `+=` l'operatore per combinare il valore di una variabile con un'altra.</span><span class="sxs-lookup"><span data-stu-id="0f144-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="0f144-130">La prima parte USA `+=` con le variabili numeriche per aggiungere un valore a un altro.</span><span class="sxs-lookup"><span data-stu-id="0f144-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="0f144-131">La seconda parte USA `+=` con `String` le variabili per concatenare un valore con un altro.</span><span class="sxs-lookup"><span data-stu-id="0f144-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="0f144-132">In entrambi i casi, il risultato viene assegnato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="0f144-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="0f144-133">Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".</span><span class="sxs-lookup"><span data-stu-id="0f144-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f144-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f144-134">See also</span></span>

- [<span data-ttu-id="0f144-135">Operatore +</span><span class="sxs-lookup"><span data-stu-id="0f144-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="0f144-136">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="0f144-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="0f144-137">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="0f144-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="0f144-138">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="0f144-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="0f144-139">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f144-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="0f144-140">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="0f144-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="0f144-141">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="0f144-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
