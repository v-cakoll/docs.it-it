---
title: Istruzione Do...Loop (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 8c965dc89794654127e4b872c6aebf55c8902468
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525149"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="39ce7-102">Istruzione Do...Loop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39ce7-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="39ce7-103">Ripete un blocco di istruzioni finché un' `Boolean` condizione `True` o fino a quando la condizione diventa `True`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ce7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39ce7-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="39ce7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="39ce7-105">Parts</span></span>  
  
|<span data-ttu-id="39ce7-106">Termine</span><span class="sxs-lookup"><span data-stu-id="39ce7-106">Term</span></span>|<span data-ttu-id="39ce7-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ce7-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="39ce7-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="39ce7-108">Required.</span></span> <span data-ttu-id="39ce7-109">Inizia la definizione del `Do` ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="39ce7-110">Obbligatorio a meno che non sia usato `Until`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-110">Required unless `Until` is used.</span></span> <span data-ttu-id="39ce7-111">Ripetere il ciclo finché `condition` è `False`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="39ce7-112">Obbligatorio a meno che non sia usato `While`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-112">Required unless `While` is used.</span></span> <span data-ttu-id="39ce7-113">Ripetere il ciclo finché `condition` è `True`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="39ce7-114">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-114">Optional.</span></span> <span data-ttu-id="39ce7-115">`Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="39ce7-115">`Boolean` expression.</span></span> <span data-ttu-id="39ce7-116">Se `condition` viene `Nothing`, Visual Basic lo considera come `False`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="39ce7-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-117">Optional.</span></span> <span data-ttu-id="39ce7-118">Una o più istruzioni while o until, ripetute `condition` è `True`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="39ce7-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-119">Optional.</span></span> <span data-ttu-id="39ce7-120">Trasferisce il controllo all'iterazione successiva del `Do` ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="39ce7-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-121">Optional.</span></span> <span data-ttu-id="39ce7-122">Trasferisce il controllo fuori il `Do` ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="39ce7-123">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="39ce7-123">Required.</span></span> <span data-ttu-id="39ce7-124">Termina la definizione del `Do` ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39ce7-125">Note</span><span class="sxs-lookup"><span data-stu-id="39ce7-125">Remarks</span></span>  
 <span data-ttu-id="39ce7-126">Usare un `Do...Loop` struttura quando si desidera ripetere un set di istruzioni un numero indefinito di volte, fino a quando non viene soddisfatta una condizione.</span><span class="sxs-lookup"><span data-stu-id="39ce7-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="39ce7-127">Se si desidera ripetere un determinato numero di volte, le istruzioni di [per... Istruzione Next](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="39ce7-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="39ce7-128">È possibile usare `While` oppure `Until` per specificare `condition`, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="39ce7-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="39ce7-129">È possibile testare `condition` solo una volta, all'inizio o fine del ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="39ce7-130">Se si testano `condition` all'inizio del ciclo (nel `Do` istruzione), il ciclo potrebbe non funzionare ancora una volta.</span><span class="sxs-lookup"><span data-stu-id="39ce7-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="39ce7-131">Se si verifica alla fine del ciclo (nel `Loop` istruzione), il ciclo viene sempre eseguito almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="39ce7-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="39ce7-132">La condizione è dovuta in genere da un confronto tra due valori, ma può essere qualsiasi espressione che restituisce un [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valore (`True` o `False`).</span><span class="sxs-lookup"><span data-stu-id="39ce7-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="39ce7-133">Questo include i valori di altri tipi di dati, ad esempio tipi numerici, che sono stati convertiti in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="39ce7-134">È possibile annidare `Do` cicli inserendo un ciclo all'interno di altra.</span><span class="sxs-lookup"><span data-stu-id="39ce7-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="39ce7-135">È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di altro.</span><span class="sxs-lookup"><span data-stu-id="39ce7-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="39ce7-136">Per altre informazioni, vedere [strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="39ce7-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39ce7-137">Il `Do...Loop` struttura offre maggiore flessibilità di [mentre... L'istruzione end anche se](../../../visual-basic/language-reference/statements/while-end-while-statement.md) perché ti consente di decidere se terminare il ciclo quando `condition` diviene `True` o quando diventa `True`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="39ce7-138">Inoltre, consente di testare `condition` all'inizio o fine del ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="39ce7-139">Exit Do</span><span class="sxs-lookup"><span data-stu-id="39ce7-139">Exit Do</span></span>  
 <span data-ttu-id="39ce7-140">Il [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione può fornire un modo alternativo per chiudere un `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="39ce7-141">`Exit Do` Trasferisce il controllo all'istruzione che segue immediatamente il `Loop` istruzione.</span><span class="sxs-lookup"><span data-stu-id="39ce7-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="39ce7-142">`Exit Do` viene spesso usato dopo che viene valutata una condizione, ad esempio in un `If...Then...Else` struttura.</span><span class="sxs-lookup"><span data-stu-id="39ce7-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="39ce7-143">È possibile uscire da un ciclo se si rileva una condizione che rende inutili o impossibili da continuare a eseguire iterazioni, ad esempio un valore errato o una richiesta di terminazione.</span><span class="sxs-lookup"><span data-stu-id="39ce7-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="39ce7-144">Un uso del `Exit Do` consiste nel testare una condizione che potrebbe causare un' *ciclo infinito*, che è un ciclo che è stato possibile eseguire un numero elevato o persino infinito di volte.</span><span class="sxs-lookup"><span data-stu-id="39ce7-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="39ce7-145">È possibile usare `Exit Do` per interrompere il ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="39ce7-146">È possibile includere un numero qualsiasi di `Exit Do` istruzioni in un punto qualsiasi in un `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="39ce7-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="39ce7-147">Quando usata all'interno di cicli `Do` cicli, `Exit Do` trasferisce il controllo all'esterno del ciclo più interno e nel livello superiore successivo di annidamento.</span><span class="sxs-lookup"><span data-stu-id="39ce7-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39ce7-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="39ce7-148">Example</span></span>  
 <span data-ttu-id="39ce7-149">Nell'esempio seguente, le istruzioni nel ciclo continuano fino a incontrare il `index` variabile è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="39ce7-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="39ce7-150">Il `Until` clausola si trova alla fine del ciclo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="39ce7-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="39ce7-151">Example</span></span>  
 <span data-ttu-id="39ce7-152">L'esempio seguente usa un' `While` clausola WITH invece di un' `Until` clausola e `condition` viene verificata all'inizio del ciclo anziché alla fine.</span><span class="sxs-lookup"><span data-stu-id="39ce7-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="39ce7-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="39ce7-153">Example</span></span>  
 <span data-ttu-id="39ce7-154">Nell'esempio riportato di seguito `condition` Arresta il ciclo quando il `index` variabile è maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="39ce7-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="39ce7-155">Il `If` istruzione del ciclo, tuttavia, provoca la `Exit Do` istruzione per interrompere il ciclo quando la variabile di indice è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="39ce7-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="39ce7-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="39ce7-156">Example</span></span>  
 <span data-ttu-id="39ce7-157">Nell'esempio seguente legge tutte le righe in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="39ce7-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="39ce7-158">Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri.</span><span class="sxs-lookup"><span data-stu-id="39ce7-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="39ce7-159">Nel `Do...Loop` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo il `StreamReader` determina se sono presenti eventuali caratteri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="39ce7-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="39ce7-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39ce7-160">See also</span></span>
- [<span data-ttu-id="39ce7-161">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="39ce7-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="39ce7-162">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="39ce7-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="39ce7-163">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="39ce7-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="39ce7-164">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="39ce7-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="39ce7-165">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="39ce7-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="39ce7-166">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="39ce7-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
