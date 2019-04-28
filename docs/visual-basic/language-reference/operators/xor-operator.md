---
title: Operatore Xor (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 0cba3a995fb1ab774c8a5308e58f0b6905fc23f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781173"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="84ceb-102">Operatore Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84ceb-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="84ceb-103">Esegue un'esclusione logica su due `Boolean` espressioni, oppure un'esclusione bit per bit su due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="84ceb-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ceb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84ceb-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="84ceb-105">Parti</span><span class="sxs-lookup"><span data-stu-id="84ceb-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="84ceb-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="84ceb-106">Required.</span></span> <span data-ttu-id="84ceb-107">Qualsiasi `Boolean` o variabile numerica.</span><span class="sxs-lookup"><span data-stu-id="84ceb-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="84ceb-108">Confronto di valori booleani `result` è l'esclusione logica (disgiunzione logica esclusiva) di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="84ceb-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="84ceb-109">Operazioni bit per bit, `result` è un valore numerico che rappresenta l'esclusione bit per bit (disgiunzione bit per bit esclusiva) di due schemi di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="84ceb-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="84ceb-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="84ceb-110">Required.</span></span> <span data-ttu-id="84ceb-111">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="84ceb-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="84ceb-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="84ceb-112">Required.</span></span> <span data-ttu-id="84ceb-113">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="84ceb-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84ceb-114">Note</span><span class="sxs-lookup"><span data-stu-id="84ceb-114">Remarks</span></span>  
 <span data-ttu-id="84ceb-115">Confronto di valori booleani `result` viene `True` se e solo se esattamente uno dei `expression1` e `expression2` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="84ceb-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="84ceb-116">Vale a dire, se e solo se `expression1` e `expression2` valutare opposti `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="84ceb-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="84ceb-117">La tabella seguente illustra come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="84ceb-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="84ceb-118">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="84ceb-118">If `expression1` is</span></span>|<span data-ttu-id="84ceb-119">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="84ceb-119">And `expression2` is</span></span>|<span data-ttu-id="84ceb-120">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="84ceb-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="84ceb-121">In un confronto booleano, il `Xor` operatore valuta sempre entrambe le espressioni, che potrebbe includere effettua le chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="84ceb-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="84ceb-122">Non vi è alcun equivalente di corto circuito a `Xor`, perché il risultato dipende sempre da entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="84ceb-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="84ceb-123">Per la *corto circuito* operatori logici, vedere [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) e [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="84ceb-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="84ceb-124">Operazioni bit per bit, il `Xor` operatore esegue un confronto bit per bit dei bit di due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="84ceb-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="84ceb-125">Se in bit in `expression1` è</span><span class="sxs-lookup"><span data-stu-id="84ceb-125">If bit in `expression1` is</span></span>|<span data-ttu-id="84ceb-126">E il bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="84ceb-126">And bit in `expression2` is</span></span>|<span data-ttu-id="84ceb-127">Il bit nel `result` è</span><span class="sxs-lookup"><span data-stu-id="84ceb-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="84ceb-128">1</span><span class="sxs-lookup"><span data-stu-id="84ceb-128">1</span></span>|<span data-ttu-id="84ceb-129">1</span><span class="sxs-lookup"><span data-stu-id="84ceb-129">1</span></span>|<span data-ttu-id="84ceb-130">0</span><span class="sxs-lookup"><span data-stu-id="84ceb-130">0</span></span>|  
|<span data-ttu-id="84ceb-131">1</span><span class="sxs-lookup"><span data-stu-id="84ceb-131">1</span></span>|<span data-ttu-id="84ceb-132">0</span><span class="sxs-lookup"><span data-stu-id="84ceb-132">0</span></span>|<span data-ttu-id="84ceb-133">1</span><span class="sxs-lookup"><span data-stu-id="84ceb-133">1</span></span>|  
|<span data-ttu-id="84ceb-134">0</span><span class="sxs-lookup"><span data-stu-id="84ceb-134">0</span></span>|<span data-ttu-id="84ceb-135">1</span><span class="sxs-lookup"><span data-stu-id="84ceb-135">1</span></span>|<span data-ttu-id="84ceb-136">1</span><span class="sxs-lookup"><span data-stu-id="84ceb-136">1</span></span>|  
|<span data-ttu-id="84ceb-137">0</span><span class="sxs-lookup"><span data-stu-id="84ceb-137">0</span></span>|<span data-ttu-id="84ceb-138">0</span><span class="sxs-lookup"><span data-stu-id="84ceb-138">0</span></span>|<span data-ttu-id="84ceb-139">0</span><span class="sxs-lookup"><span data-stu-id="84ceb-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="84ceb-140">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiusi tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="84ceb-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="84ceb-141">Ad esempio, 5 `Xor` 3 è 6.</span><span class="sxs-lookup"><span data-stu-id="84ceb-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="84ceb-142">Per visualizzare il motivo per cui si tratta comunque, convertire in rappresentazioni binarie, 101 e 011 5 e 3.</span><span class="sxs-lookup"><span data-stu-id="84ceb-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="84ceb-143">Usare quindi la tabella precedente per determinare che Xor 101 011 è 110, ovvero la rappresentazione binaria del numero decimale 6.</span><span class="sxs-lookup"><span data-stu-id="84ceb-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="84ceb-144">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="84ceb-144">Data Types</span></span>  
 <span data-ttu-id="84ceb-145">Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="84ceb-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="84ceb-146">Per un `Boolean` è il tipo di dati del risultato del confronto, `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="84ceb-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="84ceb-147">Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="84ceb-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="84ceb-148">Vedere la tabella "Relazionale e confronti bit per bit" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="84ceb-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="84ceb-149">Overload</span><span class="sxs-lookup"><span data-stu-id="84ceb-149">Overloading</span></span>  
 <span data-ttu-id="84ceb-150">Il `Xor` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="84ceb-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="84ceb-151">Se il codice Usa l'operatore su una classe o struttura, assicurarsi che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="84ceb-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="84ceb-152">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="84ceb-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84ceb-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="84ceb-153">Example</span></span>  
 <span data-ttu-id="84ceb-154">L'esempio seguente usa il `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica esclusiva) di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="84ceb-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="84ceb-155">Il risultato è un `Boolean` valore che indica se esattamente una delle espressioni è `True`.</span><span class="sxs-lookup"><span data-stu-id="84ceb-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="84ceb-156">L'esempio precedente produce i risultati dei `False`, `True`, e `False`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="84ceb-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84ceb-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="84ceb-157">Example</span></span>  
 <span data-ttu-id="84ceb-158">L'esempio seguente usa il `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica esclusiva) sui singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="84ceb-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="84ceb-159">Il bit nel risultato viene impostato se esattamente uno dei bit corrispondenti in operandi è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="84ceb-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="84ceb-160">L'esempio precedente produce i risultati di 2, 12 e 14, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="84ceb-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ceb-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84ceb-161">See also</span></span>

- [<span data-ttu-id="84ceb-162">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84ceb-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="84ceb-163">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84ceb-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="84ceb-164">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="84ceb-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="84ceb-165">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84ceb-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
