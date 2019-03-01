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
ms.openlocfilehash: 090ae67c1e5f04c5d9c4f6aed7f8131d8f830166
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968855"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="c62d8-102">Operatore And (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c62d8-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="c62d8-103">Esegue una congiunzione logica su due `Boolean` espressioni oppure una congiunzione bit per bit su due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="c62d8-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c62d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c62d8-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c62d8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c62d8-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c62d8-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c62d8-106">Required.</span></span> <span data-ttu-id="c62d8-107">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="c62d8-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="c62d8-108">Confronto di valori booleani `result` è la congiunzione logica di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="c62d8-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="c62d8-109">Operazioni bit per bit, `result` è un valore numerico che rappresenta la combinazione bit per bit di due schemi di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="c62d8-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="c62d8-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c62d8-110">Required.</span></span> <span data-ttu-id="c62d8-111">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="c62d8-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c62d8-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c62d8-112">Required.</span></span> <span data-ttu-id="c62d8-113">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="c62d8-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c62d8-114">Note</span><span class="sxs-lookup"><span data-stu-id="c62d8-114">Remarks</span></span>  
 <span data-ttu-id="c62d8-115">Confronto di valori booleani `result` viene `True` se e solo se entrambi `expression1` e `expression2` restituiscono `True`.</span><span class="sxs-lookup"><span data-stu-id="c62d8-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="c62d8-116">La tabella seguente illustra come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="c62d8-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c62d8-117">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="c62d8-117">If `expression1` is</span></span>|<span data-ttu-id="c62d8-118">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="c62d8-118">And `expression2` is</span></span>|<span data-ttu-id="c62d8-119">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="c62d8-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="c62d8-120">In un confronto booleano, il `And` operatore valuta sempre entrambe le espressioni, che potrebbe includere effettua le chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="c62d8-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="c62d8-121">Il [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) esegue *corto circuito*, che significa che se `expression1` viene `False`, quindi `expression2` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="c62d8-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="c62d8-122">Quando applicata a valori numerici, il `And` operatore esegue un confronto bit per bit dei bit di due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="c62d8-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="c62d8-123">Se in bit in `expression1` è</span><span class="sxs-lookup"><span data-stu-id="c62d8-123">If bit in `expression1` is</span></span>|<span data-ttu-id="c62d8-124">E il bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="c62d8-124">And bit in `expression2` is</span></span>|<span data-ttu-id="c62d8-125">Il bit nel `result` è</span><span class="sxs-lookup"><span data-stu-id="c62d8-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="c62d8-126">1</span><span class="sxs-lookup"><span data-stu-id="c62d8-126">1</span></span>|<span data-ttu-id="c62d8-127">1</span><span class="sxs-lookup"><span data-stu-id="c62d8-127">1</span></span>|<span data-ttu-id="c62d8-128">1</span><span class="sxs-lookup"><span data-stu-id="c62d8-128">1</span></span>|  
|<span data-ttu-id="c62d8-129">1</span><span class="sxs-lookup"><span data-stu-id="c62d8-129">1</span></span>|<span data-ttu-id="c62d8-130">0</span><span class="sxs-lookup"><span data-stu-id="c62d8-130">0</span></span>|<span data-ttu-id="c62d8-131">0</span><span class="sxs-lookup"><span data-stu-id="c62d8-131">0</span></span>|  
|<span data-ttu-id="c62d8-132">0</span><span class="sxs-lookup"><span data-stu-id="c62d8-132">0</span></span>|<span data-ttu-id="c62d8-133">1</span><span class="sxs-lookup"><span data-stu-id="c62d8-133">1</span></span>|<span data-ttu-id="c62d8-134">0</span><span class="sxs-lookup"><span data-stu-id="c62d8-134">0</span></span>|  
|<span data-ttu-id="c62d8-135">0</span><span class="sxs-lookup"><span data-stu-id="c62d8-135">0</span></span>|<span data-ttu-id="c62d8-136">0</span><span class="sxs-lookup"><span data-stu-id="c62d8-136">0</span></span>|<span data-ttu-id="c62d8-137">0</span><span class="sxs-lookup"><span data-stu-id="c62d8-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c62d8-138">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuso tra parentesi per garantire risultati accurati.</span><span class="sxs-lookup"><span data-stu-id="c62d8-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="c62d8-139">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c62d8-139">Data Types</span></span>  
 <span data-ttu-id="c62d8-140">Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="c62d8-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="c62d8-141">Per un confronto booleano, il tipo di dati del risultato è `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c62d8-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="c62d8-142">Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="c62d8-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="c62d8-143">Vedere la tabella "Relazionale e confronti bit per bit" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="c62d8-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c62d8-144">Il `And` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="c62d8-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c62d8-145">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="c62d8-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c62d8-146">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c62d8-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c62d8-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="c62d8-147">Example</span></span>  
 <span data-ttu-id="c62d8-148">L'esempio seguente usa il `And` operatore per eseguire una congiunzione logica su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="c62d8-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="c62d8-149">Il risultato è un `Boolean` valore che indica se entrambe le espressioni sono `True`.</span><span class="sxs-lookup"><span data-stu-id="c62d8-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="c62d8-150">Nell'esempio precedente produce i risultati dei `True` e `False`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="c62d8-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c62d8-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="c62d8-151">Example</span></span>  
 <span data-ttu-id="c62d8-152">L'esempio seguente usa il `And` operatore per eseguire la congiunzione logica tra i singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="c62d8-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="c62d8-153">Il bit nel risultato viene impostato se i bit corrispondenti negli operandi sono entrambe impostate su 1.</span><span class="sxs-lookup"><span data-stu-id="c62d8-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="c62d8-154">Nell'esempio precedente produce i risultati di 8, 2 e 0, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="c62d8-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c62d8-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c62d8-155">See also</span></span>
- [<span data-ttu-id="c62d8-156">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c62d8-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="c62d8-157">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c62d8-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c62d8-158">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="c62d8-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c62d8-159">Operatore AndAlso</span><span class="sxs-lookup"><span data-stu-id="c62d8-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="c62d8-160">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c62d8-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
