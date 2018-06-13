---
title: '&lt;&lt; Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: bdec015309526aeac2499bc7b459b6ccab6f1e4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604458"
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="ddfe2-102">&lt;&lt; Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddfe2-102">&lt;&lt; Operator (Visual Basic)</span></span>
<span data-ttu-id="ddfe2-103">Esegue uno spostamento a sinistra aritmetico in uno schema di bit.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddfe2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddfe2-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="ddfe2-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ddfe2-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="ddfe2-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-106">Required.</span></span> <span data-ttu-id="ddfe2-107">Valore numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-107">Integral numeric value.</span></span> <span data-ttu-id="ddfe2-108">Il risultato di spostamento dello schema di bit.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="ddfe2-109">Il tipo di dati è uguale a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="ddfe2-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-110">Required.</span></span> <span data-ttu-id="ddfe2-111">Espressione numerica integrale.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-111">Integral numeric expression.</span></span> <span data-ttu-id="ddfe2-112">Lo schema di bit da spostare.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="ddfe2-113">Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="ddfe2-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="ddfe2-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-114">Required.</span></span> <span data-ttu-id="ddfe2-115">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-115">Numeric expression.</span></span> <span data-ttu-id="ddfe2-116">Il numero di bit da spostare lo schema di bit.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="ddfe2-117">Il tipo di dati deve essere `Integer` o ampliarsi `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddfe2-118">Note</span><span class="sxs-lookup"><span data-stu-id="ddfe2-118">Remarks</span></span>  
 <span data-ttu-id="ddfe2-119">Aritmetici non sono circolare, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="ddfe2-120">In uno spostamento a sinistra aritmetico, vengono eliminati i bit spostati oltre l'intervallo del tipo di dati di risultati, e le posizioni dei bit liberate a destra vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="ddfe2-121">Per evitare lo spostamento di un bit più che il risultato può contenere, Visual Basic nasconde il valore di `amount` con una maschera di dimensioni che corrisponde al tipo di dati di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="ddfe2-122">L'operazione di AND binaria di questi valori viene utilizzato per l'entità dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="ddfe2-123">Di seguito sono riportate le maschere di dimensioni:</span><span class="sxs-lookup"><span data-stu-id="ddfe2-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="ddfe2-124">Tipo di dati `pattern`</span><span class="sxs-lookup"><span data-stu-id="ddfe2-124">Data type of `pattern`</span></span>|<span data-ttu-id="ddfe2-125">Maschera di dimensioni (decimale)</span><span class="sxs-lookup"><span data-stu-id="ddfe2-125">Size mask (decimal)</span></span>|<span data-ttu-id="ddfe2-126">Maschera di dimensioni (esadecimale)</span><span class="sxs-lookup"><span data-stu-id="ddfe2-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="ddfe2-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="ddfe2-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="ddfe2-128">7</span><span class="sxs-lookup"><span data-stu-id="ddfe2-128">7</span></span>|<span data-ttu-id="ddfe2-129">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="ddfe2-129">&H00000007</span></span>|  
|<span data-ttu-id="ddfe2-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="ddfe2-130">`Short`, `UShort`</span></span>|<span data-ttu-id="ddfe2-131">15</span><span class="sxs-lookup"><span data-stu-id="ddfe2-131">15</span></span>|<span data-ttu-id="ddfe2-132">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="ddfe2-132">&H0000000F</span></span>|  
|<span data-ttu-id="ddfe2-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="ddfe2-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="ddfe2-134">31</span><span class="sxs-lookup"><span data-stu-id="ddfe2-134">31</span></span>|<span data-ttu-id="ddfe2-135">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="ddfe2-135">&H0000001F</span></span>|  
|<span data-ttu-id="ddfe2-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="ddfe2-136">`Long`, `ULong`</span></span>|<span data-ttu-id="ddfe2-137">63</span><span class="sxs-lookup"><span data-stu-id="ddfe2-137">63</span></span>|<span data-ttu-id="ddfe2-138">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="ddfe2-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="ddfe2-139">Se `amount` è zero, il valore di `result` è identico al valore di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="ddfe2-140">Se `amount` è negativo, verrà considerato come un valore senza segno e nascosto con la maschera di dimensioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="ddfe2-141">Aritmetici non generano mai eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddfe2-142">Il `<<` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ddfe2-143">Se il codice utilizza l'operatore su una classe o una struttura, assicurarsi di aver compreso il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="ddfe2-144">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ddfe2-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddfe2-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddfe2-145">Example</span></span>  
 <span data-ttu-id="ddfe2-146">L'esempio seguente usa il `<<` operatore per eseguire operazioni aritmetiche sinistra su valori integrali.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="ddfe2-147">Il risultato dispone sempre gli stessi dati di tipo dell'espressione viene spostato.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 <span data-ttu-id="ddfe2-148">I risultati dell'esempio precedente sono come segue:</span><span class="sxs-lookup"><span data-stu-id="ddfe2-148">The results of the previous example are as follows:</span></span>  
  
-   <span data-ttu-id="ddfe2-149">`result1` è 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="ddfe2-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
-   <span data-ttu-id="ddfe2-150">`result2` è 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="ddfe2-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
-   <span data-ttu-id="ddfe2-151">`result3` è compreso tra -32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="ddfe2-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
-   <span data-ttu-id="ddfe2-152">`result4` è 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="ddfe2-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
-   <span data-ttu-id="ddfe2-153">`result5` è 0 (spostati 15 cifre a sinistra).</span><span class="sxs-lookup"><span data-stu-id="ddfe2-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="ddfe2-154">L'entità dello spostamento per `result4` viene calcolata come 17 e 15, pari a 1.</span><span class="sxs-lookup"><span data-stu-id="ddfe2-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddfe2-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddfe2-155">See Also</span></span>  
 [<span data-ttu-id="ddfe2-156">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="ddfe2-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="ddfe2-157">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="ddfe2-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="ddfe2-158">Operatore <<=</span><span class="sxs-lookup"><span data-stu-id="ddfe2-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [<span data-ttu-id="ddfe2-159">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddfe2-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ddfe2-160">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="ddfe2-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ddfe2-161">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddfe2-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
