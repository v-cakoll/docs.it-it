---
title: Operatore Or
ms.date: 07/20/2015
f1_keywords:
- vb.Or
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
ms.openlocfilehash: 8f28026b526c29a6122725b2689e53b7f6ee7327
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348246"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="4c214-102">Operatore Or (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c214-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="4c214-103">Esegue una disgiunzione logica di due espressioni `Boolean` o una disgiunzione bit per bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="4c214-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c214-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c214-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4c214-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4c214-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="4c214-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4c214-106">Required.</span></span> <span data-ttu-id="4c214-107">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4c214-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="4c214-108">Per `Boolean` confronto, `result` è la disgiunzione logica inclusiva di due valori di `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4c214-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="4c214-109">Per le operazioni bit per bit, `result` è un valore numerico che rappresenta la disgiunzione bit per bit inclusiva di due modelli di bit numerici.</span><span class="sxs-lookup"><span data-stu-id="4c214-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="4c214-110">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4c214-110">Required.</span></span> <span data-ttu-id="4c214-111">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4c214-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4c214-112">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4c214-112">Required.</span></span> <span data-ttu-id="4c214-113">Qualsiasi `Boolean` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4c214-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c214-114">Note</span><span class="sxs-lookup"><span data-stu-id="4c214-114">Remarks</span></span>  
 <span data-ttu-id="4c214-115">Per `Boolean` confronto, `result` viene `False` se e solo se sia `expression1` che `expression2` restituiscono `False`.</span><span class="sxs-lookup"><span data-stu-id="4c214-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="4c214-116">Nella tabella seguente viene illustrato il modo in cui viene determinato `result`.</span><span class="sxs-lookup"><span data-stu-id="4c214-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="4c214-117">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="4c214-117">If `expression1` is</span></span>|<span data-ttu-id="4c214-118">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="4c214-118">And `expression2` is</span></span>|<span data-ttu-id="4c214-119">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="4c214-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="4c214-120">In un confronto di `Boolean`, l'operatore `Or` valuta sempre entrambe le espressioni, che possono includere la chiamata di routine.</span><span class="sxs-lookup"><span data-stu-id="4c214-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="4c214-121">L' [operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) esegue un *corto circuito*, il che significa che se `expression1` è `True`, `expression2` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="4c214-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="4c214-122">Per le operazioni bit per bit, l'operatore `Or` esegue un confronto bit per bit dei bit posizionati in modo identico in due espressioni numeriche e imposta il bit corrispondente in `result` in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4c214-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="4c214-123">Se bit in `expression1` è</span><span class="sxs-lookup"><span data-stu-id="4c214-123">If bit in `expression1` is</span></span>|<span data-ttu-id="4c214-124">E bit in `expression2` è</span><span class="sxs-lookup"><span data-stu-id="4c214-124">And bit in `expression2` is</span></span>|<span data-ttu-id="4c214-125">Il bit in `result` è</span><span class="sxs-lookup"><span data-stu-id="4c214-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="4c214-126">1</span><span class="sxs-lookup"><span data-stu-id="4c214-126">1</span></span>|<span data-ttu-id="4c214-127">1</span><span class="sxs-lookup"><span data-stu-id="4c214-127">1</span></span>|<span data-ttu-id="4c214-128">1</span><span class="sxs-lookup"><span data-stu-id="4c214-128">1</span></span>|  
|<span data-ttu-id="4c214-129">1</span><span class="sxs-lookup"><span data-stu-id="4c214-129">1</span></span>|<span data-ttu-id="4c214-130">0</span><span class="sxs-lookup"><span data-stu-id="4c214-130">0</span></span>|<span data-ttu-id="4c214-131">1</span><span class="sxs-lookup"><span data-stu-id="4c214-131">1</span></span>|  
|<span data-ttu-id="4c214-132">0</span><span class="sxs-lookup"><span data-stu-id="4c214-132">0</span></span>|<span data-ttu-id="4c214-133">1</span><span class="sxs-lookup"><span data-stu-id="4c214-133">1</span></span>|<span data-ttu-id="4c214-134">1</span><span class="sxs-lookup"><span data-stu-id="4c214-134">1</span></span>|  
|<span data-ttu-id="4c214-135">0</span><span class="sxs-lookup"><span data-stu-id="4c214-135">0</span></span>|<span data-ttu-id="4c214-136">0</span><span class="sxs-lookup"><span data-stu-id="4c214-136">0</span></span>|<span data-ttu-id="4c214-137">0</span><span class="sxs-lookup"><span data-stu-id="4c214-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="4c214-138">Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.</span><span class="sxs-lookup"><span data-stu-id="4c214-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="4c214-139">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4c214-139">Data Types</span></span>  
 <span data-ttu-id="4c214-140">Se gli operandi sono costituiti da un'espressione `Boolean` e un'espressione numerica, Visual Basic converte l'espressione `Boolean` in un valore numerico (-1 per `True` e 0 per `False`) ed esegue un'operazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="4c214-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="4c214-141">Per un confronto di `Boolean`, il tipo di dati del risultato è `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4c214-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="4c214-142">Per un confronto bit per bit, il tipo di dati result è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`.</span><span class="sxs-lookup"><span data-stu-id="4c214-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4c214-143">Vedere la tabella "confronto relazionale e bit per bit" in [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="4c214-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4c214-144">Overload</span><span class="sxs-lookup"><span data-stu-id="4c214-144">Overloading</span></span>  
 <span data-ttu-id="4c214-145">L'operatore `Or` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="4c214-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4c214-146">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="4c214-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4c214-147">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4c214-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c214-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c214-148">Example</span></span>  
 <span data-ttu-id="4c214-149">Nell'esempio seguente viene usato l'operatore `Or` per eseguire una disgiunzione logica inclusiva su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="4c214-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="4c214-150">Il risultato è un valore `Boolean` che indica se una delle due espressioni è `True`.</span><span class="sxs-lookup"><span data-stu-id="4c214-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="4c214-151">Nell'esempio precedente vengono prodotti rispettivamente i risultati di `True`, `True`e `False`.</span><span class="sxs-lookup"><span data-stu-id="4c214-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c214-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c214-152">Example</span></span>  
 <span data-ttu-id="4c214-153">Nell'esempio seguente viene usato l'operatore `Or` per eseguire la disgiunzione logica inclusiva sui singoli bit di due espressioni numeriche.</span><span class="sxs-lookup"><span data-stu-id="4c214-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="4c214-154">Il bit nel modello di risultato viene impostato se uno dei bit corrispondenti negli operandi è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="4c214-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="4c214-155">Nell'esempio precedente vengono prodotti rispettivamente i risultati 10, 14 e 14.</span><span class="sxs-lookup"><span data-stu-id="4c214-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c214-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c214-156">See also</span></span>

- [<span data-ttu-id="4c214-157">Operatori logici/bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c214-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="4c214-158">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c214-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4c214-159">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="4c214-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4c214-160">Operatore OrElse</span><span class="sxs-lookup"><span data-stu-id="4c214-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="4c214-161">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c214-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
