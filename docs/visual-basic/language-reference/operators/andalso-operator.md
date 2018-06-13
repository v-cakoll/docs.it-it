---
title: Operatore AndAlso (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 549d14cc35d285ac2e4a02a37dd201cc669c5627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604080"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="913a2-102">Operatore AndAlso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="913a2-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="913a2-103">Esegue una congiunzione logica su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="913a2-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="913a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="913a2-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="913a2-105">Parti</span><span class="sxs-lookup"><span data-stu-id="913a2-105">Parts</span></span>  
  
|<span data-ttu-id="913a2-106">Termine</span><span class="sxs-lookup"><span data-stu-id="913a2-106">Term</span></span>|<span data-ttu-id="913a2-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="913a2-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="913a2-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="913a2-108">Required.</span></span> <span data-ttu-id="913a2-109">Qualsiasi espressione `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="913a2-109">Any `Boolean` expression.</span></span> <span data-ttu-id="913a2-110">Il risultato è il `Boolean` risultato del confronto di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="913a2-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="913a2-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="913a2-111">Required.</span></span> <span data-ttu-id="913a2-112">Qualsiasi espressione `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="913a2-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="913a2-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="913a2-113">Required.</span></span> <span data-ttu-id="913a2-114">Qualsiasi espressione `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="913a2-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="913a2-115">Note</span><span class="sxs-lookup"><span data-stu-id="913a2-115">Remarks</span></span>  
 <span data-ttu-id="913a2-116">Viene definita un'operazione logica *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="913a2-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="913a2-117">Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, è necessario valutare l'espressione della seconda, perché non è possibile modificare il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="913a2-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="913a2-118">Corto circuito può migliorare le prestazioni se l'espressione ignorata è complessa o se include le chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="913a2-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="913a2-119">Se entrambe le espressioni restituiscono `True`, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="913a2-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="913a2-120">Nella tabella seguente viene illustrato come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="913a2-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="913a2-121">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="913a2-121">If `expression1` is</span></span>|<span data-ttu-id="913a2-122">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="913a2-122">And `expression2` is</span></span>|<span data-ttu-id="913a2-123">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="913a2-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="913a2-124">(non valutato)</span><span class="sxs-lookup"><span data-stu-id="913a2-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="913a2-125">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="913a2-125">Data Types</span></span>  
 <span data-ttu-id="913a2-126">Il `AndAlso` è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="913a2-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="913a2-127">Visual Basic converte ogni operando in base alle esigenze per `Boolean` e l'operazione viene eseguita interamente in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="913a2-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="913a2-128">Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="913a2-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="913a2-129">Questa operazione può generare un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="913a2-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="913a2-130">Ad esempio, `5 AndAlso 12` comporta `–1` quando convertito in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="913a2-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="913a2-131">Overload</span><span class="sxs-lookup"><span data-stu-id="913a2-131">Overloading</span></span>  
 <span data-ttu-id="913a2-132">Il [operatore e](../../../visual-basic/language-reference/operators/and-operator.md) e [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) può essere *overload*, il che significa che una classe o struttura possibile ridefinirne il comportamento quando il tipo di oggetto che dispone di un operando classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="913a2-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="913a2-133">L'overload di `And` e `IsFalse` operatori influisce sul comportamento del `AndAlso` operatore.</span><span class="sxs-lookup"><span data-stu-id="913a2-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="913a2-134">Se il codice utilizza `AndAlso` in una classe o struttura che esegue l'overload `And` e `IsFalse`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="913a2-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="913a2-135">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="913a2-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="913a2-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="913a2-136">Example</span></span>  
 <span data-ttu-id="913a2-137">L'esempio seguente usa il `AndAlso` operatore per eseguire una congiunzione logica tra due espressioni.</span><span class="sxs-lookup"><span data-stu-id="913a2-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="913a2-138">Il risultato è un `Boolean` valore che indica se l'intera espressione di congiunzione è true.</span><span class="sxs-lookup"><span data-stu-id="913a2-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="913a2-139">Se la prima espressione è `False`, la seconda non viene valutata.</span><span class="sxs-lookup"><span data-stu-id="913a2-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 <span data-ttu-id="913a2-140">Nell'esempio precedente produce i risultati di `True`, `False`, e `False`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="913a2-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="913a2-141">Nel calcolo della `secondCheck`, la seconda espressione non viene valutata in quanto il primo è già `False`.</span><span class="sxs-lookup"><span data-stu-id="913a2-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="913a2-142">Tuttavia, la seconda espressione viene valutata nel calcolo della `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="913a2-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="913a2-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="913a2-143">Example</span></span>  
 <span data-ttu-id="913a2-144">Nell'esempio seguente un `Function` routine che esegue la ricerca di un determinato valore tra gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="913a2-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="913a2-145">Se la matrice è vuota o se viene superata la lunghezza della matrice, il `While` istruzione non testa l'elemento della matrice rispetto al valore di ricerca.</span><span class="sxs-lookup"><span data-stu-id="913a2-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="913a2-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="913a2-146">See Also</span></span>  
 [<span data-ttu-id="913a2-147">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="913a2-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="913a2-148">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="913a2-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="913a2-149">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="913a2-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="913a2-150">Operatore And</span><span class="sxs-lookup"><span data-stu-id="913a2-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)  
 [<span data-ttu-id="913a2-151">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="913a2-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="913a2-152">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="913a2-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
