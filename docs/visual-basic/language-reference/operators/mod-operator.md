---
title: Operatore Mod (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="7f095-102">Operatore Mod (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f095-102">Mod Operator (Visual Basic)</span></span>
<span data-ttu-id="7f095-103">Divide due numeri e restituisce solo il resto.</span><span class="sxs-lookup"><span data-stu-id="7f095-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f095-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f095-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="7f095-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7f095-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="7f095-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f095-106">Required.</span></span> <span data-ttu-id="7f095-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7f095-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="7f095-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f095-108">Required.</span></span> <span data-ttu-id="7f095-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7f095-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7f095-110">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="7f095-110">Supported Types</span></span>  
 <span data-ttu-id="7f095-111">Tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="7f095-111">All numeric types.</span></span> <span data-ttu-id="7f095-112">Sono inclusi i tipi senza segno a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="7f095-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="7f095-113">Risultato</span><span class="sxs-lookup"><span data-stu-id="7f095-113">Result</span></span>  
 <span data-ttu-id="7f095-114">Il risultato è il resto dopo `number1` viene diviso per `number2`.</span><span class="sxs-lookup"><span data-stu-id="7f095-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="7f095-115">Ad esempio, l'espressione `14 Mod 4` restituisce 2.</span><span class="sxs-lookup"><span data-stu-id="7f095-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f095-116">Note</span><span class="sxs-lookup"><span data-stu-id="7f095-116">Remarks</span></span>  
 <span data-ttu-id="7f095-117">Se il valore `number1` o `number2` è un valore a virgola mobile, viene restituito il resto della divisione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="7f095-117">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="7f095-118">Il tipo di dati del risultato è il tipo di dati più piccolo che può contenere tutti i possibili valori risultanti dalla divisione con i tipi di dati di `number1` e `number2`.</span><span class="sxs-lookup"><span data-stu-id="7f095-118">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="7f095-119">Se `number1` o `number2` restituisce [nulla](../../../visual-basic/language-reference/nothing.md), viene considerato pari a zero.</span><span class="sxs-lookup"><span data-stu-id="7f095-119">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="7f095-120">Gli operatori correlati includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7f095-120">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="7f095-121">Il [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente di una divisione.</span><span class="sxs-lookup"><span data-stu-id="7f095-121">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="7f095-122">Ad esempio, l'espressione `14 \ 4` restituisce 3.</span><span class="sxs-lookup"><span data-stu-id="7f095-122">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="7f095-123">Il [/ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, come numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="7f095-123">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="7f095-124">Ad esempio, l'espressione `14 / 4` restituisce 3.5.</span><span class="sxs-lookup"><span data-stu-id="7f095-124">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="7f095-125">Tentativo di divisione per Zero</span><span class="sxs-lookup"><span data-stu-id="7f095-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="7f095-126">Se `number2` restituisce zero, il comportamento del `Mod` operatore dipende dal tipo di dati degli operandi.</span><span class="sxs-lookup"><span data-stu-id="7f095-126">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="7f095-127">Una divisione integrale genera un <xref:System.DivideByZeroException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="7f095-127">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="7f095-128">Restituisce una divisione a virgola mobile <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="7f095-128">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="7f095-129">Formula equivalente</span><span class="sxs-lookup"><span data-stu-id="7f095-129">Equivalent Formula</span></span>  
 <span data-ttu-id="7f095-130">L'espressione `a Mod b` è equivalente a una delle seguenti formule:</span><span class="sxs-lookup"><span data-stu-id="7f095-130">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="7f095-131">A virgola mobile imprecisione</span><span class="sxs-lookup"><span data-stu-id="7f095-131">Floating-Point Imprecision</span></span>  
 <span data-ttu-id="7f095-132">Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre contengono una precisa rappresentazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="7f095-132">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="7f095-133">Ciò potrebbe provocare risultati imprevisti da alcune operazioni, ad esempio il confronto di valori e `Mod` operatore.</span><span class="sxs-lookup"><span data-stu-id="7f095-133">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="7f095-134">Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f095-134">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7f095-135">Overload</span><span class="sxs-lookup"><span data-stu-id="7f095-135">Overloading</span></span>  
 <span data-ttu-id="7f095-136">Il `Mod` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il relativo comportamento.</span><span class="sxs-lookup"><span data-stu-id="7f095-136">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="7f095-137">Se il codice applica `Mod` a un'istanza di una classe o struttura che include un overload di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="7f095-137">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7f095-138">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7f095-138">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f095-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f095-139">Example</span></span>  
 <span data-ttu-id="7f095-140">L'esempio seguente usa il `Mod` operatore di divisione tra due numeri e restituire solo il resto.</span><span class="sxs-lookup"><span data-stu-id="7f095-140">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="7f095-141">Se il numero è un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.</span><span class="sxs-lookup"><span data-stu-id="7f095-141">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="7f095-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f095-142">Example</span></span>  
 <span data-ttu-id="7f095-143">L'esempio seguente illustra la potenziale imprecisione degli operandi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="7f095-143">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="7f095-144">Nella prima istruzione, gli operandi sono `Double`, e una frazione binaria ripetuta all'infinito con un valore archiviato di 0,20000000000000001 0,2.</span><span class="sxs-lookup"><span data-stu-id="7f095-144">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="7f095-145">Nella seconda istruzione, il valore letterale carattere tipo `D` impone entrambi gli operandi siano `Decimal`, e 0,2 la rappresentazione è precisa.</span><span class="sxs-lookup"><span data-stu-id="7f095-145">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7f095-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f095-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="7f095-147">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="7f095-147">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="7f095-148">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f095-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="7f095-149">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="7f095-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="7f095-150">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7f095-150">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="7f095-151">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f095-151">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="7f095-152">\ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f095-152">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
