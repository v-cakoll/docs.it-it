---
title: Operatore <<
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 1128b32a739e7dbf3893dcd19b37247cd4643c85
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370635"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c1565-102">\<\<Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1565-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="c1565-103">Esegue uno scorrimento a sinistra aritmetico in uno schema di bit.</span><span class="sxs-lookup"><span data-stu-id="c1565-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1565-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1565-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="c1565-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c1565-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c1565-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c1565-106">Required.</span></span> <span data-ttu-id="c1565-107">Valore numerico integrale.</span><span class="sxs-lookup"><span data-stu-id="c1565-107">Integral numeric value.</span></span> <span data-ttu-id="c1565-108">Risultato dello spostamento dello schema di bit.</span><span class="sxs-lookup"><span data-stu-id="c1565-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="c1565-109">Il tipo di dati corrisponde a quello di `pattern`.</span><span class="sxs-lookup"><span data-stu-id="c1565-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="c1565-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c1565-110">Required.</span></span> <span data-ttu-id="c1565-111">Espressione numerica integrale.</span><span class="sxs-lookup"><span data-stu-id="c1565-111">Integral numeric expression.</span></span> <span data-ttu-id="c1565-112">Schema di bit da spostare.</span><span class="sxs-lookup"><span data-stu-id="c1565-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="c1565-113">Il tipo di dati deve essere integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="c1565-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="c1565-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c1565-114">Required.</span></span> <span data-ttu-id="c1565-115">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="c1565-115">Numeric expression.</span></span> <span data-ttu-id="c1565-116">Numero di bit per spostare lo schema di bit.</span><span class="sxs-lookup"><span data-stu-id="c1565-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="c1565-117">Il tipo di dati deve essere `Integer` o ampliato a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c1565-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1565-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="c1565-118">Remarks</span></span>  
 <span data-ttu-id="c1565-119">I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="c1565-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="c1565-120">In uno scorrimento a sinistra aritmetico, i bit spostati oltre l'intervallo del tipo di dati del risultato vengono rimossi e le posizioni dei bit sgomberate a destra vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="c1565-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="c1565-121">Per evitare uno spostamento di più bit rispetto al risultato, Visual Basic maschera il valore di `amount` con una maschera di dimensioni che corrisponde al tipo di dati di `pattern` .</span><span class="sxs-lookup"><span data-stu-id="c1565-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="c1565-122">Il file binario e di questi valori viene utilizzato per l'importo dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="c1565-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="c1565-123">Le maschere delle dimensioni sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1565-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="c1565-124">Tipo di dati di`pattern`</span><span class="sxs-lookup"><span data-stu-id="c1565-124">Data type of `pattern`</span></span>|<span data-ttu-id="c1565-125">Maschera dimensioni (decimale)</span><span class="sxs-lookup"><span data-stu-id="c1565-125">Size mask (decimal)</span></span>|<span data-ttu-id="c1565-126">Maschera dimensioni (esadecimale)</span><span class="sxs-lookup"><span data-stu-id="c1565-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="c1565-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="c1565-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="c1565-128">7</span><span class="sxs-lookup"><span data-stu-id="c1565-128">7</span></span>|<span data-ttu-id="c1565-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="c1565-129">&H00000007</span></span>|  
|<span data-ttu-id="c1565-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="c1565-130">`Short`, `UShort`</span></span>|<span data-ttu-id="c1565-131">15</span><span class="sxs-lookup"><span data-stu-id="c1565-131">15</span></span>|<span data-ttu-id="c1565-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="c1565-132">&H0000000F</span></span>|  
|<span data-ttu-id="c1565-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="c1565-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="c1565-134">31</span><span class="sxs-lookup"><span data-stu-id="c1565-134">31</span></span>|<span data-ttu-id="c1565-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="c1565-135">&H0000001F</span></span>|  
|<span data-ttu-id="c1565-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="c1565-136">`Long`, `ULong`</span></span>|<span data-ttu-id="c1565-137">63</span><span class="sxs-lookup"><span data-stu-id="c1565-137">63</span></span>|<span data-ttu-id="c1565-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="c1565-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="c1565-139">Se `amount` è zero, il valore di `result` è identico al valore di `pattern` .</span><span class="sxs-lookup"><span data-stu-id="c1565-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="c1565-140">Se `amount` è negativo, viene considerato come un valore senza segno e mascherato con la maschera di dimensioni appropriata.</span><span class="sxs-lookup"><span data-stu-id="c1565-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="c1565-141">I turni aritmetici non generano mai eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="c1565-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1565-142">L' `<<` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="c1565-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c1565-143">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="c1565-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="c1565-144">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c1565-144">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1565-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1565-145">Example</span></span>  
 <span data-ttu-id="c1565-146">Nell'esempio seguente viene utilizzato l' `<<` operatore per eseguire turni aritmetici a sinistra sui valori integrali.</span><span class="sxs-lookup"><span data-stu-id="c1565-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="c1565-147">Il risultato ha sempre lo stesso tipo di dati dell'espressione spostata.</span><span class="sxs-lookup"><span data-stu-id="c1565-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="c1565-148">I risultati dell'esempio precedente sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1565-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="c1565-149">`result1`è 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="c1565-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="c1565-150">`result2`è 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="c1565-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="c1565-151">`result3`is-32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="c1565-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="c1565-152">`result4`è 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="c1565-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="c1565-153">`result5`è 0 (spostato di 15 posizioni a sinistra).</span><span class="sxs-lookup"><span data-stu-id="c1565-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="c1565-154">Il valore Shift per `result4` viene calcolato come 17 e 15, che è uguale a 1.</span><span class="sxs-lookup"><span data-stu-id="c1565-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1565-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1565-155">See also</span></span>

- [<span data-ttu-id="c1565-156">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="c1565-156">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="c1565-157">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="c1565-157">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="c1565-158">Operatore<<=</span><span class="sxs-lookup"><span data-stu-id="c1565-158"><<= Operator</span></span>](left-shift-assignment-operator.md)
- [<span data-ttu-id="c1565-159">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1565-159">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c1565-160">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="c1565-160">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c1565-161">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1565-161">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
