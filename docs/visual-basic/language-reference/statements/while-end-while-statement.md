---
title: Istruzione While...End While
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 87f6fbd6147b6dbfbe08c93e862d58b9868f9201
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352743"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="61aef-102">Istruzione While...End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61aef-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="61aef-103">Esegue una serie di istruzioni purché una determinata condizione sia `True`.</span><span class="sxs-lookup"><span data-stu-id="61aef-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61aef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61aef-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="61aef-105">Parti</span><span class="sxs-lookup"><span data-stu-id="61aef-105">Parts</span></span>  
  
|<span data-ttu-id="61aef-106">Termine</span><span class="sxs-lookup"><span data-stu-id="61aef-106">Term</span></span>|<span data-ttu-id="61aef-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="61aef-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="61aef-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="61aef-108">Required.</span></span> <span data-ttu-id="61aef-109">espressione `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="61aef-109">`Boolean` expression.</span></span> <span data-ttu-id="61aef-110">Se `condition` è `Nothing`, Visual Basic lo considera `False`.</span><span class="sxs-lookup"><span data-stu-id="61aef-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="61aef-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="61aef-111">Optional.</span></span> <span data-ttu-id="61aef-112">Una o più istruzioni che seguono `While`, che vengono eseguite ogni volta che viene `True``condition`.</span><span class="sxs-lookup"><span data-stu-id="61aef-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="61aef-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="61aef-113">Optional.</span></span> <span data-ttu-id="61aef-114">Trasferisce il controllo all'iterazione successiva del blocco `While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="61aef-115">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="61aef-115">Optional.</span></span> <span data-ttu-id="61aef-116">Trasferisce il controllo all'esterno del blocco `While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="61aef-117">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="61aef-117">Required.</span></span> <span data-ttu-id="61aef-118">Termina la definizione del blocco `While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61aef-119">Note</span><span class="sxs-lookup"><span data-stu-id="61aef-119">Remarks</span></span>  
 <span data-ttu-id="61aef-120">Utilizzare una struttura `While...End While` quando si desidera ripetere un set di istruzioni per un numero indefinito di volte, purché rimanga `True`una condizione.</span><span class="sxs-lookup"><span data-stu-id="61aef-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="61aef-121">Se si desidera maggiore flessibilità con la posizione in cui si testa la condizione o il risultato per il test, è preferibile [eseguire... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="61aef-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="61aef-122">Se si desidera ripetere le istruzioni impostando il numero di volte, [per... L'istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="61aef-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61aef-123">La parola chiave `While` viene utilizzata anche nell' [attività do... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), [clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) e [clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="61aef-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="61aef-124">Se `condition` è `True`, tutti i `statements` eseguiti fino a quando non viene rilevata l'istruzione `End While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="61aef-125">Il controllo viene quindi restituito all'istruzione `While` e la `condition` viene nuovamente controllata.</span><span class="sxs-lookup"><span data-stu-id="61aef-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="61aef-126">Se `condition` è ancora `True`, il processo viene ripetuto.</span><span class="sxs-lookup"><span data-stu-id="61aef-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="61aef-127">Se è `False`, il controllo passa all'istruzione che segue l'istruzione `End While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="61aef-128">L'istruzione `While` controlla sempre la condizione prima di avviare il ciclo.</span><span class="sxs-lookup"><span data-stu-id="61aef-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="61aef-129">Il ciclo continua finché la condizione rimane `True`.</span><span class="sxs-lookup"><span data-stu-id="61aef-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="61aef-130">Se `condition` viene `False` quando si immette il ciclo per la prima volta, non viene eseguito neanche una volta.</span><span class="sxs-lookup"><span data-stu-id="61aef-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="61aef-131">Il `condition` in genere deriva da un confronto di due valori, ma può essere qualsiasi espressione che restituisce un valore [booleano di tipo di dati](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`).</span><span class="sxs-lookup"><span data-stu-id="61aef-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="61aef-132">Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato convertito in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="61aef-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="61aef-133">È possibile annidare `While` cicli inserendo un ciclo all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="61aef-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="61aef-134">È anche possibile annidare diversi tipi di strutture di controllo tra loro.</span><span class="sxs-lookup"><span data-stu-id="61aef-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="61aef-135">Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="61aef-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="61aef-136">Esci da</span><span class="sxs-lookup"><span data-stu-id="61aef-136">Exit While</span></span>  
 <span data-ttu-id="61aef-137">L'istruzione [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) può fornire un altro modo per uscire da un ciclo `While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="61aef-138">`Exit While` trasferisce immediatamente il controllo all'istruzione che segue l'istruzione `End While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="61aef-139">In genere si usa `Exit While` dopo la valutazione di una determinata condizione, ad esempio in una struttura di `If...Then...Else`.</span><span class="sxs-lookup"><span data-stu-id="61aef-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="61aef-140">Potrebbe essere necessario uscire da un ciclo se viene rilevata una condizione che rende superfluo o Impossibile continuare l'iterazione, ad esempio un valore errato o una richiesta di terminazione.</span><span class="sxs-lookup"><span data-stu-id="61aef-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="61aef-141">È possibile utilizzare `Exit While` quando si verifica una condizione che può causare un *ciclo infinito*, ovvero un ciclo che può eseguire un numero di volte molto grande o anche infinito.</span><span class="sxs-lookup"><span data-stu-id="61aef-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="61aef-142">È quindi possibile usare `Exit While` per eseguire l'escape del ciclo.</span><span class="sxs-lookup"><span data-stu-id="61aef-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="61aef-143">È possibile inserire un numero qualsiasi di istruzioni di `Exit While` in qualsiasi punto del ciclo `While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="61aef-144">Quando viene utilizzato all'interno di cicli di `While` annidati, `Exit While` trasferisce il controllo dal ciclo più interno al successivo livello di nidificazione.</span><span class="sxs-lookup"><span data-stu-id="61aef-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="61aef-145">L'istruzione `Continue While` trasferisce immediatamente il controllo all'iterazione successiva del ciclo.</span><span class="sxs-lookup"><span data-stu-id="61aef-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="61aef-146">Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="61aef-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61aef-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="61aef-147">Example</span></span>  
 <span data-ttu-id="61aef-148">Nell'esempio seguente, le istruzioni del ciclo continuano a essere eseguite fino a quando la variabile di `index` non è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="61aef-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="61aef-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="61aef-149">Example</span></span>  
 <span data-ttu-id="61aef-150">Nell'esempio seguente viene illustrato l'utilizzo delle istruzioni `Continue While` e `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="61aef-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="61aef-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="61aef-151">Example</span></span>  
 <span data-ttu-id="61aef-152">Nell'esempio seguente vengono lette tutte le righe in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="61aef-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="61aef-153">Il metodo <xref:System.IO.File.OpenText%2A> apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri.</span><span class="sxs-lookup"><span data-stu-id="61aef-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="61aef-154">Nella condizione `While` il <xref:System.IO.StreamReader.Peek%2A> metodo del `StreamReader` determina se il file contiene caratteri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="61aef-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="61aef-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61aef-155">See also</span></span>

- [<span data-ttu-id="61aef-156">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="61aef-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="61aef-157">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="61aef-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="61aef-158">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="61aef-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="61aef-159">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="61aef-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="61aef-160">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="61aef-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="61aef-161">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="61aef-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="61aef-162">Istruzione Continue</span><span class="sxs-lookup"><span data-stu-id="61aef-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
