---
title: '&gt;&gt; Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: e1d2b6569e2bcb3c1516dbc8c78adca0855481e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668496"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="1db21-102">&gt;&gt; Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db21-102">&gt;&gt; Operator (Visual Basic)</span></span>
<span data-ttu-id="1db21-103">Esegue uno scorrimento a destra aritmetico in uno schema di bit.</span><span class="sxs-lookup"><span data-stu-id="1db21-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1db21-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1db21-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="1db21-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1db21-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="1db21-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1db21-106">Required.</span></span> <span data-ttu-id="1db21-107">Valore numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="1db21-107">Integral numeric value.</span></span> <span data-ttu-id="1db21-108">Il risultato dello spostamento dello schema di bit.</span><span class="sxs-lookup"><span data-stu-id="1db21-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="1db21-109">Il tipo di dati è uguale a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="1db21-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="1db21-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1db21-110">Required.</span></span> <span data-ttu-id="1db21-111">Espressione numerica integrale.</span><span class="sxs-lookup"><span data-stu-id="1db21-111">Integral numeric expression.</span></span> <span data-ttu-id="1db21-112">Lo schema di bit da spostare.</span><span class="sxs-lookup"><span data-stu-id="1db21-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="1db21-113">Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="1db21-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="1db21-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1db21-114">Required.</span></span> <span data-ttu-id="1db21-115">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="1db21-115">Numeric expression.</span></span> <span data-ttu-id="1db21-116">Il numero di bit da spostare lo schema di bit.</span><span class="sxs-lookup"><span data-stu-id="1db21-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="1db21-117">Il tipo di dati deve essere `Integer` o ampliato a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="1db21-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1db21-118">Note</span><span class="sxs-lookup"><span data-stu-id="1db21-118">Remarks</span></span>  
 <span data-ttu-id="1db21-119">Aritmetici non sono circolari, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità.</span><span class="sxs-lookup"><span data-stu-id="1db21-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="1db21-120">In uno scorrimento aritmetico a destra, i bit spostati oltre la posizione del bit più a destra vengono ignorati e il bit più a sinistra (accesso) viene propagato nelle posizioni dei bit liberate a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1db21-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="1db21-121">Questo significa che se `pattern` ha un valore negativo, le posizioni vuote sono impostate su uno; in caso contrario, essi vengono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="1db21-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="1db21-122">Si noti che i tipi di dati `Byte`, `UShort`, `UInteger`, e `ULong` non sono firmati, pertanto non presenta alcun bit di segno per la propagazione.</span><span class="sxs-lookup"><span data-stu-id="1db21-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="1db21-123">Se `pattern` è di qualsiasi tipi senza segno, le posizioni vuote sono sempre impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="1db21-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="1db21-124">Per impedire lo spostamento da più bit quello che può contenere il risultato, Visual Basic nasconde il valore di `amount` con una maschera di dimensione corrispondente al tipo di dati di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="1db21-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="1db21-125">L'operatore AND binaria di questi valori viene utilizzato per l'entità dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="1db21-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="1db21-126">Le maschere di dimensioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1db21-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="1db21-127">Tipo di dati `pattern`</span><span class="sxs-lookup"><span data-stu-id="1db21-127">Data type of `pattern`</span></span>|<span data-ttu-id="1db21-128">Maschera di dimensioni (decimale)</span><span class="sxs-lookup"><span data-stu-id="1db21-128">Size mask (decimal)</span></span>|<span data-ttu-id="1db21-129">Maschera di dimensioni (esadecimale)</span><span class="sxs-lookup"><span data-stu-id="1db21-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="1db21-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="1db21-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="1db21-131">7</span><span class="sxs-lookup"><span data-stu-id="1db21-131">7</span></span>|<span data-ttu-id="1db21-132">&H00000007</span><span class="sxs-lookup"><span data-stu-id="1db21-132">&H00000007</span></span>|  
|<span data-ttu-id="1db21-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="1db21-133">`Short`, `UShort`</span></span>|<span data-ttu-id="1db21-134">15</span><span class="sxs-lookup"><span data-stu-id="1db21-134">15</span></span>|<span data-ttu-id="1db21-135">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="1db21-135">&H0000000F</span></span>|  
|<span data-ttu-id="1db21-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="1db21-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="1db21-137">31</span><span class="sxs-lookup"><span data-stu-id="1db21-137">31</span></span>|<span data-ttu-id="1db21-138">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="1db21-138">&H0000001F</span></span>|  
|<span data-ttu-id="1db21-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="1db21-139">`Long`, `ULong`</span></span>|<span data-ttu-id="1db21-140">63</span><span class="sxs-lookup"><span data-stu-id="1db21-140">63</span></span>|<span data-ttu-id="1db21-141">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="1db21-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="1db21-142">Se `amount` è zero, il valore di `result` è identico a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="1db21-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="1db21-143">Se `amount` è negativo, viene considerato come un valore senza segno e nascosto con la maschera delle dimensioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="1db21-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="1db21-144">Aritmetici non generano mai le eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="1db21-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1db21-145">Overload</span><span class="sxs-lookup"><span data-stu-id="1db21-145">Overloading</span></span>  
 <span data-ttu-id="1db21-146">Il `>>` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="1db21-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1db21-147">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="1db21-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1db21-148">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1db21-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1db21-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="1db21-149">Example</span></span>  
 <span data-ttu-id="1db21-150">L'esempio seguente usa il `>>` operatore eseguire spostamenti a destra aritmetici in valori integrali.</span><span class="sxs-lookup"><span data-stu-id="1db21-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="1db21-151">Il risultato ha sempre gli stessi dati di tipo come quello dell'espressione viene spostato.</span><span class="sxs-lookup"><span data-stu-id="1db21-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 <span data-ttu-id="1db21-152">I risultati dell'esempio precedente sono come segue:</span><span class="sxs-lookup"><span data-stu-id="1db21-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="1db21-153">`result1` is 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="1db21-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="1db21-154">`result2` is 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="1db21-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="1db21-155">`result3` is 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="1db21-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="1db21-156">`result4` is 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="1db21-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="1db21-157">`result5` è uguale a 0 (spostate 15 cifre a destra).</span><span class="sxs-lookup"><span data-stu-id="1db21-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="1db21-158">L'entità dello spostamento per `result4` è pari a 18 e 15, quali uguale a 2.</span><span class="sxs-lookup"><span data-stu-id="1db21-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="1db21-159">Nell'esempio seguente mostra aritmetici su un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="1db21-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 <span data-ttu-id="1db21-160">I risultati dell'esempio precedente sono come segue:</span><span class="sxs-lookup"><span data-stu-id="1db21-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="1db21-161">`negresult1` is -512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="1db21-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="1db21-162">`negresult2` è -1 (il bit di segno viene propagato).</span><span class="sxs-lookup"><span data-stu-id="1db21-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db21-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1db21-163">See also</span></span>
- [<span data-ttu-id="1db21-164">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="1db21-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="1db21-165">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="1db21-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="1db21-166">Operatore >>=</span><span class="sxs-lookup"><span data-stu-id="1db21-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="1db21-167">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1db21-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1db21-168">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="1db21-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1db21-169">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1db21-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
