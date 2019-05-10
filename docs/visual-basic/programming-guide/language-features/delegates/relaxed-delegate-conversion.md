---
title: Conversione di tipo relaxed del delegato (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ac1246764d26d694d10b817b9195b13169d6d9be
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651260"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="a0227-102">Conversione di tipo relaxed del delegato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0227-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="a0227-103">Conversione di tipo relaxed del delegato consente di assegnare subroutine e funzioni a delegati o gestori anche quando le relative firme non sono identiche.</span><span class="sxs-lookup"><span data-stu-id="a0227-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="a0227-104">Pertanto, l'associazione ai delegati diventa coerenti con l'associazione già consentito per le chiamate ai metodi.</span><span class="sxs-lookup"><span data-stu-id="a0227-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="a0227-105">I parametri e il tipo restituito</span><span class="sxs-lookup"><span data-stu-id="a0227-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="a0227-106">Al posto di esatta corrispondenza della firma, la conversione di tipo "relaxed" richiede che essere soddisfatte le condizioni seguenti quando si `Option Strict` è impostata su `On`:</span><span class="sxs-lookup"><span data-stu-id="a0227-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="a0227-107">Deve esistere una conversione verso un dal tipo di dati di ogni parametro del delegato per il tipo di dati del parametro corrispondente della funzione assegnata o `Sub`.</span><span class="sxs-lookup"><span data-stu-id="a0227-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="a0227-108">Nell'esempio seguente, il delegato `Del1` ha un parametro, un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a0227-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="a0227-109">Parametro `m` nell'espressione lambda assegnata espressioni devono presentare un tipo di dati per il quale viene eseguita una conversione widening dal `Integer`, ad esempio `Long` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="a0227-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="a0227-110">Conversioni di Narrowing sono consentite solo quando `Option Strict` è impostata su `Off`.</span><span class="sxs-lookup"><span data-stu-id="a0227-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="a0227-111">Deve esistere una conversione verso un nella direzione opposta dal tipo restituito della funzione assegnata o `Sub` nel tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="a0227-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="a0227-112">Negli esempi seguenti, deve restituire il corpo di ogni espressione lambda assegnata a un tipo di dati che si amplia in `Integer` perché il tipo restituito di `del1` è `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a0227-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="a0227-113">Se `Option Strict` è impostata su `Off`, l'ampliamento restrizione è stata rimossa in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="a0227-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="a0227-114">Omettendo le specifiche dei parametri</span><span class="sxs-lookup"><span data-stu-id="a0227-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="a0227-115">Delegati di tipo relaxed consentono anche di omettere completamente le specifiche dei parametri nel metodo assegnato:</span><span class="sxs-lookup"><span data-stu-id="a0227-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="a0227-116">Si noti che non è possibile specificare alcuni parametri e omettere gli altri.</span><span class="sxs-lookup"><span data-stu-id="a0227-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="a0227-117">La possibilità di omettere i parametri è utile in situazioni, ad esempio definendo un gestore eventi, in cui sono coinvolti diversi parametri complessi.</span><span class="sxs-lookup"><span data-stu-id="a0227-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="a0227-118">Gli argomenti per alcuni gestori di eventi non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="a0227-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="a0227-119">Al contrario, il gestore accede direttamente lo stato del controllo in cui è registrato l'evento e gli argomenti vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="a0227-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="a0227-120">Delegati di tipo relaxed consentono di omettere gli argomenti nelle dichiarazioni di questo tipo quando nessun risultato le ambiguità.</span><span class="sxs-lookup"><span data-stu-id="a0227-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="a0227-121">Nell'esempio seguente, il metodo specificato completamente `OnClick` può essere riscritta come `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="a0227-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="a0227-122">Esempi di AddressOf</span><span class="sxs-lookup"><span data-stu-id="a0227-122">AddressOf Examples</span></span>  
 <span data-ttu-id="a0227-123">Le espressioni lambda vengono usate negli esempi precedenti in modo semplice visualizzare le relazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="a0227-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="a0227-124">Tuttavia, gli allentamenti stesso sono consentiti per le assegnazioni di delegato che usano `AddressOf`, `Handles`, o `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="a0227-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="a0227-125">Nell'esempio seguente, le funzioni `f1`, `f2`, `f3`, e `f4` possono essere assegnati a `Del1`.</span><span class="sxs-lookup"><span data-stu-id="a0227-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="a0227-126">L'esempio seguente è valido solo quando `Option Strict` è impostata su `Off`.</span><span class="sxs-lookup"><span data-stu-id="a0227-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="a0227-127">Eliminazione di elementi restituiti da funzioni</span><span class="sxs-lookup"><span data-stu-id="a0227-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="a0227-128">Conversione di tipo relaxed del delegato che consente di assegnare una funzione a un `Sub` delegato, in modo efficace, ignorando il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="a0227-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="a0227-129">Tuttavia, non è possibile assegnare un `Sub` a un delegato di funzione.</span><span class="sxs-lookup"><span data-stu-id="a0227-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="a0227-130">Nell'esempio seguente, l'indirizzo della funzione `doubler` viene assegnato a `Sub` delegare `Del3`.</span><span class="sxs-lookup"><span data-stu-id="a0227-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="a0227-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0227-131">See also</span></span>

- [<span data-ttu-id="a0227-132">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="a0227-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="a0227-133">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="a0227-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a0227-134">Delegati</span><span class="sxs-lookup"><span data-stu-id="a0227-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="a0227-135">Procedura: Passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0227-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="a0227-136">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="a0227-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="a0227-137">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="a0227-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
