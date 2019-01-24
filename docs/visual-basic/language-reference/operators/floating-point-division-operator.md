---
title: Operatore / (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: 2036ec8009cfc72a20bcd828d7bc0b252e620cab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610825"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="0af84-102">Operatore / (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0af84-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="0af84-103">Divide due numeri e restituisce un risultato a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="0af84-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af84-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0af84-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="0af84-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0af84-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="0af84-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0af84-106">Required.</span></span> <span data-ttu-id="0af84-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="0af84-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="0af84-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0af84-108">Required.</span></span> <span data-ttu-id="0af84-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="0af84-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="0af84-110">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="0af84-110">Supported Types</span></span>  
 <span data-ttu-id="0af84-111">Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="0af84-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="0af84-112">Risultato</span><span class="sxs-lookup"><span data-stu-id="0af84-112">Result</span></span>  
 <span data-ttu-id="0af84-113">Il risultato è il quoziente completo del `expression1` diviso per `expression2`, incluso l'eventuale resto.</span><span class="sxs-lookup"><span data-stu-id="0af84-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="0af84-114">Il [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente, interrompendo il resto.</span><span class="sxs-lookup"><span data-stu-id="0af84-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0af84-115">Note</span><span class="sxs-lookup"><span data-stu-id="0af84-115">Remarks</span></span>  
 <span data-ttu-id="0af84-116">Il tipo di dati del risultato dipende dai tipi degli operandi.</span><span class="sxs-lookup"><span data-stu-id="0af84-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="0af84-117">La tabella seguente illustra come viene determinato il tipo di dati del risultato.</span><span class="sxs-lookup"><span data-stu-id="0af84-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="0af84-118">Tipi di dati di operando</span><span class="sxs-lookup"><span data-stu-id="0af84-118">Operand data types</span></span>|<span data-ttu-id="0af84-119">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0af84-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="0af84-120">Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [breve](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="0af84-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="0af84-121">Un'espressione è un [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) tipo di dati e l'altro non è un [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="0af84-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="0af84-122">Un'espressione è un [decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md) tipo di dati e l'altro non è un [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) o un [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="0af84-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="0af84-123">Delle espressioni è una [doppie](../../../visual-basic/language-reference/data-types/double-data-type.md) tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0af84-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="0af84-124">Prima di eseguita la divisione, le espressioni numeriche integrali vengono estesi a `Double`.</span><span class="sxs-lookup"><span data-stu-id="0af84-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="0af84-125">Se si assegna il risultato a un tipo di dati integrali, Visual Basic tenta di convertire il risultato da `Double` per quel tipo.</span><span class="sxs-lookup"><span data-stu-id="0af84-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="0af84-126">Ciò può generare un'eccezione se il risultato non rientra in tale tipo.</span><span class="sxs-lookup"><span data-stu-id="0af84-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="0af84-127">In particolare, vedere "Ha tentato di divisione per Zero" in questa pagina della Guida.</span><span class="sxs-lookup"><span data-stu-id="0af84-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="0af84-128">Se `expression1` oppure `expression2` restituisca [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.</span><span class="sxs-lookup"><span data-stu-id="0af84-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="0af84-129">Tentativo di divisione per Zero</span><span class="sxs-lookup"><span data-stu-id="0af84-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="0af84-130">Se `expression2` restituisce zero, il `/` operatore si comporta in modo diverso per i tipi di dati di operando diversi.</span><span class="sxs-lookup"><span data-stu-id="0af84-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="0af84-131">Nella tabella seguente sono elencati i comportamenti possibili.</span><span class="sxs-lookup"><span data-stu-id="0af84-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="0af84-132">Tipi di dati di operando</span><span class="sxs-lookup"><span data-stu-id="0af84-132">Operand data types</span></span>|<span data-ttu-id="0af84-133">Comportamento se `expression2` è uguale a zero</span><span class="sxs-lookup"><span data-stu-id="0af84-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="0af84-134">A virgola mobile (`Single` o `Double`)</span><span class="sxs-lookup"><span data-stu-id="0af84-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="0af84-135">Restituisce un numero infinito (<xref:System.Double.PositiveInfinity> oppure <xref:System.Double.NegativeInfinity>), o <xref:System.Double.NaN> (non un numero) se `expression1` anche è zero</span><span class="sxs-lookup"><span data-stu-id="0af84-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="0af84-136">Genera un'eccezione <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="0af84-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="0af84-137">Integrale (con o senza segno)</span><span class="sxs-lookup"><span data-stu-id="0af84-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="0af84-138">Tentativo di riconvertire in genera un'eccezione di tipo integrale <xref:System.OverflowException> perché non possono accettare i tipi integrali <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, o <xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="0af84-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0af84-139">Il `/` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="0af84-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0af84-140">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="0af84-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0af84-141">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0af84-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0af84-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="0af84-142">Example</span></span>  
 <span data-ttu-id="0af84-143">Questo esempio viene usato il `/` operatore per eseguire la divisione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="0af84-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="0af84-144">Il risultato è il quoziente di due operandi.</span><span class="sxs-lookup"><span data-stu-id="0af84-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 <span data-ttu-id="0af84-145">Le espressioni nell'esempio precedente restituiscono valori di 2,5 e 3,333333.</span><span class="sxs-lookup"><span data-stu-id="0af84-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="0af84-146">Si noti che il risultato è sempre a virgola mobile (`Double`), anche se entrambi gli operandi sono costanti integer.</span><span class="sxs-lookup"><span data-stu-id="0af84-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af84-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0af84-147">See also</span></span>
- [<span data-ttu-id="0af84-148">/ = (Operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0af84-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="0af84-149">\ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0af84-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="0af84-150">Tipi di dati dei risultati degli operatori</span><span class="sxs-lookup"><span data-stu-id="0af84-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="0af84-151">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="0af84-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="0af84-152">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0af84-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="0af84-153">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="0af84-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="0af84-154">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0af84-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
