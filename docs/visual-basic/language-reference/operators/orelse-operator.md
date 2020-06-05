---
title: Operatore OrElse
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
ms.openlocfilehash: 3095a11523eeb8ec531c7f312fca74d2a070c92f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401407"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="6ef89-102">Operatore OrElse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ef89-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="6ef89-103">Esegue una disgiunzione logica inclusiva di corto circuito su due espressioni.</span><span class="sxs-lookup"><span data-stu-id="6ef89-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ef89-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="6ef89-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6ef89-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="6ef89-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6ef89-106">Required.</span></span> <span data-ttu-id="6ef89-107">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="6ef89-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6ef89-108">Required.</span></span> <span data-ttu-id="6ef89-109">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="6ef89-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6ef89-110">Required.</span></span> <span data-ttu-id="6ef89-111">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef89-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="6ef89-112">Remarks</span></span>  
 <span data-ttu-id="6ef89-113">Un'operazione logica viene detta *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione a seconda del risultato di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="6ef89-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="6ef89-114">Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario valutare la seconda espressione, perché non è in grado di modificare il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="6ef89-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="6ef89-115">Il cortocircuito può migliorare le prestazioni se l'espressione bypassata è complessa o se implica chiamate di routine.</span><span class="sxs-lookup"><span data-stu-id="6ef89-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="6ef89-116">Se una o entrambe le espressioni restituiscono `True` , `result` è `True` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="6ef89-117">Nella tabella seguente viene illustrato come `result` determinare.</span><span class="sxs-lookup"><span data-stu-id="6ef89-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="6ef89-118">Se `expression1` è </span><span class="sxs-lookup"><span data-stu-id="6ef89-118">If `expression1` is</span></span>|<span data-ttu-id="6ef89-119">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="6ef89-119">And `expression2` is</span></span>|<span data-ttu-id="6ef89-120">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="6ef89-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="6ef89-121">(non valutato)</span><span class="sxs-lookup"><span data-stu-id="6ef89-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="6ef89-122">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6ef89-122">Data Types</span></span>  
 <span data-ttu-id="6ef89-123">L' `OrElse` operatore viene definito solo per il [tipo di dati Boolean](../data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="6ef89-123">The `OrElse` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="6ef89-124">Visual Basic converte ogni operando come necessario in `Boolean` prima di valutare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="6ef89-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="6ef89-125">Se il risultato viene assegnato a un tipo numerico, Visual Basic lo converte da `Boolean` a tale tipo, in modo che `False` diventi `0` e `True` diventi `-1` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="6ef89-126">Per altre informazioni, vedere [conversioni di tipi booleani](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="6ef89-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="6ef89-127">Overload</span><span class="sxs-lookup"><span data-stu-id="6ef89-127">Overloading</span></span>  
 <span data-ttu-id="6ef89-128">L' [operatore OR](or-operator.md) e l' [operatore IsTrue](istrue-operator.md) possono essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="6ef89-128">The [Or Operator](or-operator.md) and the [IsTrue Operator](istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6ef89-129">L'overload degli `Or` operatori e `IsTrue` influiscono sul comportamento dell' `OrElse` operatore.</span><span class="sxs-lookup"><span data-stu-id="6ef89-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="6ef89-130">Se il codice usa `OrElse` su una classe o una struttura che esegue l'overload `Or` di e `IsTrue` , assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="6ef89-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="6ef89-131">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6ef89-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ef89-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ef89-132">Example</span></span>  
 <span data-ttu-id="6ef89-133">Nell'esempio seguente viene usato l' `OrElse` operatore per eseguire la disgiunzione logica di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="6ef89-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="6ef89-134">Il risultato è un `Boolean` valore che indica se una delle due espressioni è true.</span><span class="sxs-lookup"><span data-stu-id="6ef89-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="6ef89-135">Se la prima espressione è `True` , la seconda non viene valutata.</span><span class="sxs-lookup"><span data-stu-id="6ef89-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="6ef89-136">Nell'esempio precedente vengono prodotti rispettivamente i risultati di `True` , `True` e `False` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="6ef89-137">Nel calcolo di `firstCheck` la seconda espressione non viene valutata perché il primo è già `True` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="6ef89-138">Tuttavia, la seconda espressione viene valutata nel calcolo di `secondCheck` .</span><span class="sxs-lookup"><span data-stu-id="6ef89-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ef89-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ef89-139">Example</span></span>  
 <span data-ttu-id="6ef89-140">Nell'esempio seguente viene illustrata un' `If` istruzione... `Then` contenente due chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="6ef89-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="6ef89-141">Se la prima chiamata restituisce `True` , la seconda procedura non viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="6ef89-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="6ef89-142">Questo potrebbe produrre risultati imprevisti se la seconda procedura esegue attività importanti che devono essere sempre eseguite quando viene eseguita questa sezione del codice.</span><span class="sxs-lookup"><span data-stu-id="6ef89-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="6ef89-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ef89-143">See also</span></span>

- [<span data-ttu-id="6ef89-144">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ef89-144">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="6ef89-145">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ef89-145">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="6ef89-146">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="6ef89-146">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="6ef89-147">Operatore Or</span><span class="sxs-lookup"><span data-stu-id="6ef89-147">Or Operator</span></span>](or-operator.md)
- [<span data-ttu-id="6ef89-148">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="6ef89-148">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="6ef89-149">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ef89-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
