---
title: Assoluta conversione delegato (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 016c808145f7faba26a288cd5075f10d7f5279d5
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="03139-102">Conversione di tipo relaxed del delegato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03139-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="03139-103">Conversione di tipo relaxed del delegato consente di assegnare subroutine e funzioni ai delegati o gestori anche quando le firme non sono identiche.</span><span class="sxs-lookup"><span data-stu-id="03139-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="03139-104">Pertanto, l'associazione ai delegati diventa coerente con l'associazione già consentita per le chiamate ai metodi.</span><span class="sxs-lookup"><span data-stu-id="03139-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="03139-105">Parametri e tipo restituito</span><span class="sxs-lookup"><span data-stu-id="03139-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="03139-106">Al posto della corrispondenza esatta delle firme, conversione di tipo relaxed richiede che siano soddisfatte le condizioni seguenti quando `Option Strict` è impostato su `On`:</span><span class="sxs-lookup"><span data-stu-id="03139-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="03139-107">Deve esistere una conversione dal tipo di dati di ogni parametro del delegato al tipo di dati del parametro corrispondente della funzione assegnata o `Sub`.</span><span class="sxs-lookup"><span data-stu-id="03139-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="03139-108">Nell'esempio seguente, il delegato `Del1` dispone di un parametro, un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="03139-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="03139-109">Parametro `m` nell'espressione lambda assegnato le espressioni devono contenere un tipo di dati per cui è disponibile una conversione da `Integer`, ad esempio `Long` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="03139-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     <span data-ttu-id="03139-110">[!code-vb[VbVbalrRelaxedDelegates n.&1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-110">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
     <span data-ttu-id="03139-111">[!code-vb[VbVbalrRelaxedDelegates n.&2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-111">[!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span></span>  
  
     <span data-ttu-id="03139-112">Le conversioni sono consentite solo quando `Option Strict` è impostato su `Off`.</span><span class="sxs-lookup"><span data-stu-id="03139-112">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     <span data-ttu-id="03139-113">[!code-vb[VbVbalrRelaxedDelegates n.&8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-113">[!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span></span>  
  
-   <span data-ttu-id="03139-114">Deve esistere una conversione nella direzione opposta dal tipo restituito della funzione assegnata o `Sub` per il tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="03139-114">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="03139-115">Negli esempi seguenti, il corpo di ogni espressione lambda assegnata deve restituire un tipo di dati che si amplia in `Integer` perché il tipo restituito di `del1` è `Integer`.</span><span class="sxs-lookup"><span data-stu-id="03139-115">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     <span data-ttu-id="03139-116">[!code-vb[VbVbalrRelaxedDelegates n.&3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-116">[!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span></span>  
  
 <span data-ttu-id="03139-117">Se `Option Strict` è impostato su `Off`, le conversioni di restrizione è stata rimossa in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="03139-117">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 <span data-ttu-id="03139-118">[!code-vb[VbVbalrRelaxedDelegates n.&4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-118">[!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span></span>  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="03139-119">L'omissione di specifiche di parametro</span><span class="sxs-lookup"><span data-stu-id="03139-119">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="03139-120">Delegati di tipo relaxed consentono inoltre di omettere completamente le specifiche dei parametri nel metodo assegnato:</span><span class="sxs-lookup"><span data-stu-id="03139-120">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 <span data-ttu-id="03139-121">[!code-vb[VbVbalrRelaxedDelegates n.&5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-121">[!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span></span>  
  
 <span data-ttu-id="03139-122">[!code-vb[6 VbVbalrRelaxedDelegates](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-122">[!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span></span>  
  
 <span data-ttu-id="03139-123">Si noti che non è possibile specificare alcuni parametri e omettere gli altri.</span><span class="sxs-lookup"><span data-stu-id="03139-123">Note that you cannot specify some parameters and omit others.</span></span>  
  
 <span data-ttu-id="03139-124">[!code-vb[VbVbalrRelaxedDelegates&#15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-124">[!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span></span>  
  
 <span data-ttu-id="03139-125">La possibilità di omettere i parametri è utile in una situazione simile definisce un gestore eventi, in cui sono coinvolti diversi parametri complessi.</span><span class="sxs-lookup"><span data-stu-id="03139-125">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="03139-126">Gli argomenti per alcuni gestori di eventi non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="03139-126">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="03139-127">Al contrario, il gestore accede direttamente lo stato del controllo in cui viene registrato l'evento e gli argomenti vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="03139-127">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="03139-128">Delegati di tipo relaxed consentono di omettere gli argomenti in tali dichiarazioni quando non risultano ambiguità.</span><span class="sxs-lookup"><span data-stu-id="03139-128">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="03139-129">Nell'esempio seguente, il metodo specificato completamente `OnClick` può essere riscritta come `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="03139-129">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="03139-130">Esempi di AddressOf</span><span class="sxs-lookup"><span data-stu-id="03139-130">AddressOf Examples</span></span>  
 <span data-ttu-id="03139-131">Espressioni lambda vengono utilizzate negli esempi precedenti in modo semplice visualizzare le relazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="03139-131">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="03139-132">Tuttavia, le stesse conversioni di tipo relaxed sono consentite per le assegnazioni di delegato che utilizzano `AddressOf`, `Handles`, o `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="03139-132">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="03139-133">Nell'esempio seguente, le funzioni `f1`, `f2`, `f3`, e `f4` può essere assegnato a `Del1`.</span><span class="sxs-lookup"><span data-stu-id="03139-133">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 <span data-ttu-id="03139-134">[!code-vb[VbVbalrRelaxedDelegates n.&1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-134">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
 <span data-ttu-id="03139-135">[!code-vb[VbVbalrRelaxedDelegates&#7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-135">[!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span></span>  
  
 <span data-ttu-id="03139-136">[!code-vb[9 VbVbalrRelaxedDelegates](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-136">[!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span></span>  
  
 <span data-ttu-id="03139-137">Nell'esempio seguente è valido solo quando `Option Strict` è impostato su `Off`.</span><span class="sxs-lookup"><span data-stu-id="03139-137">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 <span data-ttu-id="03139-138">[!code-vb[VbVbalrRelaxedDelegates&#14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-138">[!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span></span>  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="03139-139">Eliminazione di elementi restituiti dalla funzione</span><span class="sxs-lookup"><span data-stu-id="03139-139">Dropping Function Returns</span></span>  
 <span data-ttu-id="03139-140">Conversione di tipo relaxed del delegato consente di assegnare una funzione a un `Sub` delegato, ignorando efficacemente il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="03139-140">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="03139-141">Tuttavia, non è possibile assegnare un `Sub` a un delegato della funzione.</span><span class="sxs-lookup"><span data-stu-id="03139-141">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="03139-142">Nell'esempio seguente, l'indirizzo della funzione `doubler` viene assegnato a `Sub` delegare `Del3`.</span><span class="sxs-lookup"><span data-stu-id="03139-142">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 <span data-ttu-id="03139-143">[!code-vb[VbVbalrRelaxedDelegates&#10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-143">[!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span></span>  
  
 <span data-ttu-id="03139-144">[!code-vb[VbVbalrRelaxedDelegates&#11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="03139-144">[!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03139-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03139-145">See Also</span></span>  
 <span data-ttu-id="03139-146">[Espressioni lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="03139-146">[Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="03139-147"> [Ampliamento e restrizione conversioni](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="03139-147"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="03139-148"> [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="03139-148"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="03139-149"> [Procedura: passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="03139-149"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="03139-150"> [Inferenza del tipo locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="03139-150"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="03139-151"> [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="03139-151"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
