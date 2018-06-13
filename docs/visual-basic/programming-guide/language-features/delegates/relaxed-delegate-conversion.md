---
title: Conversione di tipo relaxed del delegato (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: c4a41bf74716a6ea7d3c1139651834acccf27657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650829"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="bb5f9-102">Conversione di tipo relaxed del delegato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb5f9-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="bb5f9-103">Conversione di tipo relaxed del delegato consente di assegnare subroutine e funzioni a delegati o gestori anche quando le firme non sono identiche.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="bb5f9-104">Pertanto, l'associazione di delegati diventa coerente con l'associazione già consentita per le chiamate di metodo.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="bb5f9-105">Parametri e tipo restituito</span><span class="sxs-lookup"><span data-stu-id="bb5f9-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="bb5f9-106">Al posto di corrispondenza esatta delle firme, conversione di tipo relaxed richiede che le condizioni seguenti quando `Option Strict` è impostato su `On`:</span><span class="sxs-lookup"><span data-stu-id="bb5f9-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="bb5f9-107">Deve esistere una conversione dal tipo di dati di ogni parametro del delegato al tipo di dati del parametro corrispondente della funzione assegnata o `Sub`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="bb5f9-108">Nell'esempio seguente, il delegato `Del1` dispone di un parametro, un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="bb5f9-109">Parametro `m` nell'espressione lambda assegnata espressioni devono avere un tipo di dati per cui è disponibile una conversione da `Integer`, ad esempio `Long` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     <span data-ttu-id="bb5f9-110">Conversioni di restrizione sono consentite solo quando `Option Strict` è impostato su `Off`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   <span data-ttu-id="bb5f9-111">Deve esistere una conversione widening nella direzione opposta dal tipo restituito della funzione assegnata o `Sub` per il tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="bb5f9-112">Negli esempi seguenti, il corpo di ogni espressione lambda assegnata deve restituire un tipo di dati che si amplia in `Integer` perché il tipo restituito di `del1` è `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 <span data-ttu-id="bb5f9-113">Se `Option Strict` è impostato su `Off`, l'ampliamento restrizione è stata rimossa in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="bb5f9-114">L'omissione di specifiche di parametro</span><span class="sxs-lookup"><span data-stu-id="bb5f9-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="bb5f9-115">Delegati di tipo relaxed consentono anche di omettere completamente le specifiche dei parametri nel metodo assegnato:</span><span class="sxs-lookup"><span data-stu-id="bb5f9-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 <span data-ttu-id="bb5f9-116">Si noti che non è possibile specificare alcuni parametri e omettere gli altri.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 <span data-ttu-id="bb5f9-117">La possibilità di omettere i parametri è utile in una situazione ad esempio la definizione di un gestore eventi, in cui sono coinvolti diversi parametri complessi.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="bb5f9-118">Non vengono utilizzati gli argomenti per alcuni gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="bb5f9-119">Invece, il gestore accede direttamente lo stato del controllo in cui è registrato l'evento e gli argomenti vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="bb5f9-120">Delegati di tipo relaxed consentono di omettere gli argomenti in tali dichiarazioni quando non risultano ambiguità.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="bb5f9-121">Nell'esempio seguente, il metodo specificato completamente `OnClick` può essere riscritta come `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="bb5f9-122">Esempi di AddressOf</span><span class="sxs-lookup"><span data-stu-id="bb5f9-122">AddressOf Examples</span></span>  
 <span data-ttu-id="bb5f9-123">Espressioni lambda vengono utilizzate negli esempi precedenti in modo semplice visualizzare le relazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="bb5f9-124">Tuttavia, le stesse conversioni di tipo relaxed sono consentite per le assegnazioni di delegato che utilizzano `AddressOf`, `Handles`, o `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="bb5f9-125">Nell'esempio seguente, le funzioni `f1`, `f2`, `f3`, e `f4` può essere assegnato a `Del1`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 <span data-ttu-id="bb5f9-126">Nell'esempio seguente è valido solo quando `Option Strict` è impostato su `Off`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="bb5f9-127">Eliminazione di elementi restituiti da funzioni</span><span class="sxs-lookup"><span data-stu-id="bb5f9-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="bb5f9-128">Conversione di tipo relaxed del delegato consente di assegnare una funzione da un `Sub` delegato, in modo efficace, ignorando il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="bb5f9-129">Tuttavia, non è possibile assegnare un `Sub` a un delegato della funzione.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="bb5f9-130">Nell'esempio seguente, l'indirizzo della funzione `doubler` viene assegnato a `Sub` delegato `Del3`.</span><span class="sxs-lookup"><span data-stu-id="bb5f9-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bb5f9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb5f9-131">See Also</span></span>  
 [<span data-ttu-id="bb5f9-132">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="bb5f9-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="bb5f9-133">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="bb5f9-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="bb5f9-134">Delegati</span><span class="sxs-lookup"><span data-stu-id="bb5f9-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="bb5f9-135">Procedura: Passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb5f9-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [<span data-ttu-id="bb5f9-136">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="bb5f9-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="bb5f9-137">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="bb5f9-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
