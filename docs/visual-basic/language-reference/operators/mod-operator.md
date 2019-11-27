---
title: Operatore Mod
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
ms.openlocfilehash: b7552550d4b0496d6ad7ee76a7327054d544b874
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350909"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="54135-102">Operatore Mod (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54135-102">Mod operator (Visual Basic)</span></span>

<span data-ttu-id="54135-103">Divide due numeri e restituisce solo il resto.</span><span class="sxs-lookup"><span data-stu-id="54135-103">Divides two numbers and returns only the remainder.</span></span>

## <a name="syntax"></a><span data-ttu-id="54135-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54135-104">Syntax</span></span>

```vb
result = number1 Mod number2
```

## <a name="parts"></a><span data-ttu-id="54135-105">Parti</span><span class="sxs-lookup"><span data-stu-id="54135-105">Parts</span></span>

`result` \
<span data-ttu-id="54135-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="54135-106">Required.</span></span> <span data-ttu-id="54135-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="54135-107">Any numeric variable or property.</span></span>

`number1` \
<span data-ttu-id="54135-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="54135-108">Required.</span></span> <span data-ttu-id="54135-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="54135-109">Any numeric expression.</span></span>

`number2` \
<span data-ttu-id="54135-110">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="54135-110">Required.</span></span> <span data-ttu-id="54135-111">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="54135-111">Any numeric expression.</span></span>

## <a name="supported-types"></a><span data-ttu-id="54135-112">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="54135-112">Supported types</span></span>

<span data-ttu-id="54135-113">tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="54135-113">All numeric types.</span></span> <span data-ttu-id="54135-114">Sono inclusi i tipi a virgola mobile e senza segno e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="54135-114">This includes the unsigned and floating-point types and `Decimal`.</span></span>

## <a name="result"></a><span data-ttu-id="54135-115">Risultato</span><span class="sxs-lookup"><span data-stu-id="54135-115">Result</span></span>

<span data-ttu-id="54135-116">Il risultato è il resto dopo la divisione di `number1` per `number2`.</span><span class="sxs-lookup"><span data-stu-id="54135-116">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="54135-117">Ad esempio, l'espressione `14 Mod 4` restituisce 2.</span><span class="sxs-lookup"><span data-stu-id="54135-117">For example, the expression `14 Mod 4` evaluates to 2.</span></span>

> [!NOTE]
> <span data-ttu-id="54135-118">Esiste una differenza tra *resto* e *modulo* in matematica, con risultati diversi per i numeri negativi.</span><span class="sxs-lookup"><span data-stu-id="54135-118">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="54135-119">L'operatore `Mod` in Visual Basic, l'operatore .NET Framework `op_Modulus` e l'istruzione [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) il sottostante eseguono un'operazione resto.</span><span class="sxs-lookup"><span data-stu-id="54135-119">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="54135-120">Il risultato di un'operazione di `Mod` mantiene il segno del dividendo, `number1`e pertanto può essere positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="54135-120">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="54135-121">Il risultato è sempre compreso nell'intervallo (-`number2`, `number2`), Exclusive.</span><span class="sxs-lookup"><span data-stu-id="54135-121">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="54135-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="54135-122">For example:</span></span>

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

## <a name="remarks"></a><span data-ttu-id="54135-123">Note</span><span class="sxs-lookup"><span data-stu-id="54135-123">Remarks</span></span>

<span data-ttu-id="54135-124">Se `number1` o `number2` è un valore a virgola mobile, viene restituito il resto a virgola mobile della divisione.</span><span class="sxs-lookup"><span data-stu-id="54135-124">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="54135-125">Il tipo di dati del risultato è il tipo di dati più piccolo che può conservare tutti i valori possibili risultanti dalla divisione con i tipi di dati di `number1` e `number2`.</span><span class="sxs-lookup"><span data-stu-id="54135-125">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>

<span data-ttu-id="54135-126">Se `number1` o `number2` restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.</span><span class="sxs-lookup"><span data-stu-id="54135-126">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>

<span data-ttu-id="54135-127">Gli operatori correlati includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="54135-127">Related operators include the following:</span></span>

- <span data-ttu-id="54135-128">L' [operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente integer di una divisione.</span><span class="sxs-lookup"><span data-stu-id="54135-128">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="54135-129">Ad esempio, l'espressione `14 \ 4` restituisce 3.</span><span class="sxs-lookup"><span data-stu-id="54135-129">For example, the expression `14 \ 4` evaluates to 3.</span></span>

