---
title: Operatore /
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
ms.openlocfilehash: 537d8b0c703b59743f1a7c531448118058707645
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331046"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="df48f-102">Operatore / (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df48f-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="df48f-103">Divide due numeri e restituisce un risultato a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="df48f-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df48f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df48f-104">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="df48f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="df48f-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="df48f-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="df48f-106">Required.</span></span> <span data-ttu-id="df48f-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="df48f-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="df48f-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="df48f-108">Required.</span></span> <span data-ttu-id="df48f-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="df48f-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="df48f-110">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="df48f-110">Supported Types</span></span>  
 <span data-ttu-id="df48f-111">Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="df48f-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="df48f-112">Risultato</span><span class="sxs-lookup"><span data-stu-id="df48f-112">Result</span></span>  
 <span data-ttu-id="df48f-113">Il risultato è il quoziente completo di `expression1` diviso per `expression2`, incluso qualsiasi resto.</span><span class="sxs-lookup"><span data-stu-id="df48f-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="df48f-114">L' [operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente integer, che elimina il resto.</span><span class="sxs-lookup"><span data-stu-id="df48f-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df48f-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="df48f-115">Remarks</span></span>  
 <span data-ttu-id="df48f-116">Il tipo di dati del risultato dipende dai tipi degli operandi.</span><span class="sxs-lookup"><span data-stu-id="df48f-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="df48f-117">Nella tabella seguente viene illustrato il modo in cui viene determinato il tipo di dati del risultato.</span><span class="sxs-lookup"><span data-stu-id="df48f-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="df48f-118">Tipi di dati degli operandi</span><span class="sxs-lookup"><span data-stu-id="df48f-118">Operand data types</span></span>|<span data-ttu-id="df48f-119">Tipo di dati result</span><span class="sxs-lookup"><span data-stu-id="df48f-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="df48f-120">Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULONG](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="df48f-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="df48f-121">Un'espressione è un tipo di dati [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) e l'altra non è un [valore Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="df48f-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="df48f-122">Un'espressione è un tipo di dati [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) e l'altra non è una [singola](../../../visual-basic/language-reference/data-types/single-data-type.md) o una [doppia](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="df48f-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="df48f-123">Expression è un tipo di dati [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="df48f-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="df48f-124">Prima di eseguire la divisione, le espressioni numeriche integrali vengono ampliate `Double`.</span><span class="sxs-lookup"><span data-stu-id="df48f-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="df48f-125">Se il risultato viene assegnato a un tipo di dati integrale, Visual Basic tenta di convertire il risultato da `Double` a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="df48f-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="df48f-126">Questa operazione può generare un'eccezione se il risultato non rientra in tale tipo.</span><span class="sxs-lookup"><span data-stu-id="df48f-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="df48f-127">In particolare, vedere "tentativo di divisione per zero" in questa pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="df48f-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="df48f-128">Se `expression1` o `expression2` restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.</span><span class="sxs-lookup"><span data-stu-id="df48f-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="df48f-129">Tentativo di divisione per zero</span><span class="sxs-lookup"><span data-stu-id="df48f-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="df48f-130">Se `expression2` restituisce zero, l'operatore `/` si comporta in modo diverso per i diversi tipi di dati dell'operando.</span><span class="sxs-lookup"><span data-stu-id="df48f-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="df48f-131">La tabella seguente illustra i possibili comportamenti.</span><span class="sxs-lookup"><span data-stu-id="df48f-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="df48f-132">Tipi di dati degli operandi</span><span class="sxs-lookup"><span data-stu-id="df48f-132">Operand data types</span></span>|<span data-ttu-id="df48f-133">Comportamento se `expression2` è zero</span><span class="sxs-lookup"><span data-stu-id="df48f-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="df48f-134">A virgola mobile (`Single` o `Double`)</span><span class="sxs-lookup"><span data-stu-id="df48f-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="df48f-135">Restituisce Infinity (<xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>) oppure <xref:System.Double.NaN> (non un numero) se `expression1` è anche zero</span><span class="sxs-lookup"><span data-stu-id="df48f-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="df48f-136">Genera <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="df48f-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="df48f-137">Integrale (con segno o senza segno)</span><span class="sxs-lookup"><span data-stu-id="df48f-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="df48f-138">Il tentativo di conversione nel tipo integrale genera <xref:System.OverflowException> perché i tipi integrali non accettano <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>o <xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="df48f-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="df48f-139">L'operatore `/` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="df48f-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="df48f-140">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="df48f-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="df48f-141">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="df48f-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="df48f-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="df48f-142">Example</span></span>  
 <span data-ttu-id="df48f-143">Questo esempio usa l'operatore `/` per eseguire la divisione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="df48f-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="df48f-144">Il risultato è il quoziente dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="df48f-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="df48f-145">Le espressioni nell'esempio precedente restituiscono i valori 2,5 e 3,333333.</span><span class="sxs-lookup"><span data-stu-id="df48f-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="df48f-146">Si noti che il risultato è sempre a virgola mobile (`Double`), anche se entrambi gli operandi sono costanti integer.</span><span class="sxs-lookup"><span data-stu-id="df48f-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df48f-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df48f-147">See also</span></span>

- [<span data-ttu-id="df48f-148">Operatore/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df48f-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="df48f-149">Operatore \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df48f-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="df48f-150">Tipi di dati dei risultati degli operatori</span><span class="sxs-lookup"><span data-stu-id="df48f-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="df48f-151">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="df48f-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="df48f-152">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df48f-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="df48f-153">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="df48f-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="df48f-154">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df48f-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
