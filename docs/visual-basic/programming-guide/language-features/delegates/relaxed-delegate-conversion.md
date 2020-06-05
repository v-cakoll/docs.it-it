---
title: Conversione di tipo relaxed del delegato
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: a581ffae77c496908d2e4e38df53491a54ae2ab8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410670"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="3d95f-102">Conversione di tipo relaxed del delegato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d95f-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="3d95f-103">La conversione di un delegato rilassato consente di assegnare subroutine e funzioni a delegati o gestori anche quando le relative firme non sono identiche.</span><span class="sxs-lookup"><span data-stu-id="3d95f-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="3d95f-104">Pertanto, l'associazione a delegati diventa coerente con l'associazione già consentita per le chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="3d95f-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="3d95f-105">Parametri e tipo restituito</span><span class="sxs-lookup"><span data-stu-id="3d95f-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="3d95f-106">Al posto della corrispondenza esatta della firma, la conversione rilassata richiede che vengano soddisfatte le condizioni seguenti quando `Option Strict` è impostato su `On` :</span><span class="sxs-lookup"><span data-stu-id="3d95f-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="3d95f-107">Deve esistere una conversione verso un tipo di dati più ampio dal tipo di dati di ogni parametro del delegato al tipo di dati del parametro corrispondente della funzione assegnata o `Sub` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="3d95f-108">Nell'esempio seguente, il delegato `Del1` ha un parametro, un oggetto `Integer` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="3d95f-109">`m`Il parametro nelle espressioni lambda assegnate deve avere un tipo di dati per il quale esiste una conversione verso un tipo di dati più ampio da `Integer` , ad esempio `Long` o `Double` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="3d95f-110">Le conversioni verso un tipo di caratteri più piccolo sono consentite solo quando `Option Strict` è impostato su `Off` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="3d95f-111">Una conversione verso un tipo di allargamento deve esistere nella direzione opposta dal tipo restituito della funzione assegnata o `Sub` al tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="3d95f-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="3d95f-112">Negli esempi seguenti, il corpo di ogni espressione lambda assegnata deve restituire un tipo di dati che viene ampliato a `Integer` perché il tipo restituito di `del1` è `Integer` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="3d95f-113">Se `Option Strict` è impostato su `Off` , la restrizione di ampliamento viene rimossa in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="3d95f-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="3d95f-114">Omissione delle specifiche di parametro</span><span class="sxs-lookup"><span data-stu-id="3d95f-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="3d95f-115">I delegati rilassati consentono inoltre di omettere completamente le specifiche dei parametri nel metodo assegnato:</span><span class="sxs-lookup"><span data-stu-id="3d95f-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="3d95f-116">Si noti che non è possibile specificare alcuni parametri e ometterne altri.</span><span class="sxs-lookup"><span data-stu-id="3d95f-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="3d95f-117">La possibilità di omettere i parametri è utile in una situazione come la definizione di un gestore eventi, in cui sono interessati diversi parametri complessi.</span><span class="sxs-lookup"><span data-stu-id="3d95f-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="3d95f-118">Gli argomenti per alcuni gestori di eventi non vengono usati.</span><span class="sxs-lookup"><span data-stu-id="3d95f-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="3d95f-119">Al contrario, il gestore accede direttamente allo stato del controllo in cui è registrato l'evento e ignora gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3d95f-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="3d95f-120">I delegati rilassati consentono di omettere gli argomenti in tali dichiarazioni quando non risultano ambiguità.</span><span class="sxs-lookup"><span data-stu-id="3d95f-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="3d95f-121">Nell'esempio seguente, il metodo completamente specificato `OnClick` può essere riscritto come `RelaxedOnClick` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="3d95f-122">Esempi di AddressOf</span><span class="sxs-lookup"><span data-stu-id="3d95f-122">AddressOf Examples</span></span>  
 <span data-ttu-id="3d95f-123">Le espressioni lambda vengono usate negli esempi precedenti per semplificare la visualizzazione delle relazioni tra i tipi.</span><span class="sxs-lookup"><span data-stu-id="3d95f-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="3d95f-124">Tuttavia, sono consentiti gli stessi relax per le assegnazioni di delegati che usano `AddressOf` , `Handles` o `AddHandler` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="3d95f-125">Nell'esempio seguente le funzioni `f1` ,, `f2` `f3` e `f4` possono essere assegnate a `Del1` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="3d95f-126">L'esempio seguente è valido solo quando `Option Strict` è impostato su `Off` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="3d95f-127">Eliminazione della funzione restituita</span><span class="sxs-lookup"><span data-stu-id="3d95f-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="3d95f-128">La conversione di un delegato rilassato consente di assegnare una funzione a un `Sub` delegato, ignorando in modo efficace il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="3d95f-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="3d95f-129">Tuttavia, non è possibile assegnare un oggetto `Sub` a un delegato di funzione.</span><span class="sxs-lookup"><span data-stu-id="3d95f-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="3d95f-130">Nell'esempio seguente, l'indirizzo della funzione `doubler` viene assegnato al `Sub` delegato `Del3` .</span><span class="sxs-lookup"><span data-stu-id="3d95f-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="3d95f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d95f-131">See also</span></span>

- [<span data-ttu-id="3d95f-132">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="3d95f-132">Lambda Expressions</span></span>](../procedures/lambda-expressions.md)
- [<span data-ttu-id="3d95f-133">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="3d95f-133">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="3d95f-134">Delegati</span><span class="sxs-lookup"><span data-stu-id="3d95f-134">Delegates</span></span>](index.md)
- [<span data-ttu-id="3d95f-135">Procedura: passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d95f-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="3d95f-136">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="3d95f-136">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="3d95f-137">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="3d95f-137">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
