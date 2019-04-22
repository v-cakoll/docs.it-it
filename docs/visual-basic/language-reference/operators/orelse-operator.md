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
ms.openlocfilehash: 28d1481b71979936bb16a2ecfb1140d85a674ef7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816395"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="5e0e7-102">Operatore OrElse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e0e7-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="5e0e7-103">Esegue una disgiunzione logica inclusiva su due espressioni di corto circuito.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e0e7-104">Syntax</span></span>  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="5e0e7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5e0e7-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="5e0e7-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-106">Required.</span></span> <span data-ttu-id="5e0e7-107">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5e0e7-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="5e0e7-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-108">Required.</span></span> <span data-ttu-id="5e0e7-109">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5e0e7-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="5e0e7-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-110">Required.</span></span> <span data-ttu-id="5e0e7-111">Qualsiasi espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5e0e7-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e0e7-112">Note</span><span class="sxs-lookup"><span data-stu-id="5e0e7-112">Remarks</span></span>  
 <span data-ttu-id="5e0e7-113">Un'operazione logica viene detto *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="5e0e7-114">Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario per valutare la seconda espressione, in quanto non può modificare il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="5e0e7-115">Corto circuito può migliorare le prestazioni se l'espressione ignorato è complesso, o se prevede le chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="5e0e7-116">Se una o entrambe le espressioni restituiscono `True`, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="5e0e7-117">La tabella seguente illustra come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="5e0e7-118">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="5e0e7-118">If `expression1` is</span></span>|<span data-ttu-id="5e0e7-119">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="5e0e7-119">And `expression2` is</span></span>|<span data-ttu-id="5e0e7-120">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="5e0e7-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="5e0e7-121">(non valutati)</span><span class="sxs-lookup"><span data-stu-id="5e0e7-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="5e0e7-122">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="5e0e7-122">Data Types</span></span>  
 <span data-ttu-id="5e0e7-123">Il `OrElse` operatore è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="5e0e7-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="5e0e7-124">Visual Basic consente di convertire ogni operando in base alle esigenze per `Boolean` ed esegue l'operazione interamente in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-124">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="5e0e7-125">Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` per quel tipo.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="5e0e7-126">Questa operazione può generare un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-126">This could produce unexpected behavior.</span></span> <span data-ttu-id="5e0e7-127">Ad esempio, `5 OrElse 12` comporterà `–1` quando convertito in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-127">For example, `5 OrElse 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5e0e7-128">Overload</span><span class="sxs-lookup"><span data-stu-id="5e0e7-128">Overloading</span></span>  
 <span data-ttu-id="5e0e7-129">Il [operatore Or](../../../visual-basic/language-reference/operators/or-operator.md) e il [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) può essere *sottoposti a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di tale classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-129">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5e0e7-130">L'overload di `Or` e `IsTrue` operatori influisce sul comportamento del `OrElse` operatore.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="5e0e7-131">Se il codice usi `OrElse` in una classe o struttura che esegue l'overload `Or` e `IsTrue`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="5e0e7-132">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5e0e7-132">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e0e7-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e0e7-133">Example</span></span>  
 <span data-ttu-id="5e0e7-134">L'esempio seguente usa il `OrElse` operatore per eseguire la disgiunzione logica tra due espressioni.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="5e0e7-135">Il risultato è un `Boolean` valore che rappresenta se viene soddisfatta una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="5e0e7-136">Se la prima espressione è `True`, la seconda non viene valutata.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="5e0e7-137">Nell'esempio precedente produce i risultati dei `True`, `True`, e `False` rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="5e0e7-138">Nel calcolo della `firstCheck`, la seconda espressione non viene valutata il primo è già `True`.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="5e0e7-139">Tuttavia, la seconda espressione viene valutata nel calcolo della `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e0e7-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e0e7-140">Example</span></span>  
 <span data-ttu-id="5e0e7-141">L'esempio seguente mostra un `If`... `Then` istruzione che contiene due chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="5e0e7-142">Se la prima chiamata restituisce `True`, la seconda procedura non viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="5e0e7-143">Ciò potrebbe produrre risultati imprevisti se la seconda procedura esegue le attività importanti che devono essere sempre eseguite quando viene eseguito in questa sezione del codice.</span><span class="sxs-lookup"><span data-stu-id="5e0e7-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="5e0e7-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e0e7-144">See also</span></span>

- [<span data-ttu-id="5e0e7-145">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e0e7-145">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="5e0e7-146">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e0e7-146">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5e0e7-147">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="5e0e7-147">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5e0e7-148">Operatore Or</span><span class="sxs-lookup"><span data-stu-id="5e0e7-148">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="5e0e7-149">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="5e0e7-149">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="5e0e7-150">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e0e7-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
