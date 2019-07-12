---
title: Operatore OrElse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 02be78c8f2b7529f1fb0e46e9fe610a3c66b0652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860137"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="b3def-102">Operatore OrElse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3def-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="b3def-103">Esegue una disgiunzione logica inclusiva su due espressioni di corto circuito.</span><span class="sxs-lookup"><span data-stu-id="b3def-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3def-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3def-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="b3def-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b3def-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b3def-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="b3def-106">Required.</span></span> <span data-ttu-id="b3def-107">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="b3def-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="b3def-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="b3def-108">Required.</span></span> <span data-ttu-id="b3def-109">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="b3def-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="b3def-110">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="b3def-110">Required.</span></span> <span data-ttu-id="b3def-111">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="b3def-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3def-112">Note</span><span class="sxs-lookup"><span data-stu-id="b3def-112">Remarks</span></span>  
 <span data-ttu-id="b3def-113">Un'operazione logica viene detto *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="b3def-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="b3def-114">Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario per valutare la seconda espressione, in quanto non può modificare il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="b3def-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="b3def-115">Corto circuito può migliorare le prestazioni se l'espressione ignorato è complesso, o se prevede le chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="b3def-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="b3def-116">Se una o entrambe le espressioni restituiscono `True`, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="b3def-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="b3def-117">La tabella seguente illustra come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="b3def-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="b3def-118">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="b3def-118">If `expression1` is</span></span>|<span data-ttu-id="b3def-119">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="b3def-119">And `expression2` is</span></span>|<span data-ttu-id="b3def-120">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="b3def-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="b3def-121">(non valutati)</span><span class="sxs-lookup"><span data-stu-id="b3def-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="b3def-122">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="b3def-122">Data Types</span></span>  
 <span data-ttu-id="b3def-123">Il `OrElse` operatore è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b3def-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="b3def-124">Visual Basic consente di convertire ogni operando in base alle esigenze per `Boolean` prima della valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="b3def-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="b3def-125">Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` per quel tipo in modo che `False` diventa `0` e `True` diventa `-1`.</span><span class="sxs-lookup"><span data-stu-id="b3def-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="b3def-126">Per altre informazioni, vedere [conversioni dei tipi booleani](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="b3def-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="b3def-127">Overload</span><span class="sxs-lookup"><span data-stu-id="b3def-127">Overloading</span></span>  
 <span data-ttu-id="b3def-128">Il [operatore Or](../../../visual-basic/language-reference/operators/or-operator.md) e il [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) può essere *sottoposti a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di tale classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="b3def-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b3def-129">L'overload di `Or` e `IsTrue` operatori influisce sul comportamento del `OrElse` operatore.</span><span class="sxs-lookup"><span data-stu-id="b3def-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="b3def-130">Se il codice usi `OrElse` in una classe o struttura che esegue l'overload `Or` e `IsTrue`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="b3def-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="b3def-131">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b3def-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3def-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3def-132">Example</span></span>  
 <span data-ttu-id="b3def-133">L'esempio seguente usa il `OrElse` operatore per eseguire la disgiunzione logica tra due espressioni.</span><span class="sxs-lookup"><span data-stu-id="b3def-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="b3def-134">Il risultato è un `Boolean` valore che rappresenta se viene soddisfatta una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="b3def-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="b3def-135">Se la prima espressione è `True`, la seconda non viene valutata.</span><span class="sxs-lookup"><span data-stu-id="b3def-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="b3def-136">Nell'esempio precedente produce i risultati dei `True`, `True`, e `False` rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b3def-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="b3def-137">Nel calcolo della `firstCheck`, la seconda espressione non viene valutata il primo è già `True`.</span><span class="sxs-lookup"><span data-stu-id="b3def-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="b3def-138">Tuttavia, la seconda espressione viene valutata nel calcolo della `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="b3def-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3def-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3def-139">Example</span></span>  
 <span data-ttu-id="b3def-140">L'esempio seguente mostra un `If`... `Then` istruzione che contiene due chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="b3def-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="b3def-141">Se la prima chiamata restituisce `True`, la seconda procedura non viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="b3def-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="b3def-142">Ciò potrebbe produrre risultati imprevisti se la seconda procedura esegue le attività importanti che devono essere sempre eseguite quando viene eseguito in questa sezione del codice.</span><span class="sxs-lookup"><span data-stu-id="b3def-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="b3def-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3def-143">See also</span></span>

- [<span data-ttu-id="b3def-144">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3def-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="b3def-145">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3def-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b3def-146">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="b3def-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b3def-147">Operatore Or</span><span class="sxs-lookup"><span data-stu-id="b3def-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="b3def-148">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="b3def-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="b3def-149">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3def-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
