---
title: << Operatore (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 75c16c27dc919ba365cbe3c28c61a1e46496b0ae
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824286"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b484c-102">\<\< Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b484c-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="b484c-103">Esegue uno spostamento a sinistra aritmetico in uno schema di bit.</span><span class="sxs-lookup"><span data-stu-id="b484c-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b484c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b484c-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="b484c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b484c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b484c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b484c-106">Required.</span></span> <span data-ttu-id="b484c-107">Valore numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="b484c-107">Integral numeric value.</span></span> <span data-ttu-id="b484c-108">Il risultato dello spostamento dello schema di bit.</span><span class="sxs-lookup"><span data-stu-id="b484c-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="b484c-109">Il tipo di dati è uguale a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="b484c-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="b484c-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b484c-110">Required.</span></span> <span data-ttu-id="b484c-111">Espressione numerica integrale.</span><span class="sxs-lookup"><span data-stu-id="b484c-111">Integral numeric expression.</span></span> <span data-ttu-id="b484c-112">Lo schema di bit da spostare.</span><span class="sxs-lookup"><span data-stu-id="b484c-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="b484c-113">Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="b484c-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="b484c-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b484c-114">Required.</span></span> <span data-ttu-id="b484c-115">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="b484c-115">Numeric expression.</span></span> <span data-ttu-id="b484c-116">Il numero di bit da spostare lo schema di bit.</span><span class="sxs-lookup"><span data-stu-id="b484c-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="b484c-117">Il tipo di dati deve essere `Integer` o ampliato a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b484c-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b484c-118">Note</span><span class="sxs-lookup"><span data-stu-id="b484c-118">Remarks</span></span>  
 <span data-ttu-id="b484c-119">Aritmetici non sono circolari, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità.</span><span class="sxs-lookup"><span data-stu-id="b484c-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="b484c-120">In uno spostamento a sinistra aritmetico, i bit spostati oltre l'intervallo del tipo di dati di risultati vengono ignorati e le posizioni dei bit liberate a destra vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="b484c-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="b484c-121">Per evitare uno spostamento più bit quello che può contenere il risultato, Visual Basic nasconde il valore di `amount` con una maschera di dimensione che corrisponde al tipo di dati di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="b484c-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="b484c-122">L'operatore AND binaria di questi valori viene utilizzato per l'entità dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="b484c-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="b484c-123">Le maschere di dimensioni sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="b484c-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="b484c-124">Tipo di dati `pattern`</span><span class="sxs-lookup"><span data-stu-id="b484c-124">Data type of `pattern`</span></span>|<span data-ttu-id="b484c-125">Maschera di dimensioni (decimale)</span><span class="sxs-lookup"><span data-stu-id="b484c-125">Size mask (decimal)</span></span>|<span data-ttu-id="b484c-126">Maschera di dimensioni (esadecimale)</span><span class="sxs-lookup"><span data-stu-id="b484c-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="b484c-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="b484c-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="b484c-128">7</span><span class="sxs-lookup"><span data-stu-id="b484c-128">7</span></span>|<span data-ttu-id="b484c-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="b484c-129">&H00000007</span></span>|  
|<span data-ttu-id="b484c-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="b484c-130">`Short`, `UShort`</span></span>|<span data-ttu-id="b484c-131">15</span><span class="sxs-lookup"><span data-stu-id="b484c-131">15</span></span>|<span data-ttu-id="b484c-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="b484c-132">&H0000000F</span></span>|  
|<span data-ttu-id="b484c-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="b484c-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="b484c-134">31</span><span class="sxs-lookup"><span data-stu-id="b484c-134">31</span></span>|<span data-ttu-id="b484c-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="b484c-135">&H0000001F</span></span>|  
|<span data-ttu-id="b484c-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="b484c-136">`Long`, `ULong`</span></span>|<span data-ttu-id="b484c-137">63</span><span class="sxs-lookup"><span data-stu-id="b484c-137">63</span></span>|<span data-ttu-id="b484c-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="b484c-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="b484c-139">Se `amount` è zero, il valore di `result` è identico a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="b484c-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="b484c-140">Se `amount` è negativo, viene considerato come un valore senza segno e nascosto con la maschera delle dimensioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="b484c-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="b484c-141">Aritmetici non generano mai le eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="b484c-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b484c-142">Il `<<` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="b484c-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b484c-143">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di aver compreso il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="b484c-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="b484c-144">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b484c-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b484c-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="b484c-145">Example</span></span>  
 <span data-ttu-id="b484c-146">L'esempio seguente usa il `<<` operatore per eseguire operazioni aritmetiche sinistra su valori integrali.</span><span class="sxs-lookup"><span data-stu-id="b484c-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="b484c-147">Il risultato ha sempre gli stessi dati di tipo come quello dell'espressione viene spostato.</span><span class="sxs-lookup"><span data-stu-id="b484c-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="b484c-148">I risultati dell'esempio precedente sono come segue:</span><span class="sxs-lookup"><span data-stu-id="b484c-148">The results of the previous example are as follows:</span></span>  
  
-   <span data-ttu-id="b484c-149">`result1` is 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="b484c-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
-   <span data-ttu-id="b484c-150">`result2` is 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="b484c-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
-   <span data-ttu-id="b484c-151">`result3` is -32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="b484c-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
-   <span data-ttu-id="b484c-152">`result4` is 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="b484c-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
-   <span data-ttu-id="b484c-153">`result5` è uguale a 0 (spostate 15 cifre a sinistra).</span><span class="sxs-lookup"><span data-stu-id="b484c-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="b484c-154">L'entità dello spostamento per `result4` è pari a 17 e 15, quali uguale a 1.</span><span class="sxs-lookup"><span data-stu-id="b484c-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b484c-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b484c-155">See also</span></span>

- [<span data-ttu-id="b484c-156">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="b484c-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="b484c-157">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="b484c-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="b484c-158">Operatore <<=</span><span class="sxs-lookup"><span data-stu-id="b484c-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="b484c-159">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b484c-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b484c-160">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="b484c-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b484c-161">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b484c-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
