---
title: '>> Operatore (Visual Basic)'
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
ms.openlocfilehash: 337d651e831dc2ab132056f6e9a1f2b5300bf7f8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701321"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="19ac2-102">Operatore > > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19ac2-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="19ac2-103">Esegue uno spostamento a destra aritmetico in uno schema di bit.</span><span class="sxs-lookup"><span data-stu-id="19ac2-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ac2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19ac2-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="19ac2-105">Parti</span><span class="sxs-lookup"><span data-stu-id="19ac2-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="19ac2-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="19ac2-106">Required.</span></span> <span data-ttu-id="19ac2-107">Valore numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="19ac2-107">Integral numeric value.</span></span> <span data-ttu-id="19ac2-108">Risultato dello spostamento dello schema di bit.</span><span class="sxs-lookup"><span data-stu-id="19ac2-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="19ac2-109">Il tipo di dati è uguale a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="19ac2-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="19ac2-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="19ac2-110">Required.</span></span> <span data-ttu-id="19ac2-111">Espressione numerica integrale.</span><span class="sxs-lookup"><span data-stu-id="19ac2-111">Integral numeric expression.</span></span> <span data-ttu-id="19ac2-112">Modello di bit da spostare.</span><span class="sxs-lookup"><span data-stu-id="19ac2-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="19ac2-113">Il tipo di dati deve essere un tipo integrale`SByte`( `Byte` `Short`,, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="19ac2-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="19ac2-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="19ac2-114">Required.</span></span> <span data-ttu-id="19ac2-115">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="19ac2-115">Numeric expression.</span></span> <span data-ttu-id="19ac2-116">Numero di bit per spostare lo schema di bit.</span><span class="sxs-lookup"><span data-stu-id="19ac2-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="19ac2-117">Il tipo di dati deve `Integer` essere o ampliato a. `Integer`</span><span class="sxs-lookup"><span data-stu-id="19ac2-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19ac2-118">Note</span><span class="sxs-lookup"><span data-stu-id="19ac2-118">Remarks</span></span>  
 <span data-ttu-id="19ac2-119">I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="19ac2-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="19ac2-120">In uno spostamento a destra aritmetico i bit spostati oltre la posizione del bit più a destra vengono eliminati e il bit più a sinistra (segno) viene propagato nelle posizioni dei bit sgomberate a sinistra.</span><span class="sxs-lookup"><span data-stu-id="19ac2-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="19ac2-121">Ciò significa che se `pattern` ha un valore negativo, le posizioni sgomberate sono impostate su uno. in caso contrario, vengono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="19ac2-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="19ac2-122">Si noti che i tipi di dati `Byte`, `UShort`, `UInteger` e `ULong` non sono firmati, pertanto non è presente alcun bit di segno da propagare.</span><span class="sxs-lookup"><span data-stu-id="19ac2-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="19ac2-123">Se `pattern` è di qualsiasi tipo senza segno, le posizioni sgomberate vengono sempre impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="19ac2-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="19ac2-124">Per impedire lo spostamento di più bit rispetto al risultato, Visual Basic maschera il valore di `amount` con una maschera di dimensioni corrispondente al tipo di dati di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="19ac2-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="19ac2-125">Il file binario e di questi valori viene utilizzato per l'importo dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="19ac2-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="19ac2-126">Le maschere delle dimensioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="19ac2-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="19ac2-127">Tipo di dati di `pattern`</span><span class="sxs-lookup"><span data-stu-id="19ac2-127">Data type of `pattern`</span></span>|<span data-ttu-id="19ac2-128">Maschera dimensioni (decimale)</span><span class="sxs-lookup"><span data-stu-id="19ac2-128">Size mask (decimal)</span></span>|<span data-ttu-id="19ac2-129">Maschera dimensioni (esadecimale)</span><span class="sxs-lookup"><span data-stu-id="19ac2-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="19ac2-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="19ac2-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="19ac2-131">7</span><span class="sxs-lookup"><span data-stu-id="19ac2-131">7</span></span>|<span data-ttu-id="19ac2-132">& H00000007</span><span class="sxs-lookup"><span data-stu-id="19ac2-132">&H00000007</span></span>|  
|<span data-ttu-id="19ac2-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="19ac2-133">`Short`, `UShort`</span></span>|<span data-ttu-id="19ac2-134">15</span><span class="sxs-lookup"><span data-stu-id="19ac2-134">15</span></span>|<span data-ttu-id="19ac2-135">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="19ac2-135">&H0000000F</span></span>|  
|<span data-ttu-id="19ac2-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="19ac2-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="19ac2-137">31</span><span class="sxs-lookup"><span data-stu-id="19ac2-137">31</span></span>|<span data-ttu-id="19ac2-138">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="19ac2-138">&H0000001F</span></span>|  
|<span data-ttu-id="19ac2-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="19ac2-139">`Long`, `ULong`</span></span>|<span data-ttu-id="19ac2-140">63</span><span class="sxs-lookup"><span data-stu-id="19ac2-140">63</span></span>|<span data-ttu-id="19ac2-141">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="19ac2-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="19ac2-142">Se `amount` è zero, il valore di `result` è identico al valore di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="19ac2-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="19ac2-143">Se `amount` è negativo, viene considerato come un valore senza segno e mascherato con la maschera di dimensioni appropriata.</span><span class="sxs-lookup"><span data-stu-id="19ac2-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="19ac2-144">I turni aritmetici non generano mai eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="19ac2-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="19ac2-145">Overload</span><span class="sxs-lookup"><span data-stu-id="19ac2-145">Overloading</span></span>  
 <span data-ttu-id="19ac2-146">L'operatore `>>` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="19ac2-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="19ac2-147">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="19ac2-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="19ac2-148">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="19ac2-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19ac2-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="19ac2-149">Example</span></span>  
 <span data-ttu-id="19ac2-150">Nell'esempio seguente viene usato l'operatore `>>` per eseguire turni aritmetici a destra sui valori integrali.</span><span class="sxs-lookup"><span data-stu-id="19ac2-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="19ac2-151">Il risultato ha sempre lo stesso tipo di dati dell'espressione spostata.</span><span class="sxs-lookup"><span data-stu-id="19ac2-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="19ac2-152">I risultati dell'esempio precedente sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="19ac2-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="19ac2-153">`result1` è 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="19ac2-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="19ac2-154">`result2` is 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="19ac2-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="19ac2-155">`result3` è 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="19ac2-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="19ac2-156">`result4` is 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="19ac2-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="19ac2-157">`result5` è 0 (spostato di 15 posizioni a destra).</span><span class="sxs-lookup"><span data-stu-id="19ac2-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="19ac2-158">Il valore Shift per `result4` viene calcolato come 18 e 15, che è uguale a 2.</span><span class="sxs-lookup"><span data-stu-id="19ac2-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="19ac2-159">Nell'esempio seguente vengono illustrati i turni aritmetici su un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="19ac2-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="19ac2-160">I risultati dell'esempio precedente sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="19ac2-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="19ac2-161">`negresult1` è-512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="19ac2-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="19ac2-162">`negresult2` è-1 (il bit di segno viene propagato).</span><span class="sxs-lookup"><span data-stu-id="19ac2-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ac2-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19ac2-163">See also</span></span>

- [<span data-ttu-id="19ac2-164">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="19ac2-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="19ac2-165">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="19ac2-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="19ac2-166">Operatore >>=</span><span class="sxs-lookup"><span data-stu-id="19ac2-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="19ac2-167">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19ac2-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="19ac2-168">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="19ac2-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="19ac2-169">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19ac2-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
