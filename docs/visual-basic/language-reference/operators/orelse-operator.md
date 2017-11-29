---
title: Operatore OrElse (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47239a1d2b5b20f2b8cacc9b9185a0f95f63dc84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="b97a8-102">Operatore OrElse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b97a8-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="b97a8-103">Esegue la disgiunzione logica inclusiva su due espressioni di corto circuito.</span><span class="sxs-lookup"><span data-stu-id="b97a8-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b97a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b97a8-104">Syntax</span></span>  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="b97a8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b97a8-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b97a8-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b97a8-106">Required.</span></span> <span data-ttu-id="b97a8-107">Qualsiasi espressione `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="b97a8-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b97a8-108">Required.</span></span> <span data-ttu-id="b97a8-109">Qualsiasi espressione `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="b97a8-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b97a8-110">Required.</span></span> <span data-ttu-id="b97a8-111">Qualsiasi espressione `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b97a8-112">Note</span><span class="sxs-lookup"><span data-stu-id="b97a8-112">Remarks</span></span>  
 <span data-ttu-id="b97a8-113">Viene definita un'operazione logica *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="b97a8-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="b97a8-114">Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, è necessario valutare l'espressione della seconda, perché non è possibile modificare il risultato finale.</span><span class="sxs-lookup"><span data-stu-id="b97a8-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="b97a8-115">Corto circuito può migliorare le prestazioni se l'espressione ignorata è complessa o se include le chiamate di procedura.</span><span class="sxs-lookup"><span data-stu-id="b97a8-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="b97a8-116">Se una o entrambe le espressioni restituiscono `True`, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="b97a8-117">Nella tabella seguente viene illustrato come `result` è determinata.</span><span class="sxs-lookup"><span data-stu-id="b97a8-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="b97a8-118">Se `expression1` è</span><span class="sxs-lookup"><span data-stu-id="b97a8-118">If `expression1` is</span></span>|<span data-ttu-id="b97a8-119">E `expression2` è</span><span class="sxs-lookup"><span data-stu-id="b97a8-119">And `expression2` is</span></span>|<span data-ttu-id="b97a8-120">Il valore di `result` è</span><span class="sxs-lookup"><span data-stu-id="b97a8-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="b97a8-121">(non valutato)</span><span class="sxs-lookup"><span data-stu-id="b97a8-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="b97a8-122">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="b97a8-122">Data Types</span></span>  
 <span data-ttu-id="b97a8-123">Il `OrElse` è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b97a8-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="b97a8-124">Visual Basic converte ogni operando in base alle esigenze per `Boolean` e l'operazione viene eseguita interamente in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-124">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="b97a8-125">Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="b97a8-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="b97a8-126">Questa operazione può generare un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="b97a8-126">This could produce unexpected behavior.</span></span> <span data-ttu-id="b97a8-127">Ad esempio, `5 OrElse 12` comporta `–1` quando convertito in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-127">For example, `5 OrElse 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b97a8-128">Overload</span><span class="sxs-lookup"><span data-stu-id="b97a8-128">Overloading</span></span>  
 <span data-ttu-id="b97a8-129">Il [operatore o](../../../visual-basic/language-reference/operators/or-operator.md) e [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) può essere *overload*, il che significa che una classe o struttura possibile ridefinirne il comportamento quando il tipo di tale classe dispone di un operando o struttura.</span><span class="sxs-lookup"><span data-stu-id="b97a8-129">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b97a8-130">L'overload di `Or` e `IsTrue` operatori influisce sul comportamento del `OrElse` operatore.</span><span class="sxs-lookup"><span data-stu-id="b97a8-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="b97a8-131">Se il codice utilizza `OrElse` in una classe o struttura che esegue l'overload `Or` e `IsTrue`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="b97a8-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="b97a8-132">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b97a8-132">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b97a8-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="b97a8-133">Example</span></span>  
 <span data-ttu-id="b97a8-134">L'esempio seguente usa il `OrElse` operatore per eseguire la disgiunzione logica tra due espressioni.</span><span class="sxs-lookup"><span data-stu-id="b97a8-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="b97a8-135">Il risultato è un `Boolean` valore che rappresenta se viene soddisfatta una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="b97a8-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="b97a8-136">Se la prima espressione è `True`, la seconda non viene valutata.</span><span class="sxs-lookup"><span data-stu-id="b97a8-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 <span data-ttu-id="b97a8-137">Nell'esempio precedente produce i risultati di `True`, `True`, e `False` rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b97a8-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="b97a8-138">Nel calcolo della `firstCheck`, la seconda espressione non viene valutata in quanto il primo è già `True`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="b97a8-139">Tuttavia, la seconda espressione viene valutata nel calcolo della `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="b97a8-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b97a8-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="b97a8-140">Example</span></span>  
 <span data-ttu-id="b97a8-141">Nell'esempio seguente un `If`... `Then` istruzione contenente due chiamate di routine.</span><span class="sxs-lookup"><span data-stu-id="b97a8-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="b97a8-142">Se la prima chiamata restituisce `True`, la seconda procedura non viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="b97a8-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="b97a8-143">Questo può produrre risultati imprevisti se la seconda procedura esegue attività importanti che devono sempre essere eseguite durante l'esecuzione di questa sezione del codice.</span><span class="sxs-lookup"><span data-stu-id="b97a8-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b97a8-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b97a8-144">See Also</span></span>  
 [<span data-ttu-id="b97a8-145">Operatori logici e bit per bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b97a8-145">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="b97a8-146">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b97a8-146">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b97a8-147">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="b97a8-147">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b97a8-148">Operatore Or</span><span class="sxs-lookup"><span data-stu-id="b97a8-148">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)  
 [<span data-ttu-id="b97a8-149">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="b97a8-149">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="b97a8-150">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b97a8-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
