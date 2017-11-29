---
title: Operatore Or (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4c9429eb2bdeb86bfa73786433231fdc22a230d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="7558c-102">Operatore Or (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7558c-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="7558c-103">Esegue una disgiunzione logica tra due `Boolean` espressioni oppure una disgiunzione bit per bit tra due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="7558c-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7558c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7558c-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="7558c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7558c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7558c-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7558c-106">Required.</span></span> <span data-ttu-id="7558c-107">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7558c-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="7558c-108">Per `Boolean` confronto, `result` è la disgiunzione logica di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="7558c-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="7558c-109">Operazioni bit per bit, `result` è un valore numerico che rappresenta la disgiunzione bit per bit di due schemi di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="7558c-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="7558c-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7558c-110">Required.</span></span> <span data-ttu-id="7558c-111">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7558c-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="7558c-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7558c-112">Required.</span></span> <span data-ttu-id="7558c-113">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="7558c-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7558c-114">Note</span><span class="sxs-lookup"><span data-stu-id="7558c-114">Remarks</span></span>  
 <span data-ttu-id="7558c-115">Per `Boolean` confronto, `result` è `False` se e solo se entrambi `expression1` e `expression2` restituiscono `False`.</span><span class="sxs-lookup"><span data-stu-id="7558c-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="7558c-116">Nella tabella seguente viene illustrato come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="7558c-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="7558c-117">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="7558c-117">If `expression1` is</span></span>|<span data-ttu-id="7558c-118">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="7558c-118">And `expression2` is</span></span>|<span data-ttu-id="7558c-119">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="7558c-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="7558c-120">In un `Boolean` confronto, il `Or` operatore valuta sempre entrambe le espressioni, che potrebbe includere chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="7558c-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="7558c-121">Il [operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) esegue *corto circuito*, che significa che se `expression1` è `True`, quindi `expression2` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="7558c-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="7558c-122">Operazioni bit per bit, il `Or` operatore esegue un confronto bit per bit di bit in due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7558c-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="7558c-123">Se in bit in `expression1` è</span><span class="sxs-lookup"><span data-stu-id="7558c-123">If bit in `expression1` is</span></span>|<span data-ttu-id="7558c-124">E il bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="7558c-124">And bit in `expression2` is</span></span>|<span data-ttu-id="7558c-125">Il bit `result` è</span><span class="sxs-lookup"><span data-stu-id="7558c-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="7558c-126">1</span><span class="sxs-lookup"><span data-stu-id="7558c-126">1</span></span>|<span data-ttu-id="7558c-127">1</span><span class="sxs-lookup"><span data-stu-id="7558c-127">1</span></span>|<span data-ttu-id="7558c-128">1</span><span class="sxs-lookup"><span data-stu-id="7558c-128">1</span></span>|  
|<span data-ttu-id="7558c-129">1</span><span class="sxs-lookup"><span data-stu-id="7558c-129">1</span></span>|<span data-ttu-id="7558c-130">0</span><span class="sxs-lookup"><span data-stu-id="7558c-130">0</span></span>|<span data-ttu-id="7558c-131">1</span><span class="sxs-lookup"><span data-stu-id="7558c-131">1</span></span>|  
|<span data-ttu-id="7558c-132">0</span><span class="sxs-lookup"><span data-stu-id="7558c-132">0</span></span>|<span data-ttu-id="7558c-133">1</span><span class="sxs-lookup"><span data-stu-id="7558c-133">1</span></span>|<span data-ttu-id="7558c-134">1</span><span class="sxs-lookup"><span data-stu-id="7558c-134">1</span></span>|  
|<span data-ttu-id="7558c-135">0</span><span class="sxs-lookup"><span data-stu-id="7558c-135">0</span></span>|<span data-ttu-id="7558c-136">0</span><span class="sxs-lookup"><span data-stu-id="7558c-136">0</span></span>|<span data-ttu-id="7558c-137">0</span><span class="sxs-lookup"><span data-stu-id="7558c-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7558c-138">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiuse tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="7558c-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="7558c-139">Riepilogo dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7558c-139">Data Types</span></span>  
 <span data-ttu-id="7558c-140">Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (– 1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="7558c-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="7558c-141">Per un `Boolean` è il tipo di dati del risultato del confronto, `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7558c-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="7558c-142">Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="7558c-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="7558c-143">Vedere la tabella "Confronti relazionali e bit per bit" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="7558c-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7558c-144">Overload</span><span class="sxs-lookup"><span data-stu-id="7558c-144">Overloading</span></span>  
 <span data-ttu-id="7558c-145">Il `Or` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="7558c-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7558c-146">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="7558c-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7558c-147">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7558c-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7558c-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="7558c-148">Example</span></span>  
 <span data-ttu-id="7558c-149">L'esempio seguente usa il `Or` operatore per eseguire una disgiunzione logica inclusiva su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="7558c-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="7558c-150">Il risultato è un `Boolean` valore che rappresenta se una delle due espressioni è `True`.</span><span class="sxs-lookup"><span data-stu-id="7558c-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 <span data-ttu-id="7558c-151">Nell'esempio precedente produce i risultati di `True`, `True`, e `False`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="7558c-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7558c-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="7558c-152">Example</span></span>  
 <span data-ttu-id="7558c-153">L'esempio seguente usa il `Or` operatore per eseguire la disgiunzione logica inclusiva su singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="7558c-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="7558c-154">Il bit nel risultato viene impostato se uno dei bit corrispondenti negli operandi è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="7558c-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 <span data-ttu-id="7558c-155">Nell'esempio precedente produce risultati di 10, 14 e 14, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="7558c-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7558c-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7558c-156">See Also</span></span>  
 [<span data-ttu-id="7558c-157">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7558c-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="7558c-158">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7558c-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="7558c-159">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="7558c-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="7558c-160">Operatore OrElse</span><span class="sxs-lookup"><span data-stu-id="7558c-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)  
 [<span data-ttu-id="7558c-161">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7558c-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
