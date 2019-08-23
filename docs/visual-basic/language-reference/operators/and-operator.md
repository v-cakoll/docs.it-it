---
title: Operatore And (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913163"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="1a3a9-102">Operatore And (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a3a9-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="1a3a9-103">Esegue una congiunzione logica di `Boolean` due espressioni o una congiunzione bit per bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a3a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a3a9-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="1a3a9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1a3a9-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="1a3a9-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-106">Required.</span></span> <span data-ttu-id="1a3a9-107">Espressione `Boolean` qualsiasi o numerica.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="1a3a9-108">Per il confronto booleano, `result` è la congiunzione logica di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="1a3a9-109">Per le operazioni bit `result` per bit, è un valore numerico che rappresenta la combinazione bit per bit di due schemi di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="1a3a9-110">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-110">Required.</span></span> <span data-ttu-id="1a3a9-111">Espressione `Boolean` qualsiasi o numerica.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="1a3a9-112">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-112">Required.</span></span> <span data-ttu-id="1a3a9-113">Espressione `Boolean` qualsiasi o numerica.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a3a9-114">Note</span><span class="sxs-lookup"><span data-stu-id="1a3a9-114">Remarks</span></span>  
 <span data-ttu-id="1a3a9-115">Per il confronto booleano `True` , `result` è `expression1` se e solo `True`se `expression2` e restituiscono.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="1a3a9-116">Nella tabella seguente viene illustrato come `result` determinare.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="1a3a9-117">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="1a3a9-117">If `expression1` is</span></span>|<span data-ttu-id="1a3a9-118">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="1a3a9-118">And `expression2` is</span></span>|<span data-ttu-id="1a3a9-119">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="1a3a9-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="1a3a9-120">In un confronto booleano, `And` l'operatore valuta sempre entrambe le espressioni, che possono includere l'esecuzione di chiamate di routine.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="1a3a9-121">L' [operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `False`, `expression2` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="1a3a9-122">Quando viene applicato a valori numerici `And` , l'operatore esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni `result` numeriche e imposta il bit corrispondente in in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="1a3a9-123">Se il bit `expression1` in è</span><span class="sxs-lookup"><span data-stu-id="1a3a9-123">If bit in `expression1` is</span></span>|<span data-ttu-id="1a3a9-124">E bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="1a3a9-124">And bit in `expression2` is</span></span>|<span data-ttu-id="1a3a9-125">Il bit in `result` è</span><span class="sxs-lookup"><span data-stu-id="1a3a9-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="1a3a9-126">1</span><span class="sxs-lookup"><span data-stu-id="1a3a9-126">1</span></span>|<span data-ttu-id="1a3a9-127">1</span><span class="sxs-lookup"><span data-stu-id="1a3a9-127">1</span></span>|<span data-ttu-id="1a3a9-128">1</span><span class="sxs-lookup"><span data-stu-id="1a3a9-128">1</span></span>|  
|<span data-ttu-id="1a3a9-129">1</span><span class="sxs-lookup"><span data-stu-id="1a3a9-129">1</span></span>|<span data-ttu-id="1a3a9-130">0</span><span class="sxs-lookup"><span data-stu-id="1a3a9-130">0</span></span>|<span data-ttu-id="1a3a9-131">0</span><span class="sxs-lookup"><span data-stu-id="1a3a9-131">0</span></span>|  
|<span data-ttu-id="1a3a9-132">0</span><span class="sxs-lookup"><span data-stu-id="1a3a9-132">0</span></span>|<span data-ttu-id="1a3a9-133">1</span><span class="sxs-lookup"><span data-stu-id="1a3a9-133">1</span></span>|<span data-ttu-id="1a3a9-134">0</span><span class="sxs-lookup"><span data-stu-id="1a3a9-134">0</span></span>|  
|<span data-ttu-id="1a3a9-135">0</span><span class="sxs-lookup"><span data-stu-id="1a3a9-135">0</span></span>|<span data-ttu-id="1a3a9-136">0</span><span class="sxs-lookup"><span data-stu-id="1a3a9-136">0</span></span>|<span data-ttu-id="1a3a9-137">0</span><span class="sxs-lookup"><span data-stu-id="1a3a9-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="1a3a9-138">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire risultati accurati.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="1a3a9-139">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1a3a9-139">Data Types</span></span>  
 <span data-ttu-id="1a3a9-140">Se gli operandi sono costituiti da `Boolean` un'espressione e da un'espressione numerica, `Boolean` Visual Basic converte l'espressione in un valore numerico ( `True` -1 per `False`e 0 per) ed esegue un'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="1a3a9-141">Per un confronto booleano, il tipo di dati del risultato `Boolean`è.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="1a3a9-142">Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i `expression1` tipi `expression2`di dati di e.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="1a3a9-143">Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="1a3a9-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a3a9-144">L' `And` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1a3a9-145">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1a3a9-146">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1a3a9-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a3a9-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a3a9-147">Example</span></span>  
 <span data-ttu-id="1a3a9-148">Nell'esempio seguente viene utilizzato `And` l'operatore per eseguire una congiunzione logica di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="1a3a9-149">Il risultato è un `Boolean` valore che indica se entrambe le espressioni sono. `True`</span><span class="sxs-lookup"><span data-stu-id="1a3a9-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="1a3a9-150">Nell'esempio precedente vengono restituiti i `True` risultati `False`di e, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a3a9-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a3a9-151">Example</span></span>  
 <span data-ttu-id="1a3a9-152">Nell'esempio seguente viene usato `And` l'operatore per eseguire congiunzioni logiche sui singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="1a3a9-153">Il bit nel modello di risultato viene impostato se i bit corrispondenti negli operandi sono entrambi impostati su 1.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="1a3a9-154">Nell'esempio precedente vengono prodotti rispettivamente i risultati 8, 2 e 0.</span><span class="sxs-lookup"><span data-stu-id="1a3a9-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a3a9-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a3a9-155">See also</span></span>

- [<span data-ttu-id="1a3a9-156">Operatori logici/bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a3a9-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="1a3a9-157">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a3a9-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1a3a9-158">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="1a3a9-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1a3a9-159">Operatore AndAlso</span><span class="sxs-lookup"><span data-stu-id="1a3a9-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="1a3a9-160">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a3a9-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
