---
title: Istruzione While...End While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 7ea0814c587f65ddc1f114d2314ac7147143d40d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965805"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="e337c-102">Istruzione While...End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e337c-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="e337c-103">Esegue una serie di istruzioni purché una determinata condizione sia `True`.</span><span class="sxs-lookup"><span data-stu-id="e337c-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e337c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e337c-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="e337c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e337c-105">Parts</span></span>  
  
|<span data-ttu-id="e337c-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e337c-106">Term</span></span>|<span data-ttu-id="e337c-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e337c-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="e337c-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="e337c-108">Required.</span></span> <span data-ttu-id="e337c-109">`Boolean`espressione.</span><span class="sxs-lookup"><span data-stu-id="e337c-109">`Boolean` expression.</span></span> <span data-ttu-id="e337c-110">Se `condition` `False`è `Nothing`, Visual Basic lo considera come.</span><span class="sxs-lookup"><span data-stu-id="e337c-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="e337c-111">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e337c-111">Optional.</span></span> <span data-ttu-id="e337c-112">Una o più istruzioni che `While`seguono, che vengono eseguite `condition` ogni `True`volta è.</span><span class="sxs-lookup"><span data-stu-id="e337c-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="e337c-113">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e337c-113">Optional.</span></span> <span data-ttu-id="e337c-114">Trasferisce il controllo all'iterazione successiva `While` del blocco.</span><span class="sxs-lookup"><span data-stu-id="e337c-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="e337c-115">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e337c-115">Optional.</span></span> <span data-ttu-id="e337c-116">Trasferisce il controllo all' `While` esterno del blocco.</span><span class="sxs-lookup"><span data-stu-id="e337c-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="e337c-117">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="e337c-117">Required.</span></span> <span data-ttu-id="e337c-118">Termina la definizione del blocco `While`.</span><span class="sxs-lookup"><span data-stu-id="e337c-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e337c-119">Note</span><span class="sxs-lookup"><span data-stu-id="e337c-119">Remarks</span></span>  
 <span data-ttu-id="e337c-120">Utilizzare una `While...End While` struttura quando si desidera ripetere un set di istruzioni per un numero indefinito di volte, purché rimanga `True`una condizione.</span><span class="sxs-lookup"><span data-stu-id="e337c-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="e337c-121">Se si desidera maggiore flessibilità con la posizione in cui si testa la condizione o il risultato per il test, è preferibile [eseguire... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e337c-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="e337c-122">Se si desidera ripetere le istruzioni impostando il numero di volte, [per... L'istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="e337c-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e337c-123">La `While` parola chiave viene usata anche nel. [.. Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), [clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) e [clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e337c-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="e337c-124">Se `condition` `statements` `End While` è `True`, tutto l'esecuzione fino a quando non viene rilevata l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="e337c-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="e337c-125">Il `While` controllo viene quindi restituito all'istruzione e `condition` viene di nuovo controllata.</span><span class="sxs-lookup"><span data-stu-id="e337c-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="e337c-126">Se `condition` è ancora `True`, il processo viene ripetuto.</span><span class="sxs-lookup"><span data-stu-id="e337c-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="e337c-127">Se è `False`, il controllo passa all'istruzione che segue l' `End While` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e337c-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="e337c-128">L' `While` istruzione controlla sempre la condizione prima di avviare il ciclo.</span><span class="sxs-lookup"><span data-stu-id="e337c-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="e337c-129">Il ciclo continua finché la condizione rimane `True`.</span><span class="sxs-lookup"><span data-stu-id="e337c-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="e337c-130">Se `condition` è`False` la prima volta che si immette il ciclo, non viene eseguito neanche una volta.</span><span class="sxs-lookup"><span data-stu-id="e337c-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="e337c-131">Il `condition` risultato è in genere dovuto a un confronto di due valori, ma può essere qualsiasi espressione che restituisce un valore di [tipo di dati booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`).</span><span class="sxs-lookup"><span data-stu-id="e337c-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="e337c-132">Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato `Boolean`convertito in.</span><span class="sxs-lookup"><span data-stu-id="e337c-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="e337c-133">È possibile annidare `While` i cicli inserendo un ciclo all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="e337c-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="e337c-134">È anche possibile annidare diversi tipi di strutture di controllo tra loro.</span><span class="sxs-lookup"><span data-stu-id="e337c-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="e337c-135">Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="e337c-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="e337c-136">Esci da</span><span class="sxs-lookup"><span data-stu-id="e337c-136">Exit While</span></span>  
 <span data-ttu-id="e337c-137">L'istruzione [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) può fornire un altro modo per uscire `While` da un ciclo.</span><span class="sxs-lookup"><span data-stu-id="e337c-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="e337c-138">`Exit While`trasferisce immediatamente il controllo all'istruzione che segue `End While` l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="e337c-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="e337c-139">In genere si `Exit While` USA dopo la valutazione di una determinata condizione, ad esempio `If...Then...Else` in una struttura.</span><span class="sxs-lookup"><span data-stu-id="e337c-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="e337c-140">Potrebbe essere necessario uscire da un ciclo se viene rilevata una condizione che rende superfluo o Impossibile continuare l'iterazione, ad esempio un valore errato o una richiesta di terminazione.</span><span class="sxs-lookup"><span data-stu-id="e337c-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="e337c-141">È possibile usare `Exit While` quando si esegue il test di una condizione che può causare un *ciclo infinito*, ovvero un ciclo che può eseguire un numero di volte molto grande o addirittura infinito.</span><span class="sxs-lookup"><span data-stu-id="e337c-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="e337c-142">È quindi possibile usare `Exit While` per eseguire l'escape del ciclo.</span><span class="sxs-lookup"><span data-stu-id="e337c-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="e337c-143">È possibile inserire un numero qualsiasi `Exit While` di istruzioni `While` in qualsiasi punto del ciclo.</span><span class="sxs-lookup"><span data-stu-id="e337c-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="e337c-144">Quando viene utilizzato all' `While` interno di `Exit While` cicli annidati, trasferisce il controllo al di fuori del ciclo più interno e al successivo livello di nidificazione.</span><span class="sxs-lookup"><span data-stu-id="e337c-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="e337c-145">L' `Continue While` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo.</span><span class="sxs-lookup"><span data-stu-id="e337c-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="e337c-146">Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e337c-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e337c-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="e337c-147">Example</span></span>  
 <span data-ttu-id="e337c-148">Nell'esempio seguente, le istruzioni del ciclo continuano a essere eseguite fino a quando `index` la variabile non è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="e337c-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="e337c-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="e337c-149">Example</span></span>  
 <span data-ttu-id="e337c-150">Nell'esempio seguente viene illustrato l'utilizzo delle `Continue While` istruzioni e. `Exit While`</span><span class="sxs-lookup"><span data-stu-id="e337c-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="e337c-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="e337c-151">Example</span></span>  
 <span data-ttu-id="e337c-152">Nell'esempio seguente vengono lette tutte le righe in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="e337c-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="e337c-153">Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> oggetto che legge i caratteri.</span><span class="sxs-lookup"><span data-stu-id="e337c-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="e337c-154">Nella condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo di `StreamReader` determina se il file contiene caratteri aggiuntivi. `While`</span><span class="sxs-lookup"><span data-stu-id="e337c-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="e337c-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e337c-155">See also</span></span>

- [<span data-ttu-id="e337c-156">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="e337c-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="e337c-157">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="e337c-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="e337c-158">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="e337c-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="e337c-159">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="e337c-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="e337c-160">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="e337c-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="e337c-161">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="e337c-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="e337c-162">Istruzione Continue</span><span class="sxs-lookup"><span data-stu-id="e337c-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
