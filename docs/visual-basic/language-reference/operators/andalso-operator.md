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
ms.openlocfilehash: a52f598c8a7c7a79b0f2436f1add7b3eb5d5261b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835224"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="e9934-102">Operatore AndAlso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9934-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="e9934-103">Esegue una congiunzione logica di corto circuito su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="e9934-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9934-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9934-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="e9934-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e9934-105">Parts</span></span>  
  
|<span data-ttu-id="e9934-106">Nome</span><span class="sxs-lookup"><span data-stu-id="e9934-106">Term</span></span>|<span data-ttu-id="e9934-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e9934-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="e9934-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e9934-108">Required.</span></span> <span data-ttu-id="e9934-109">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="e9934-109">Any `Boolean` expression.</span></span> <span data-ttu-id="e9934-110">Il risultato è il risultato `Boolean` del confronto delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="e9934-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="e9934-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e9934-111">Required.</span></span> <span data-ttu-id="e9934-112">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="e9934-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="e9934-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e9934-113">Required.</span></span> <span data-ttu-id="e9934-114">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="e9934-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9934-115">Note</span><span class="sxs-lookup"><span data-stu-id="e9934-115">Remarks</span></span>  
 <span data-ttu-id="e9934-116">Un'operazione logica viene detta *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione a seconda del risultato di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="e9934-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="e9934-117">Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario valutare la seconda espressione, perché non è in grado di modificare il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="e9934-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="e9934-118">Il cortocircuito può migliorare le prestazioni se l'espressione bypassata è complessa o se implica chiamate di routine.</span><span class="sxs-lookup"><span data-stu-id="e9934-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="e9934-119">Se entrambe le espressioni restituiscono `True`, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="e9934-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="e9934-120">Nella tabella seguente viene illustrato il modo in cui viene determinato `result`.</span><span class="sxs-lookup"><span data-stu-id="e9934-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="e9934-121">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="e9934-121">If `expression1` is</span></span>|<span data-ttu-id="e9934-122">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="e9934-122">And `expression2` is</span></span>|<span data-ttu-id="e9934-123">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="e9934-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="e9934-124">(non valutato)</span><span class="sxs-lookup"><span data-stu-id="e9934-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="e9934-125">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e9934-125">Data Types</span></span>  
 <span data-ttu-id="e9934-126">L'operatore `AndAlso` viene definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="e9934-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="e9934-127">Visual Basic converte ogni operando nel modo necessario per `Boolean` prima di valutare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="e9934-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="e9934-128">Se il risultato viene assegnato a un tipo numerico, Visual Basic lo converte da `Boolean` a tale tipo, in modo che `False` diventi `0` e `True` diventi `-1`.</span><span class="sxs-lookup"><span data-stu-id="e9934-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="e9934-129">Per altre informazioni, vedere [conversioni di tipi booleani](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="e9934-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="e9934-130">Overload</span><span class="sxs-lookup"><span data-stu-id="e9934-130">Overloading</span></span>  
 <span data-ttu-id="e9934-131">È possibile eseguire l' *Overload*dell' [operatore and](../../../visual-basic/language-reference/operators/and-operator.md) e dell' [operatore false](../../../visual-basic/language-reference/operators/isfalse-operator.md) , il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="e9934-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e9934-132">L'overload degli operatori `And` e `IsFalse` influiscono sul comportamento dell'operatore `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="e9934-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="e9934-133">Se il codice USA `AndAlso` su una classe o una struttura che esegue l'overload di `And` e `IsFalse`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="e9934-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="e9934-134">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e9934-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9934-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9934-135">Example</span></span>  
 <span data-ttu-id="e9934-136">Nell'esempio seguente viene usato l'operatore `AndAlso` per eseguire una congiunzione logica di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="e9934-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="e9934-137">Il risultato è un valore `Boolean` che indica se l'intera espressione conjointa è true.</span><span class="sxs-lookup"><span data-stu-id="e9934-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="e9934-138">Se la prima espressione è `False`, la seconda non viene valutata.</span><span class="sxs-lookup"><span data-stu-id="e9934-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="e9934-139">Nell'esempio precedente vengono prodotti rispettivamente i risultati `True`, `False` e `False`.</span><span class="sxs-lookup"><span data-stu-id="e9934-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="e9934-140">Nel calcolo di `secondCheck`, la seconda espressione non viene valutata perché il primo è già `False`.</span><span class="sxs-lookup"><span data-stu-id="e9934-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="e9934-141">Tuttavia, la seconda espressione viene valutata nel calcolo di `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="e9934-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9934-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9934-142">Example</span></span>  
 <span data-ttu-id="e9934-143">Nell'esempio seguente viene illustrata una procedura `Function` che cerca un valore specificato tra gli elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e9934-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="e9934-144">Se la matrice è vuota o se la lunghezza della matrice è stata superata, l'istruzione `While` non esegue il test dell'elemento della matrice rispetto al valore di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e9934-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="e9934-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9934-145">See also</span></span>

- [<span data-ttu-id="e9934-146">Operatori logici/bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9934-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="e9934-147">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e9934-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e9934-148">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="e9934-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e9934-149">Operatore And</span><span class="sxs-lookup"><span data-stu-id="e9934-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="e9934-150">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="e9934-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="e9934-151">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e9934-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
