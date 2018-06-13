---
title: Operatore \ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: ef3946e871e1dc248b54932e16f6cae6026da08e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604237"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9725d-102">Operatore \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9725d-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="9725d-103">Divide due numeri e restituisce un risultato intero.</span><span class="sxs-lookup"><span data-stu-id="9725d-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9725d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9725d-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9725d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9725d-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="9725d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9725d-106">Required.</span></span> <span data-ttu-id="9725d-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="9725d-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="9725d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9725d-108">Required.</span></span> <span data-ttu-id="9725d-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="9725d-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="9725d-110">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="9725d-110">Supported Types</span></span>  
 <span data-ttu-id="9725d-111">Tutti i tipi numerici, inclusi i tipi senza segno a virgola mobile e `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="9725d-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="9725d-112">Risultato</span><span class="sxs-lookup"><span data-stu-id="9725d-112">Result</span></span>  
 <span data-ttu-id="9725d-113">Il risultato è il quoziente di `expression1` diviso `expression2`, che le parti restanti e viene mantenuta solo la parte intera.</span><span class="sxs-lookup"><span data-stu-id="9725d-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="9725d-114">Questo è noto come *troncamento*.</span><span class="sxs-lookup"><span data-stu-id="9725d-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="9725d-115">Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="9725d-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="9725d-116">Vedere le tabelle "Calcoli di interi" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="9725d-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="9725d-117">Il [/ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) restituisce il quoziente completo, incluso il resto nella parte frazionaria.</span><span class="sxs-lookup"><span data-stu-id="9725d-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9725d-118">Note</span><span class="sxs-lookup"><span data-stu-id="9725d-118">Remarks</span></span>  
 <span data-ttu-id="9725d-119">Prima di eseguire la divisione, Visual Basic tenta di convertire qualsiasi espressione numerica a virgola mobile a `Long`.</span><span class="sxs-lookup"><span data-stu-id="9725d-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="9725d-120">Se `Option Strict` è `On`, si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="9725d-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="9725d-121">Se `Option Strict` è `Off`, un <xref:System.OverflowException> è possibile se il valore è compreso nell'intervallo del [tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="9725d-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="9725d-122">La conversione a `Long` è anche soggetto a *arrotondamento*.</span><span class="sxs-lookup"><span data-stu-id="9725d-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="9725d-123">Per ulteriori informazioni, vedere "Parti frazionarie" in [funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="9725d-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="9725d-124">Se `expression1` o `expression2` restituisce [nulla](../../../visual-basic/language-reference/nothing.md), viene considerato pari a zero.</span><span class="sxs-lookup"><span data-stu-id="9725d-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="9725d-125">Tentativo di divisione per Zero</span><span class="sxs-lookup"><span data-stu-id="9725d-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="9725d-126">Se `expression2` restituisce zero, il `\` operatore genera un <xref:System.DivideByZeroException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="9725d-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="9725d-127">Questo vale per tutti i tipi di dati numerici degli operandi.</span><span class="sxs-lookup"><span data-stu-id="9725d-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9725d-128">Il `\` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="9725d-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9725d-129">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="9725d-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9725d-130">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9725d-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9725d-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="9725d-131">Example</span></span>  
 <span data-ttu-id="9725d-132">L'esempio seguente usa il `\` operatore per eseguire la divisione di integer.</span><span class="sxs-lookup"><span data-stu-id="9725d-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="9725d-133">Il risultato è un numero intero che rappresenta il quoziente di due operandi, con il resto.</span><span class="sxs-lookup"><span data-stu-id="9725d-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 <span data-ttu-id="9725d-134">Nell'esempio precedente le espressioni restituiscono rispettivamente i valori 2, 3, 33 e -22.</span><span class="sxs-lookup"><span data-stu-id="9725d-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9725d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9725d-135">See Also</span></span>  
 [<span data-ttu-id="9725d-136">\\= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="9725d-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="9725d-137">/ Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9725d-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="9725d-138">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="9725d-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="9725d-139">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="9725d-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="9725d-140">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9725d-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="9725d-141">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="9725d-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="9725d-142">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9725d-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