- <span data-ttu-id="54135-130">L' [operatore/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto, come numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="54135-130">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="54135-131">Ad esempio, l'espressione `14 / 4` restituisce 3,5.</span><span class="sxs-lookup"><span data-stu-id="54135-131">For example, the expression `14 / 4` evaluates to 3.5.</span></span>

## <a name="attempted-division-by-zero"></a><span data-ttu-id="54135-132">Tentativo di divisione per zero</span><span class="sxs-lookup"><span data-stu-id="54135-132">Attempted division by zero</span></span>

<span data-ttu-id="54135-133">Se `number2` restituisce zero, il comportamento dell'operatore `Mod` dipende dal tipo di dati degli operandi:</span><span class="sxs-lookup"><span data-stu-id="54135-133">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands:</span></span>

- <span data-ttu-id="54135-134">Una divisione integrale genera un'eccezione <xref:System.DivideByZeroException> se non è possibile determinare `number2` in fase di compilazione e genera un errore in fase di compilazione `BC30542 Division by zero occurred while evaluating this expression` se `number2` viene valutato a zero in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="54135-134">An integral division throws a <xref:System.DivideByZeroException> exception if `number2` cannot be determined in compile-time and generates a compile-time error `BC30542 Division by zero occurred while evaluating this expression` if `number2` is evaluated to zero at compile-time.</span></span>
- <span data-ttu-id="54135-135">Una divisione a virgola mobile restituisce <xref:System.Double.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="54135-135">A floating-point division returns <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>

## <a name="equivalent-formula"></a><span data-ttu-id="54135-136">Formula equivalente</span><span class="sxs-lookup"><span data-stu-id="54135-136">Equivalent formula</span></span>

<span data-ttu-id="54135-137">L'espressione `a Mod b` è equivalente a una delle formule seguenti:</span><span class="sxs-lookup"><span data-stu-id="54135-137">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a><span data-ttu-id="54135-138">Imprecisione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="54135-138">Floating-point imprecision</span></span>

<span data-ttu-id="54135-139">Quando si utilizzano numeri a virgola mobile, tenere presente che in memoria non è sempre presente una rappresentazione decimale precisa.</span><span class="sxs-lookup"><span data-stu-id="54135-139">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="54135-140">Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l'operatore `Mod`.</span><span class="sxs-lookup"><span data-stu-id="54135-140">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="54135-141">Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="54135-141">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="overloading"></a><span data-ttu-id="54135-142">Overload</span><span class="sxs-lookup"><span data-stu-id="54135-142">Overloading</span></span>

<span data-ttu-id="54135-143">È possibile eseguire l' *Overload*dell'operatore `Mod`, il che significa che una classe o una struttura può ridefinire il comportamento.</span><span class="sxs-lookup"><span data-stu-id="54135-143">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="54135-144">Se il codice viene applicato `Mod` a un'istanza di una classe o una struttura che include tale overload, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="54135-144">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="54135-145">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="54135-145">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="54135-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="54135-146">Example</span></span>

<span data-ttu-id="54135-147">Nell'esempio seguente viene usato l'operatore `Mod` per dividere due numeri e restituire solo il resto.</span><span class="sxs-lookup"><span data-stu-id="54135-147">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="54135-148">Se uno dei due numeri è un numero a virgola mobile, il risultato è un numero a virgola mobile che rappresenta il resto.</span><span class="sxs-lookup"><span data-stu-id="54135-148">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a><span data-ttu-id="54135-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="54135-149">Example</span></span>

<span data-ttu-id="54135-150">Nell'esempio seguente viene illustrata la potenziale imprecisione degli operandi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="54135-150">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="54135-151">Nella prima istruzione gli operandi sono `Double`e 0,2 è una frazione binaria ripetuta in modo infinito con un valore archiviato di 0.20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="54135-151">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="54135-152">Nella seconda istruzione, il carattere di tipo letterale `D` impone a entrambi gli operandi di `Decimal`e 0,2 presenta una rappresentazione precisa.</span><span class="sxs-lookup"><span data-stu-id="54135-152">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a><span data-ttu-id="54135-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54135-153">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="54135-154">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="54135-154">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="54135-155">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54135-155">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="54135-156">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="54135-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="54135-157">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="54135-157">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="54135-158">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54135-158">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="54135-159">Operatore \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54135-159">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
