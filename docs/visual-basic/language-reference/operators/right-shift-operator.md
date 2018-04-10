---
title: '&gt;&gt;Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4eb0ed817c95905a679de5026bf6494eb72df078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="5c4a7-102">&gt;&gt;Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c4a7-102">&gt;&gt; Operator (Visual Basic)</span></span>
<span data-ttu-id="5c4a7-103">Esegue uno spostamento verso destra aritmetico in uno schema di bit.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c4a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c4a7-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="5c4a7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5c4a7-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="5c4a7-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-106">Required.</span></span> <span data-ttu-id="5c4a7-107">Valore numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-107">Integral numeric value.</span></span> <span data-ttu-id="5c4a7-108">Il risultato di spostamento dello schema di bit.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="5c4a7-109">Il tipo di dati è uguale a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="5c4a7-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-110">Required.</span></span> <span data-ttu-id="5c4a7-111">Espressione numerica integrale.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-111">Integral numeric expression.</span></span> <span data-ttu-id="5c4a7-112">Lo schema di bit da spostare.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="5c4a7-113">Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="5c4a7-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-114">Required.</span></span> <span data-ttu-id="5c4a7-115">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-115">Numeric expression.</span></span> <span data-ttu-id="5c4a7-116">Il numero di bit da spostare lo schema di bit.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="5c4a7-117">Il tipo di dati deve essere `Integer` o ampliarsi `Integer`.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c4a7-118">Note</span><span class="sxs-lookup"><span data-stu-id="5c4a7-118">Remarks</span></span>  
 <span data-ttu-id="5c4a7-119">Aritmetici non sono circolare, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="5c4a7-120">In un aritmetico a destra, i bit spostati oltre la posizione del primo bit a destra vengono ignorati e il bit più a sinistra (accesso) verrà distribuito alle posizioni dei bit liberate a sinistra.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="5c4a7-121">Questo significa che se `pattern` ha un valore negativo, le posizioni liberate vengono impostate su uno; in caso contrario vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="5c4a7-122">Si noti che i tipi di dati `Byte`, `UShort`, `UInteger`, e `ULong` non sono firmati, pertanto non c'è alcun bit di segno per la propagazione.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="5c4a7-123">Se `pattern` di eventuali tipi senza segno, le posizioni liberate sono sempre impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="5c4a7-124">Per impedire lo spostamento di bit più che il risultato può contenere, Visual Basic nasconde il valore di `amount` con una maschera di dimensioni corrispondenti al tipo di dati di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="5c4a7-125">L'operazione di AND binaria di questi valori viene utilizzato per l'entità dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="5c4a7-126">Di seguito sono riportate le maschere di dimensioni:</span><span class="sxs-lookup"><span data-stu-id="5c4a7-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="5c4a7-127">Tipo di dati`pattern`</span><span class="sxs-lookup"><span data-stu-id="5c4a7-127">Data type of `pattern`</span></span>|<span data-ttu-id="5c4a7-128">Maschera di dimensioni (decimale)</span><span class="sxs-lookup"><span data-stu-id="5c4a7-128">Size mask (decimal)</span></span>|<span data-ttu-id="5c4a7-129">Maschera di dimensioni (esadecimale)</span><span class="sxs-lookup"><span data-stu-id="5c4a7-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="5c4a7-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="5c4a7-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="5c4a7-131">7</span><span class="sxs-lookup"><span data-stu-id="5c4a7-131">7</span></span>|<span data-ttu-id="5c4a7-132">& H00000007</span><span class="sxs-lookup"><span data-stu-id="5c4a7-132">&H00000007</span></span>|  
|<span data-ttu-id="5c4a7-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="5c4a7-133">`Short`, `UShort`</span></span>|<span data-ttu-id="5c4a7-134">15</span><span class="sxs-lookup"><span data-stu-id="5c4a7-134">15</span></span>|<span data-ttu-id="5c4a7-135">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="5c4a7-135">&H0000000F</span></span>|  
|<span data-ttu-id="5c4a7-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="5c4a7-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="5c4a7-137">31</span><span class="sxs-lookup"><span data-stu-id="5c4a7-137">31</span></span>|<span data-ttu-id="5c4a7-138">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="5c4a7-138">&H0000001F</span></span>|  
|<span data-ttu-id="5c4a7-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="5c4a7-139">`Long`, `ULong`</span></span>|<span data-ttu-id="5c4a7-140">63</span><span class="sxs-lookup"><span data-stu-id="5c4a7-140">63</span></span>|<span data-ttu-id="5c4a7-141">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="5c4a7-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="5c4a7-142">Se `amount` è zero, il valore di `result` è identico al valore di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="5c4a7-143">Se `amount` è negativo, verrà considerato come un valore senza segno e nascosto con la maschera di dimensioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="5c4a7-144">Aritmetici non generano mai eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5c4a7-145">Overload</span><span class="sxs-lookup"><span data-stu-id="5c4a7-145">Overloading</span></span>  
 <span data-ttu-id="5c4a7-146">Il `>>` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5c4a7-147">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5c4a7-148">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c4a7-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c4a7-149">Example</span></span>  
 <span data-ttu-id="5c4a7-150">L'esempio seguente usa il `>>` operatore per eseguire spostamenti a destra aritmetici in valori integrali.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="5c4a7-151">Il risultato dispone sempre gli stessi dati di tipo dell'espressione viene spostato.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 <span data-ttu-id="5c4a7-152">I risultati dell'esempio precedente sono come segue:</span><span class="sxs-lookup"><span data-stu-id="5c4a7-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="5c4a7-153">`result1`è 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="5c4a7-154">`result2`è di 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="5c4a7-155">`result3`è 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="5c4a7-156">`result4`è 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="5c4a7-157">`result5`è 0 (spostate 15 cifre a destra).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="5c4a7-158">L'entità dello spostamento per `result4` viene calcolata come 18 e 15, pari a 2.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="5c4a7-159">Nell'esempio seguente viene aritmetici su un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="5c4a7-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 <span data-ttu-id="5c4a7-160">I risultati dell'esempio precedente sono come segue:</span><span class="sxs-lookup"><span data-stu-id="5c4a7-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="5c4a7-161">`negresult1`è -512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="5c4a7-162">`negresult2`è -1 (il bit di segno è stato propagato).</span><span class="sxs-lookup"><span data-stu-id="5c4a7-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c4a7-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c4a7-163">See Also</span></span>  
 [<span data-ttu-id="5c4a7-164">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="5c4a7-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="5c4a7-165">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="5c4a7-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="5c4a7-166">Operatore >>=</span><span class="sxs-lookup"><span data-stu-id="5c4a7-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [<span data-ttu-id="5c4a7-167">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c4a7-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5c4a7-168">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="5c4a7-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5c4a7-169">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c4a7-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
