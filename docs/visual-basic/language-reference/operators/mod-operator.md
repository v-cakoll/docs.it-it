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
ms.openlocfilehash: 08e3eec08ba099e6f5c7796a459c55de09afa917
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929327"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="9ca52-102">Operatore Mod (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ca52-102">Mod operator (Visual Basic)</span></span>

<span data-ttu-id="9ca52-103">Divide due numeri e restituisce solo il resto.</span><span class="sxs-lookup"><span data-stu-id="9ca52-103">Divides two numbers and returns only the remainder.</span></span>

## <a name="syntax"></a><span data-ttu-id="9ca52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ca52-104">Syntax</span></span>

```vb
result = number1 Mod number2
```

## <a name="parts"></a><span data-ttu-id="9ca52-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9ca52-105">Parts</span></span>

`result` \
<span data-ttu-id="9ca52-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="9ca52-106">Required.</span></span> <span data-ttu-id="9ca52-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="9ca52-107">Any numeric variable or property.</span></span>

`number1` \
<span data-ttu-id="9ca52-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="9ca52-108">Required.</span></span> <span data-ttu-id="9ca52-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="9ca52-109">Any numeric expression.</span></span>

`number2` \
<span data-ttu-id="9ca52-110">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="9ca52-110">Required.</span></span> <span data-ttu-id="9ca52-111">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="9ca52-111">Any numeric expression.</span></span>

## <a name="supported-types"></a><span data-ttu-id="9ca52-112">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="9ca52-112">Supported types</span></span>

<span data-ttu-id="9ca52-113">tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="9ca52-113">All numeric types.</span></span> <span data-ttu-id="9ca52-114">Sono inclusi i tipi a virgola mobile e non firmati `Decimal`e.</span><span class="sxs-lookup"><span data-stu-id="9ca52-114">This includes the unsigned and floating-point types and `Decimal`.</span></span>

## <a name="result"></a><span data-ttu-id="9ca52-115">Risultato</span><span class="sxs-lookup"><span data-stu-id="9ca52-115">Result</span></span>

<span data-ttu-id="9ca52-116">Il risultato è il resto dopo `number1` che è diviso `number2`per.</span><span class="sxs-lookup"><span data-stu-id="9ca52-116">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="9ca52-117">Ad esempio, l'espressione `14 Mod 4` restituisce 2.</span><span class="sxs-lookup"><span data-stu-id="9ca52-117">For example, the expression `14 Mod 4` evaluates to 2.</span></span>

> [!NOTE]
> <span data-ttu-id="9ca52-118">Esiste una differenza tra *resto* e *modulo* in matematica, con risultati diversi per i numeri negativi.</span><span class="sxs-lookup"><span data-stu-id="9ca52-118">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="9ca52-119">L' `Mod` operatore in Visual Basic, l'operatore `op_Modulus` .NET Framework e l'istruzione [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) il sottostante eseguono un'operazione resto.</span><span class="sxs-lookup"><span data-stu-id="9ca52-119">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="9ca52-120">Il risultato di un' `Mod` operazione mantiene il segno del dividendo, `number1`, quindi può essere positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="9ca52-120">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="9ca52-121">Il risultato è sempre compreso nell'intervallo (-`number2`, `number2`), Exclusive.</span><span class="sxs-lookup"><span data-stu-id="9ca52-121">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="9ca52-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ca52-122">For example:</span></span>

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

## <a name="remarks"></a><span data-ttu-id="9ca52-123">Note</span><span class="sxs-lookup"><span data-stu-id="9ca52-123">Remarks</span></span>

<span data-ttu-id="9ca52-124">`number1` Se o `number2` è un valore a virgola mobile, viene restituito il resto a virgola mobile della divisione.</span><span class="sxs-lookup"><span data-stu-id="9ca52-124">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="9ca52-125">Il tipo di dati del risultato è il tipo di dati più piccolo che può conservare tutti i valori possibili risultanti dalla divisione con i tipi `number1` di `number2`dati di e.</span><span class="sxs-lookup"><span data-stu-id="9ca52-125">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>

<span data-ttu-id="9ca52-126">Se `number1` o`number2` restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.</span><span class="sxs-lookup"><span data-stu-id="9ca52-126">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>

<span data-ttu-id="9ca52-127">Gli operatori correlati includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ca52-127">Related operators include the following:</span></span>

- <span data-ttu-id="9ca52-128">L' [operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente integer di una divisione.</span><span class="sxs-lookup"><span data-stu-id="9ca52-128">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="9ca52-129">Ad esempio, l'espressione `14 \ 4` restituisce 3.</span><span class="sxs-lookup"><span data-stu-id="9ca52-129">For example, the expression `14 \ 4` evaluates to 3.</span></span>

