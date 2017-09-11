---
title: / Operatore (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
dev_langs:
- VB
helpviewer_keywords:
- division operator, floating point
- floating-point numbers, division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators, division
- division, by zero
- operators [Visual Basic], division
- division operator, syntax
- / operator [Visual Basic]
- math operators
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 82255339c3bdab7f6e760de9bef073f463260877
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="332f3-102">Operatore / (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="332f3-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="332f3-103">Divide due numeri e restituisce un risultato a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="332f3-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="332f3-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="332f3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="332f3-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="332f3-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="332f3-106">Required.</span></span> <span data-ttu-id="332f3-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="332f3-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="332f3-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="332f3-108">Required.</span></span> <span data-ttu-id="332f3-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="332f3-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="332f3-110">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="332f3-110">Supported Types</span></span>  
 <span data-ttu-id="332f3-111">Tutti i tipi numerici, inclusi i tipi a virgola mobile e senza segno e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="332f3-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="332f3-112">Risultato</span><span class="sxs-lookup"><span data-stu-id="332f3-112">Result</span></span>  
 <span data-ttu-id="332f3-113">Il risultato è il quoziente completo di `expression1` diviso `expression2`, incluso l'eventuale resto.</span><span class="sxs-lookup"><span data-stu-id="332f3-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="332f3-114">Il [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente intero, ossia senza resto.</span><span class="sxs-lookup"><span data-stu-id="332f3-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="332f3-115">Note</span><span class="sxs-lookup"><span data-stu-id="332f3-115">Remarks</span></span>  
 <span data-ttu-id="332f3-116">Il tipo di dati del risultato dipende dai tipi degli operandi.</span><span class="sxs-lookup"><span data-stu-id="332f3-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="332f3-117">Nella tabella seguente viene illustrato come il tipo di dati del risultato è determinato.</span><span class="sxs-lookup"><span data-stu-id="332f3-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="332f3-118">Tipi di dati degli operandi</span><span class="sxs-lookup"><span data-stu-id="332f3-118">Operand data types</span></span>|<span data-ttu-id="332f3-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="332f3-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="332f3-120">Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [breve](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [intero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lungo](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="332f3-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="332f3-121">Un'espressione è un [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) tipo di dati e l'altro non è un [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="332f3-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="332f3-122">Un'espressione è un [decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md) tipo di dati e l'altro non è un [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="332f3-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="332f3-123">Delle espressioni è un [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) tipo di dati</span><span class="sxs-lookup"><span data-stu-id="332f3-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="332f3-124">Prima di eseguita la divisione, le espressioni numeriche integrali vengono estesi a `Double`.</span><span class="sxs-lookup"><span data-stu-id="332f3-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="332f3-125">Se si assegna il risultato a un tipo di dati integrali, Visual Basic tenta di convertire il risultato da `Double` a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="332f3-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="332f3-126">Ciò può generare un'eccezione se il risultato non rientra in tale tipo.</span><span class="sxs-lookup"><span data-stu-id="332f3-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="332f3-127">In particolare, vedere "Ha tentato di divisione per Zero" in questa pagina della Guida in linea.</span><span class="sxs-lookup"><span data-stu-id="332f3-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="332f3-128">Se `expression1` o `expression2` restituisce [nulla](../../../visual-basic/language-reference/nothing.md), viene considerato pari a zero.</span><span class="sxs-lookup"><span data-stu-id="332f3-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="332f3-129">Tentativo di divisione per Zero</span><span class="sxs-lookup"><span data-stu-id="332f3-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="332f3-130">Se `expression2` restituisce zero, il `/` operatore si comporta in modo diverso per i tipi di dati diversi operando.</span><span class="sxs-lookup"><span data-stu-id="332f3-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="332f3-131">La tabella seguente illustra i possibili comportamenti.</span><span class="sxs-lookup"><span data-stu-id="332f3-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="332f3-132">Tipi di dati degli operandi</span><span class="sxs-lookup"><span data-stu-id="332f3-132">Operand data types</span></span>|<span data-ttu-id="332f3-133">Comportamento se `expression2` è zero</span><span class="sxs-lookup"><span data-stu-id="332f3-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="332f3-134">A virgola mobile (`Single` o `Double`)</span><span class="sxs-lookup"><span data-stu-id="332f3-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="332f3-135">Restituisce l'infinito (<xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>), o <xref:System.Double.NaN>(non un numero) se `expression1` è zero</xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity></span><span class="sxs-lookup"><span data-stu-id="332f3-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="332f3-136">Genera un'eccezione<xref:System.DivideByZeroException></xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="332f3-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="332f3-137">Integrale (con o senza segno)</span><span class="sxs-lookup"><span data-stu-id="332f3-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="332f3-138">Tentativo di conversione al tipo integrale genera <xref:System.OverflowException>perché non possono accettare tipi integrali <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, o <xref:System.Double.NaN></xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.OverflowException></span><span class="sxs-lookup"><span data-stu-id="332f3-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="332f3-139">Il `/` operatore può essere *overload*, il che significa che una classe o struttura possibile ridefinire il comportamento quando un operando specifica il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="332f3-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="332f3-140">Se il codice utilizza l'operatore su una classe o struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="332f3-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="332f3-141">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="332f3-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="332f3-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="332f3-142">Example</span></span>  
 <span data-ttu-id="332f3-143">Questo esempio viene utilizzato il `/` operatore per eseguire una divisione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="332f3-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="332f3-144">Il risultato è il quoziente di due operandi.</span><span class="sxs-lookup"><span data-stu-id="332f3-144">The result is the quotient of the two operands.</span></span>  
  
 <span data-ttu-id="332f3-145">[!code-vb[VbVbalrOperators&#16;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="332f3-145">[!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="332f3-146">Le espressioni nell'esempio precedente restituiscono valori di 2,5 e 3,333333.</span><span class="sxs-lookup"><span data-stu-id="332f3-146">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="332f3-147">Si noti che il risultato è sempre a virgola mobile (`Double`), anche se entrambi gli operandi sono costanti integer.</span><span class="sxs-lookup"><span data-stu-id="332f3-147">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="332f3-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="332f3-148">See Also</span></span>  
 <span data-ttu-id="332f3-149">[Operatore / = (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="332f3-149">[/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="332f3-150"> [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="332f3-150"> [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span></span>  
<span data-ttu-id="332f3-151"> [Tipi di dati dei risultati degli operatori](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span><span class="sxs-lookup"><span data-stu-id="332f3-151"> [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span></span>  
<span data-ttu-id="332f3-152"> [Aritmetici (operatori)](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="332f3-152"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="332f3-153"> [Precedenza tra operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="332f3-153"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="332f3-154"> [Elencata degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="332f3-154"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="332f3-155"> [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="332f3-155"> [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span></span>

