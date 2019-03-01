---
title: Operatore Mod (Visual Basic)
ms.date: 04/24/2018
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
ms.openlocfilehash: 6bb34eb810f6e2d0b0d631f5891e3e65aa0b170f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981400"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="fae78-102">Operatore Mod (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fae78-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="fae78-103">Divide due numeri e restituisce solo il resto.</span><span class="sxs-lookup"><span data-stu-id="fae78-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae78-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fae78-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="fae78-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fae78-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="fae78-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fae78-106">Required.</span></span> <span data-ttu-id="fae78-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="fae78-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="fae78-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fae78-108">Required.</span></span> <span data-ttu-id="fae78-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="fae78-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="fae78-110">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="fae78-110">Supported types</span></span>  
 <span data-ttu-id="fae78-111">tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="fae78-111">All numeric types.</span></span> <span data-ttu-id="fae78-112">Inclusi i tipi senza segno e a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="fae78-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="fae78-113">Risultato</span><span class="sxs-lookup"><span data-stu-id="fae78-113">Result</span></span>

<span data-ttu-id="fae78-114">Il risultato è il resto dopo aver `number1` diviso per `number2`.</span><span class="sxs-lookup"><span data-stu-id="fae78-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="fae78-115">Ad esempio, l'espressione `14 Mod 4` restituisce 2.</span><span class="sxs-lookup"><span data-stu-id="fae78-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="fae78-116">È presente una differenza tra *resto* e *modulus* in matematica, con risultati diversi per i numeri negativi.</span><span class="sxs-lookup"><span data-stu-id="fae78-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="fae78-117">Il `Mod` operatore in Visual Basic, .NET Framework `op_Modulus` operatore e sottostante [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) istruzione che eseguire un'operazione di resto.</span><span class="sxs-lookup"><span data-stu-id="fae78-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="fae78-118">Il risultato di una `Mod` operazione consente di mantenere il segno del dividendo, `number1`, e pertanto può essere positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="fae78-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="fae78-119">Il risultato è sempre compreso nell'intervallo (-`number2`, `number2`), esclusivo.</span><span class="sxs-lookup"><span data-stu-id="fae78-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="fae78-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fae78-120">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="fae78-121">Note</span><span class="sxs-lookup"><span data-stu-id="fae78-121">Remarks</span></span>  
 <span data-ttu-id="fae78-122">Se uno dei due `number1` o `number2` è un valore a virgola mobile, viene restituito il resto della divisione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="fae78-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="fae78-123">Il tipo di dati del risultato è il tipo di dati più piccolo che può contenere tutti i possibili valori risultanti dalla divisione con i tipi di dati di `number1` e `number2`.</span><span class="sxs-lookup"><span data-stu-id="fae78-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="fae78-124">Se `number1` oppure `number2` restituisca [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.</span><span class="sxs-lookup"><span data-stu-id="fae78-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="fae78-125">Gli operatori correlati includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fae78-125">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="fae78-126">Il [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente di una divisione.</span><span class="sxs-lookup"><span data-stu-id="fae78-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="fae78-127">Ad esempio, l'espressione `14 \ 4` restituisce 3.</span><span class="sxs-lookup"><span data-stu-id="fae78-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="fae78-128">Il [/ operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, sotto forma di numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="fae78-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="fae78-129">Ad esempio, l'espressione `14 / 4` 3.5 viene valutata.</span><span class="sxs-lookup"><span data-stu-id="fae78-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="fae78-130">Tentativo di divisione per zero</span><span class="sxs-lookup"><span data-stu-id="fae78-130">Attempted division by zero</span></span>  
 <span data-ttu-id="fae78-131">Se `number2` restituisce zero, il comportamento del `Mod` operatore dipende dal tipo dei dati degli operandi.</span><span class="sxs-lookup"><span data-stu-id="fae78-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="fae78-132">Una divisione integrale genera un <xref:System.DivideByZeroException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="fae78-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="fae78-133">Restituisce una divisione a virgola mobile <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="fae78-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="fae78-134">Formula equivalente</span><span class="sxs-lookup"><span data-stu-id="fae78-134">Equivalent formula</span></span>  
 <span data-ttu-id="fae78-135">L'espressione `a Mod b` è equivalente a una delle formule seguenti:</span><span class="sxs-lookup"><span data-stu-id="fae78-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="fae78-136">A virgola mobile dell'imprecisione</span><span class="sxs-lookup"><span data-stu-id="fae78-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="fae78-137">Quando si lavora con numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione decimale precisa in memoria.</span><span class="sxs-lookup"><span data-stu-id="fae78-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="fae78-138">Questo può causare risultati imprevisti da determinate operazioni, ad esempio il confronto dei valori e `Mod` operatore.</span><span class="sxs-lookup"><span data-stu-id="fae78-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="fae78-139">Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fae78-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fae78-140">Overload</span><span class="sxs-lookup"><span data-stu-id="fae78-140">Overloading</span></span>  
 <span data-ttu-id="fae78-141">Il `Mod` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il relativo comportamento.</span><span class="sxs-lookup"><span data-stu-id="fae78-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="fae78-142">Se il codice applica `Mod` a un'istanza di una classe o struttura che include un overload di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="fae78-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fae78-143">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fae78-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fae78-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="fae78-144">Example</span></span>  
 <span data-ttu-id="fae78-145">L'esempio seguente usa il `Mod` operatore divide due numeri e restituisce solo il resto.</span><span class="sxs-lookup"><span data-stu-id="fae78-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="fae78-146">Se uno dei due numeri sono un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.</span><span class="sxs-lookup"><span data-stu-id="fae78-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="fae78-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="fae78-147">Example</span></span>  
 <span data-ttu-id="fae78-148">L'esempio seguente illustra le potenzialità dell'imprecisione di operandi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="fae78-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="fae78-149">Nella prima istruzione, gli operandi sono `Double`, e una frazione binaria ripetuta all'infinito con un valore memorizzato di 0.20000000000000001 0,2.</span><span class="sxs-lookup"><span data-stu-id="fae78-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="fae78-150">Nella seconda istruzione, di tipo carattere letterale `D` forza di entrambi gli operandi in `Decimal`, e 0.2 la rappresentazione è precisa.</span><span class="sxs-lookup"><span data-stu-id="fae78-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="fae78-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fae78-151">See also</span></span>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="fae78-152">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="fae78-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="fae78-153">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fae78-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fae78-154">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="fae78-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fae78-155">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="fae78-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="fae78-156">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fae78-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="fae78-157">\ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fae78-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