- <span data-ttu-id="9ca52-130">L' [operatore/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, come numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="9ca52-130">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="9ca52-131">Ad esempio, l'espressione `14 / 4` restituisce 3,5.</span><span class="sxs-lookup"><span data-stu-id="9ca52-131">For example, the expression `14 / 4` evaluates to 3.5.</span></span>

## <a name="attempted-division-by-zero"></a><span data-ttu-id="9ca52-132">Tentativo di divisione per zero</span><span class="sxs-lookup"><span data-stu-id="9ca52-132">Attempted division by zero</span></span>

<span data-ttu-id="9ca52-133">Se `number2` restituisce zero, il comportamento `Mod` dell'operatore dipende dal tipo di dati degli operandi:</span><span class="sxs-lookup"><span data-stu-id="9ca52-133">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands:</span></span>

- <span data-ttu-id="9ca52-134">Una divisione integrale genera un' <xref:System.DivideByZeroException> eccezione se `number2` non può essere determinata in fase di compilazione e genera un errore `BC30542 Division by zero occurred while evaluating this expression` in fase di `number2` compilazione se viene valutato a zero in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9ca52-134">An integral division throws a <xref:System.DivideByZeroException> exception if `number2` cannot be determined in compile-time and generates a compile-time error `BC30542 Division by zero occurred while evaluating this expression` if `number2` is evaluated to zero at compile-time.</span></span>
- <span data-ttu-id="9ca52-135">Viene restituita <xref:System.Double.NaN?displayProperty=nameWithType>una divisione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="9ca52-135">A floating-point division returns <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>

## <a name="equivalent-formula"></a><span data-ttu-id="9ca52-136">Formula equivalente</span><span class="sxs-lookup"><span data-stu-id="9ca52-136">Equivalent formula</span></span>

<span data-ttu-id="9ca52-137">L'espressione `a Mod b` è equivalente a una delle formule seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ca52-137">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a><span data-ttu-id="9ca52-138">Imprecisione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="9ca52-138">Floating-point imprecision</span></span>

<span data-ttu-id="9ca52-139">Quando si utilizzano numeri a virgola mobile, tenere presente che in memoria non è sempre presente una rappresentazione decimale precisa.</span><span class="sxs-lookup"><span data-stu-id="9ca52-139">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="9ca52-140">Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori `Mod` e l'operatore.</span><span class="sxs-lookup"><span data-stu-id="9ca52-140">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="9ca52-141">Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="9ca52-141">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="overloading"></a><span data-ttu-id="9ca52-142">Overload</span><span class="sxs-lookup"><span data-stu-id="9ca52-142">Overloading</span></span>

<span data-ttu-id="9ca52-143">È `Mod` possibile eseguire l' *Overload*dell'operatore, il che significa che una classe o una struttura può ridefinire il comportamento.</span><span class="sxs-lookup"><span data-stu-id="9ca52-143">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="9ca52-144">Se il codice si `Mod` applica a un'istanza di una classe o una struttura che include tale overload, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="9ca52-144">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9ca52-145">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9ca52-145">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="9ca52-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ca52-146">Example</span></span>

<span data-ttu-id="9ca52-147">Nell'esempio seguente viene usato `Mod` l'operatore per dividere due numeri e restituire solo il resto.</span><span class="sxs-lookup"><span data-stu-id="9ca52-147">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="9ca52-148">Se uno dei due numeri è un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.</span><span class="sxs-lookup"><span data-stu-id="9ca52-148">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a><span data-ttu-id="9ca52-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ca52-149">Example</span></span>

<span data-ttu-id="9ca52-150">Nell'esempio seguente viene illustrata la potenziale imprecisione degli operandi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="9ca52-150">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="9ca52-151">Nella prima istruzione gli operandi sono `Double`e 0,2 è una frazione binaria ripetuta in modo infinito con un valore archiviato di 0.20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="9ca52-151">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="9ca52-152">Nella seconda istruzione, il carattere `D` di tipo letterale impone entrambi gli operandi a `Decimal`e 0,2 presenta una rappresentazione precisa.</span><span class="sxs-lookup"><span data-stu-id="9ca52-152">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a><span data-ttu-id="9ca52-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ca52-153">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="9ca52-154">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="9ca52-154">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="9ca52-155">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ca52-155">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9ca52-156">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="9ca52-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9ca52-157">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9ca52-157">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="9ca52-158">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ca52-158">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="9ca52-159">Operatore \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ca52-159">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
