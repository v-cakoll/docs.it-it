---
title: Operatore Xor (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b14f11f2df2df9c29e88e9188390cfe245d2cb58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="66e99-102">Operatore Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66e99-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="66e99-103">Esegue un'esclusione logica su due `Boolean` espressioni oppure un'esclusione bit per bit su due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="66e99-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66e99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66e99-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="66e99-105">Parti</span><span class="sxs-lookup"><span data-stu-id="66e99-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="66e99-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="66e99-106">Required.</span></span> <span data-ttu-id="66e99-107">Qualsiasi `Boolean` o una variabile numerica.</span><span class="sxs-lookup"><span data-stu-id="66e99-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="66e99-108">Confronto di valori booleani, `result` è l'esclusione logica (disgiunzione logica) di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="66e99-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="66e99-109">Operazioni bit per bit, `result` è un valore numerico che rappresenta l'esclusione bit per bit (disgiunzione bit per bit) di due schemi di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="66e99-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="66e99-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="66e99-110">Required.</span></span> <span data-ttu-id="66e99-111">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="66e99-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="66e99-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="66e99-112">Required.</span></span> <span data-ttu-id="66e99-113">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="66e99-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66e99-114">Note</span><span class="sxs-lookup"><span data-stu-id="66e99-114">Remarks</span></span>  
 <span data-ttu-id="66e99-115">Confronto di valori booleani, `result` è `True` se e solo se uno degli `expression1` e `expression2` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="66e99-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="66e99-116">Ovvero, se e solo se `expression1` e `expression2` valutare opposti `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="66e99-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="66e99-117">Nella tabella seguente viene illustrato come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="66e99-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="66e99-118">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="66e99-118">If `expression1` is</span></span>|<span data-ttu-id="66e99-119">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="66e99-119">And `expression2` is</span></span>|<span data-ttu-id="66e99-120">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="66e99-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="66e99-121">In un confronto booleano, il `Xor` operatore valuta sempre entrambe le espressioni, che potrebbe includere chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="66e99-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="66e99-122">Non vi è alcun equivalente di corto circuito per `Xor`, perché il risultato dipende sempre da entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="66e99-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="66e99-123">Per *corto circuito* gli operatori logici, vedere [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) e [operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="66e99-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="66e99-124">Operazioni bit per bit, il `Xor` operatore esegue un confronto bit per bit di bit in due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="66e99-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="66e99-125">Se in bit in `expression1` è</span><span class="sxs-lookup"><span data-stu-id="66e99-125">If bit in `expression1` is</span></span>|<span data-ttu-id="66e99-126">E il bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="66e99-126">And bit in `expression2` is</span></span>|<span data-ttu-id="66e99-127">Il bit `result` è</span><span class="sxs-lookup"><span data-stu-id="66e99-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="66e99-128">1</span><span class="sxs-lookup"><span data-stu-id="66e99-128">1</span></span>|<span data-ttu-id="66e99-129">1</span><span class="sxs-lookup"><span data-stu-id="66e99-129">1</span></span>|<span data-ttu-id="66e99-130">0</span><span class="sxs-lookup"><span data-stu-id="66e99-130">0</span></span>|  
|<span data-ttu-id="66e99-131">1</span><span class="sxs-lookup"><span data-stu-id="66e99-131">1</span></span>|<span data-ttu-id="66e99-132">0</span><span class="sxs-lookup"><span data-stu-id="66e99-132">0</span></span>|<span data-ttu-id="66e99-133">1</span><span class="sxs-lookup"><span data-stu-id="66e99-133">1</span></span>|  
|<span data-ttu-id="66e99-134">0</span><span class="sxs-lookup"><span data-stu-id="66e99-134">0</span></span>|<span data-ttu-id="66e99-135">1</span><span class="sxs-lookup"><span data-stu-id="66e99-135">1</span></span>|<span data-ttu-id="66e99-136">1</span><span class="sxs-lookup"><span data-stu-id="66e99-136">1</span></span>|  
|<span data-ttu-id="66e99-137">0</span><span class="sxs-lookup"><span data-stu-id="66e99-137">0</span></span>|<span data-ttu-id="66e99-138">0</span><span class="sxs-lookup"><span data-stu-id="66e99-138">0</span></span>|<span data-ttu-id="66e99-139">0</span><span class="sxs-lookup"><span data-stu-id="66e99-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="66e99-140">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuse tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="66e99-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="66e99-141">Ad esempio 5 `Xor` 3 è 6.</span><span class="sxs-lookup"><span data-stu-id="66e99-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="66e99-142">Per comprendere meglio in tal caso, convertire in rappresentazioni binarie, 101 e 011 5 e 3.</span><span class="sxs-lookup"><span data-stu-id="66e99-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="66e99-143">Utilizzare quindi la tabella precedente per determinare che 101 Xor 011 è 110, ovvero la rappresentazione binaria del numero decimale 6.</span><span class="sxs-lookup"><span data-stu-id="66e99-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="66e99-144">Riepilogo dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="66e99-144">Data Types</span></span>  
 <span data-ttu-id="66e99-145">Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (– 1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="66e99-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="66e99-146">Per un `Boolean` è il tipo di dati del risultato del confronto, `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="66e99-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="66e99-147">Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="66e99-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="66e99-148">Vedere la tabella "Confronti relazionali e bit per bit" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="66e99-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="66e99-149">Overload</span><span class="sxs-lookup"><span data-stu-id="66e99-149">Overloading</span></span>  
 <span data-ttu-id="66e99-150">Il `Xor` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="66e99-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="66e99-151">Se il codice utilizza l'operatore su una classe o una struttura, assicurarsi che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="66e99-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="66e99-152">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="66e99-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66e99-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="66e99-153">Example</span></span>  
 <span data-ttu-id="66e99-154">L'esempio seguente usa il `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica) su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="66e99-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="66e99-155">Il risultato è un `Boolean` valore che indica se una sola delle espressioni è `True`.</span><span class="sxs-lookup"><span data-stu-id="66e99-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 <span data-ttu-id="66e99-156">Nell'esempio precedente produce i risultati di `False`, `True`, e `False`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="66e99-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66e99-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="66e99-157">Example</span></span>  
 <span data-ttu-id="66e99-158">L'esempio seguente usa il `Xor` operatore per eseguire l'esclusione logica (disgiunzione logica) dei singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="66e99-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="66e99-159">Il bit nel risultato viene impostato se esattamente uno dei bit corrispondenti negli operandi è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="66e99-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 <span data-ttu-id="66e99-160">Nell'esempio precedente produce risultati di 2, 12 e 14, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="66e99-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e99-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e99-161">See Also</span></span>  
 [<span data-ttu-id="66e99-162">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66e99-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="66e99-163">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66e99-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="66e99-164">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="66e99-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="66e99-165">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66e99-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
