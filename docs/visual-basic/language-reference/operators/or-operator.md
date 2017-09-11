---
title: Operatore OR (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Or
dev_langs:
- VB
helpviewer_keywords:
- Or operator
- operators [Visual Basic], bitwise
- inclusive Or operator
- bitwise operators, OR operator
- Or keyword
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison
- logical disjunction
- disjunction operator
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 01d51f50dd785f168ed850e3f1763b300d9d2011
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="e6a07-102">Operatore Or (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6a07-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="e6a07-103">Esegue una disgiunzione logica tra due `Boolean` espressioni oppure una disgiunzione bit per bit tra due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="e6a07-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6a07-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="e6a07-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e6a07-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e6a07-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e6a07-106">Required.</span></span> <span data-ttu-id="e6a07-107">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="e6a07-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="e6a07-108">Per `Boolean` confronto, `result` è la disgiunzione logica di due `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="e6a07-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="e6a07-109">Operazioni bit per bit, `result` è un valore numerico che rappresenta la disgiunzione bit per bit di due schemi di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="e6a07-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="e6a07-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e6a07-110">Required.</span></span> <span data-ttu-id="e6a07-111">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="e6a07-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="e6a07-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e6a07-112">Required.</span></span> <span data-ttu-id="e6a07-113">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="e6a07-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6a07-114">Note</span><span class="sxs-lookup"><span data-stu-id="e6a07-114">Remarks</span></span>  
 <span data-ttu-id="e6a07-115">Per `Boolean` confronto, `result` è `False` se e solo se `expression1` e `expression2` restituiscono `False`.</span><span class="sxs-lookup"><span data-stu-id="e6a07-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="e6a07-116">Nella tabella seguente viene illustrato come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="e6a07-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="e6a07-117">If `expression1` is</span><span class="sxs-lookup"><span data-stu-id="e6a07-117">If `expression1` is</span></span>|<span data-ttu-id="e6a07-118">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="e6a07-118">And `expression2` is</span></span>|<span data-ttu-id="e6a07-119">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="e6a07-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="e6a07-120">In un `Boolean` confronto, il `Or` operatore valuta sempre entrambe le espressioni, inclusa l'esecuzione di chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="e6a07-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="e6a07-121">Il [operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) esegue *corto circuito*, che significa che se `expression1` è `True`, quindi `expression2` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="e6a07-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="e6a07-122">Operazioni bit per bit, il `Or` operatore esegue un confronto bit per bit dei bit di due espressioni numeriche e imposta il bit nel corrispondente `result` in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e6a07-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="e6a07-123">Se bit `expression1` è</span><span class="sxs-lookup"><span data-stu-id="e6a07-123">If bit in `expression1` is</span></span>|<span data-ttu-id="e6a07-124">E il bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="e6a07-124">And bit in `expression2` is</span></span>|<span data-ttu-id="e6a07-125">Il bit `result` è</span><span class="sxs-lookup"><span data-stu-id="e6a07-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="e6a07-126">1</span><span class="sxs-lookup"><span data-stu-id="e6a07-126">1</span></span>|<span data-ttu-id="e6a07-127">1</span><span class="sxs-lookup"><span data-stu-id="e6a07-127">1</span></span>|<span data-ttu-id="e6a07-128">1</span><span class="sxs-lookup"><span data-stu-id="e6a07-128">1</span></span>|  
|<span data-ttu-id="e6a07-129">1</span><span class="sxs-lookup"><span data-stu-id="e6a07-129">1</span></span>|<span data-ttu-id="e6a07-130">0</span><span class="sxs-lookup"><span data-stu-id="e6a07-130">0</span></span>|<span data-ttu-id="e6a07-131">1</span><span class="sxs-lookup"><span data-stu-id="e6a07-131">1</span></span>|  
|<span data-ttu-id="e6a07-132">0</span><span class="sxs-lookup"><span data-stu-id="e6a07-132">0</span></span>|<span data-ttu-id="e6a07-133">1</span><span class="sxs-lookup"><span data-stu-id="e6a07-133">1</span></span>|<span data-ttu-id="e6a07-134">1</span><span class="sxs-lookup"><span data-stu-id="e6a07-134">1</span></span>|  
|<span data-ttu-id="e6a07-135">0</span><span class="sxs-lookup"><span data-stu-id="e6a07-135">0</span></span>|<span data-ttu-id="e6a07-136">0</span><span class="sxs-lookup"><span data-stu-id="e6a07-136">0</span></span>|<span data-ttu-id="e6a07-137">0</span><span class="sxs-lookup"><span data-stu-id="e6a07-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e6a07-138">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore a altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit devono essere racchiusi tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="e6a07-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="e6a07-139">Riepilogo dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e6a07-139">Data Types</span></span>  
 <span data-ttu-id="e6a07-140">Se gli operandi sono costituiti da uno `Boolean` espressione e un'espressione numerica, Visual Basic converte il `Boolean` espressione in un valore numerico (– 1 per `True` e 0 per `False`) ed esegue un'operazione OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="e6a07-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="e6a07-141">Per un `Boolean` è il tipo di dati del risultato del confronto, `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e6a07-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="e6a07-142">Per un confronto bit per bit, il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="e6a07-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="e6a07-143">Vedere la tabella "Confronti relazionali e bit per bit" in [dati tipi di operatore restituisce un risultato](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="e6a07-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e6a07-144">Overload</span><span class="sxs-lookup"><span data-stu-id="e6a07-144">Overloading</span></span>  
 <span data-ttu-id="e6a07-145">Il `Or` operatore può essere *overload*, il che significa che una classe o struttura possibile ridefinire il comportamento quando un operando specifica il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="e6a07-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e6a07-146">Se il codice utilizza l'operatore su una classe o struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="e6a07-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e6a07-147">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e6a07-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a07-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6a07-148">Example</span></span>  
 <span data-ttu-id="e6a07-149">Nell'esempio seguente viene utilizzata la `Or` operatore per eseguire una disgiunzione logica su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="e6a07-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="e6a07-150">Il risultato è un `Boolean` valore che rappresenta se una delle due espressioni è `True`.</span><span class="sxs-lookup"><span data-stu-id="e6a07-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 <span data-ttu-id="e6a07-151">[!code-vb[VbVbalrOperators&#35;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e6a07-151">[!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="e6a07-152">Nell'esempio precedente produce risultati di `True`, `True`, e `False`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e6a07-152">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a07-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6a07-153">Example</span></span>  
 <span data-ttu-id="e6a07-154">Nell'esempio seguente viene utilizzata la `Or` operatore per eseguire la disgiunzione logica dei singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="e6a07-154">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="e6a07-155">Il bit nel risultato viene impostato se entrambi i bit corrispondenti negli operandi è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="e6a07-155">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 <span data-ttu-id="e6a07-156">[!code-vb[VbVbalrOperators&#36;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e6a07-156">[!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]</span></span>  
  
 <span data-ttu-id="e6a07-157">Nell'esempio precedente produce risultati di 10, 14 e 14, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e6a07-157">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6a07-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6a07-158">See Also</span></span>  
 <span data-ttu-id="e6a07-159">[Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md) </span><span class="sxs-lookup"><span data-stu-id="e6a07-159">[Logical/Bitwise Operators (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md) </span></span>  
<span data-ttu-id="e6a07-160"> [Precedenza tra operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="e6a07-160"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="e6a07-161"> [Elencata degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="e6a07-161"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="e6a07-162"> [OrElse (operatore)](../../../visual-basic/language-reference/operators/orelse-operator.md) </span><span class="sxs-lookup"><span data-stu-id="e6a07-162"> [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) </span></span>  
<span data-ttu-id="e6a07-163"> [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="e6a07-163"> [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>

