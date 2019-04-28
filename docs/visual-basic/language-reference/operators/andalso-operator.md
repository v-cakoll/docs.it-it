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
ms.openlocfilehash: 3876fd9c32d486b8ebecc9ee2428486a687a1624
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608320"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="36a58-102">Operatore AndAlso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36a58-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="36a58-103">Esegue la congiunzione logica su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="36a58-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36a58-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="36a58-105">Parti</span><span class="sxs-lookup"><span data-stu-id="36a58-105">Parts</span></span>  
  
|<span data-ttu-id="36a58-106">Termine</span><span class="sxs-lookup"><span data-stu-id="36a58-106">Term</span></span>|<span data-ttu-id="36a58-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="36a58-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="36a58-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="36a58-108">Required.</span></span> <span data-ttu-id="36a58-109">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="36a58-109">Any `Boolean` expression.</span></span> <span data-ttu-id="36a58-110">Il risultato è il `Boolean` risultato del confronto delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="36a58-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="36a58-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="36a58-111">Required.</span></span> <span data-ttu-id="36a58-112">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="36a58-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="36a58-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="36a58-113">Required.</span></span> <span data-ttu-id="36a58-114">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="36a58-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36a58-115">Note</span><span class="sxs-lookup"><span data-stu-id="36a58-115">Remarks</span></span>  
 <span data-ttu-id="36a58-116">Un'operazione logica viene detto *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="36a58-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="36a58-117">Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario per valutare la seconda espressione, in quanto non può modificare il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="36a58-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="36a58-118">Corto circuito può migliorare le prestazioni se l'espressione ignorato è complesso, o se prevede le chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="36a58-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="36a58-119">Se entrambe le espressioni restituiscono `True`, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="36a58-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="36a58-120">La tabella seguente illustra come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="36a58-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="36a58-121">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="36a58-121">If `expression1` is</span></span>|<span data-ttu-id="36a58-122">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="36a58-122">And `expression2` is</span></span>|<span data-ttu-id="36a58-123">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="36a58-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="36a58-124">(non valutati)</span><span class="sxs-lookup"><span data-stu-id="36a58-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="36a58-125">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="36a58-125">Data Types</span></span>  
 <span data-ttu-id="36a58-126">Il `AndAlso` operatore è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="36a58-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="36a58-127">Visual Basic consente di convertire ogni operando in base alle esigenze per `Boolean` ed esegue l'operazione interamente in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="36a58-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="36a58-128">Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` per quel tipo.</span><span class="sxs-lookup"><span data-stu-id="36a58-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="36a58-129">Questa operazione può generare un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="36a58-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="36a58-130">Ad esempio, `5 AndAlso 12` comporterà `–1` quando convertito in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="36a58-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="36a58-131">Overload</span><span class="sxs-lookup"><span data-stu-id="36a58-131">Overloading</span></span>  
 <span data-ttu-id="36a58-132">Il [operatore And](../../../visual-basic/language-reference/operators/and-operator.md) e il [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) può essere *sottoposti a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di oggetto che classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="36a58-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="36a58-133">L'overload di `And` e `IsFalse` operatori influisce sul comportamento del `AndAlso` operatore.</span><span class="sxs-lookup"><span data-stu-id="36a58-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="36a58-134">Se il codice usi `AndAlso` in una classe o struttura che esegue l'overload `And` e `IsFalse`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="36a58-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="36a58-135">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="36a58-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36a58-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="36a58-136">Example</span></span>  
 <span data-ttu-id="36a58-137">L'esempio seguente usa il `AndAlso` operatore per eseguire una congiunzione logica su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="36a58-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="36a58-138">Il risultato è un `Boolean` valore che indica se l'intera espressione di congiunzione è true.</span><span class="sxs-lookup"><span data-stu-id="36a58-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="36a58-139">Se la prima espressione è `False`, la seconda non viene valutata.</span><span class="sxs-lookup"><span data-stu-id="36a58-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="36a58-140">Nell'esempio precedente produce i risultati dei `True`, `False`, e `False`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="36a58-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="36a58-141">Nel calcolo della `secondCheck`, la seconda espressione non viene valutata il primo è già `False`.</span><span class="sxs-lookup"><span data-stu-id="36a58-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="36a58-142">Tuttavia, la seconda espressione viene valutata nel calcolo della `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="36a58-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36a58-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="36a58-143">Example</span></span>  
 <span data-ttu-id="36a58-144">L'esempio seguente mostra un `Function` procedure che esegue la ricerca per un determinato valore tra gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="36a58-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="36a58-145">Se la matrice è vuota o se viene superata la lunghezza della matrice, il `While` istruzione non testa l'elemento della matrice rispetto al valore di ricerca.</span><span class="sxs-lookup"><span data-stu-id="36a58-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="36a58-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36a58-146">See also</span></span>

- [<span data-ttu-id="36a58-147">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36a58-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="36a58-148">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="36a58-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="36a58-149">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="36a58-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="36a58-150">Operatore And</span><span class="sxs-lookup"><span data-stu-id="36a58-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="36a58-151">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="36a58-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="36a58-152">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="36a58-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
