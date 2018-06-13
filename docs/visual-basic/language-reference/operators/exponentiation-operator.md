---
title: Operatore ^ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 426c3e9913dadda1091f4ba53c66c6b65e40e768
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604445"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="db612-102">Operatore ^ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db612-102">^ Operator (Visual Basic)</span></span>
<span data-ttu-id="db612-103">Eleva un numero alla potenza di un altro numero.</span><span class="sxs-lookup"><span data-stu-id="db612-103">Raises a number to the power of another number.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db612-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db612-104">Syntax</span></span>  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a><span data-ttu-id="db612-105">Parti</span><span class="sxs-lookup"><span data-stu-id="db612-105">Parts</span></span>  
 `number`  
 <span data-ttu-id="db612-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="db612-106">Required.</span></span> <span data-ttu-id="db612-107">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="db612-107">Any numeric expression.</span></span>  
  
 `exponent`  
 <span data-ttu-id="db612-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="db612-108">Required.</span></span> <span data-ttu-id="db612-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="db612-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="db612-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="db612-110">Result</span></span>  
 <span data-ttu-id="db612-111">Il risultato è `number` elevato alla potenza di `exponent`, sempre come un `Double` valore.</span><span class="sxs-lookup"><span data-stu-id="db612-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="db612-112">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="db612-112">Supported Types</span></span>  
 <span data-ttu-id="db612-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="db612-113">`Double`.</span></span> <span data-ttu-id="db612-114">Gli operandi di tipo diverso vengono convertiti in `Double`.</span><span class="sxs-lookup"><span data-stu-id="db612-114">Operands of any different type are converted to `Double`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db612-115">Note</span><span class="sxs-lookup"><span data-stu-id="db612-115">Remarks</span></span>  
 <span data-ttu-id="db612-116">Visual Basic esegue sempre elevamento a potenza nel [tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="db612-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>  
  
 <span data-ttu-id="db612-117">Il valore di `exponent` può essere frazionario, negativo o entrambi.</span><span class="sxs-lookup"><span data-stu-id="db612-117">The value of `exponent` can be fractional, negative, or both.</span></span>  
  
 <span data-ttu-id="db612-118">Quando più elevamento a potenza viene eseguito in un'unica espressione, il `^` operatore viene valutato come viene rilevata da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="db612-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db612-119">Il `^` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="db612-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="db612-120">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="db612-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="db612-121">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="db612-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db612-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="db612-122">Example</span></span>  
 <span data-ttu-id="db612-123">L'esempio seguente usa il `^` operatore per generare un numero alla potenza di un esponente.</span><span class="sxs-lookup"><span data-stu-id="db612-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="db612-124">Il risultato è il primo operando elevato alla potenza del secondo.</span><span class="sxs-lookup"><span data-stu-id="db612-124">The result is the first operand raised to the power of the second.</span></span>  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 <span data-ttu-id="db612-125">Nell'esempio precedente produce i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="db612-125">The preceding example produces the following results:</span></span>  
  
 <span data-ttu-id="db612-126">`exp1` è impostato su 4 (2 al quadrato).</span><span class="sxs-lookup"><span data-stu-id="db612-126">`exp1` is set to 4 (2 squared).</span></span>  
  
 <span data-ttu-id="db612-127">`exp2` è impostato su 19683 (3 al cubo, quindi tale valore al cubo).</span><span class="sxs-lookup"><span data-stu-id="db612-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>  
  
 <span data-ttu-id="db612-128">`exp3` è impostato su -125 (-5 al cubo).</span><span class="sxs-lookup"><span data-stu-id="db612-128">`exp3` is set to -125 (-5 cubed).</span></span>  
  
 <span data-ttu-id="db612-129">`exp4` è impostato su 625 (-5 alla quarta potenza).</span><span class="sxs-lookup"><span data-stu-id="db612-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>  
  
 <span data-ttu-id="db612-130">`exp5` è impostato su 2 (radice cubica di 8).</span><span class="sxs-lookup"><span data-stu-id="db612-130">`exp5` is set to 2 (cube root of 8).</span></span>  
  
 <span data-ttu-id="db612-131">`exp6` è impostata su 0,5 (1.0 diviso la radice cubica di 8).</span><span class="sxs-lookup"><span data-stu-id="db612-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>  
  
 <span data-ttu-id="db612-132">Si noti l'importanza delle parentesi nelle espressioni nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="db612-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="db612-133">Causa del *precedenza degli operatori*, Visual Basic esegue in genere il `^` operatore prima degli altri, anche l'operatore unario `–` operatore.</span><span class="sxs-lookup"><span data-stu-id="db612-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="db612-134">Se `exp4` e `exp6` è stata calcolata senza parentesi, prodotti sarebbero stati i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="db612-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>  
  
 <span data-ttu-id="db612-135">`exp4 = -5 ^ 4` viene calcolato come: (5 alla quarta potenza), che comporterebbe-625.</span><span class="sxs-lookup"><span data-stu-id="db612-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>  
  
 <span data-ttu-id="db612-136">`exp6 = 8 ^ -1.0 / 3.0` viene calcolato come (8 per la potenza di-1 o 0,125) diviso per 3.0, risultato uguale a 0,041666666666666666666666666666667.</span><span class="sxs-lookup"><span data-stu-id="db612-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db612-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db612-137">See Also</span></span>  
 [<span data-ttu-id="db612-138">Operatore ^=</span><span class="sxs-lookup"><span data-stu-id="db612-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="db612-139">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="db612-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="db612-140">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db612-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="db612-141">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="db612-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="db612-142">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db612-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
