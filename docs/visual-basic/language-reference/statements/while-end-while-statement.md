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
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843710"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="dd0e0-102">Istruzione While...End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd0e0-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="dd0e0-103">Esegue una serie di istruzioni purché una determinata condizione sia `True`.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd0e0-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="dd0e0-105">Parti</span><span class="sxs-lookup"><span data-stu-id="dd0e0-105">Parts</span></span>  
  
|<span data-ttu-id="dd0e0-106">Termine</span><span class="sxs-lookup"><span data-stu-id="dd0e0-106">Term</span></span>|<span data-ttu-id="dd0e0-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="dd0e0-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="dd0e0-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-108">Required.</span></span> <span data-ttu-id="dd0e0-109">`Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-109">`Boolean` expression.</span></span> <span data-ttu-id="dd0e0-110">Se `condition` viene `Nothing`, Visual Basic lo considera come `False`.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="dd0e0-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-111">Optional.</span></span> <span data-ttu-id="dd0e0-112">Uno o più istruzioni che seguono `While`, che ogni fase di esecuzione `condition` è `True`.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="dd0e0-113">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-113">Optional.</span></span> <span data-ttu-id="dd0e0-114">Trasferisce il controllo all'iterazione successiva del `While` blocco.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="dd0e0-115">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-115">Optional.</span></span> <span data-ttu-id="dd0e0-116">Trasferisce il controllo fuori il `While` blocco.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="dd0e0-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-117">Required.</span></span> <span data-ttu-id="dd0e0-118">Termina la definizione del blocco `While`.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd0e0-119">Note</span><span class="sxs-lookup"><span data-stu-id="dd0e0-119">Remarks</span></span>  
 <span data-ttu-id="dd0e0-120">Usare un `While...End While` struttura quando si desidera ripetere un set di istruzioni un numero indefinito di volte in cui, purché una condizione resta `True`.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="dd0e0-121">Se si desidera maggiore flessibilità su dove la condizione di test o per quale risultato si esegue il test, si potrebbe preferire il [si... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dd0e0-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="dd0e0-122">Se si desidera ripetere un determinato numero di volte, le istruzioni di [per... Istruzione Next](../../../visual-basic/language-reference/statements/for-next-statement.md) è in genere una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd0e0-123">Il `While` parola chiave viene usata anche nel [è... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md), il [clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) e il [clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="dd0e0-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="dd0e0-124">Se `condition` è `True`, tutti i del `statements` esecuzione finché il `End While` viene rilevata l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="dd0e0-125">Il controllo ritorna quindi per la `While` istruzione e `condition` viene nuovamente verificata.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="dd0e0-126">Se `condition` resta `True`, il processo viene ripetuto.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="dd0e0-127">In caso affermativo `False`, il controllo passa all'istruzione che segue il `End While` istruzione.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="dd0e0-128">Il `While` sempre istruzione verifica la condizione prima che venga avviato il ciclo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="dd0e0-129">Esecuzione del ciclo continua finché la condizione rimane `True`.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="dd0e0-130">Se `condition` è `False` quando si immissione prima di tutto il ciclo, non viene eseguito neppure una volta.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="dd0e0-131">Il `condition` generalmente i risultati da un confronto di due valori, ma possono essere qualsiasi espressione che restituisce un [tipo di dati booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valore (`True` o `False`).</span><span class="sxs-lookup"><span data-stu-id="dd0e0-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="dd0e0-132">Questa espressione può includere un valore di un altro tipo di dati, ad esempio un tipo numerico, che è stato convertito in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="dd0e0-133">È possibile annidare `While` inserendo un ciclo all'interno di altra.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="dd0e0-134">È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di loro.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="dd0e0-135">Per altre informazioni, vedere [strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="dd0e0-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="dd0e0-136">Uscita durante</span><span class="sxs-lookup"><span data-stu-id="dd0e0-136">Exit While</span></span>  
 <span data-ttu-id="dd0e0-137">Il [uscire mentre](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione può fornire un altro modo per chiudere un `While` ciclo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="dd0e0-138">`Exit While` Trasferisce il controllo all'istruzione che segue immediatamente il `End While` istruzione.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="dd0e0-139">In genere si usa `Exit While` dopo che viene valutata una condizione (ad esempio, in un `If...Then...Else` struttura).</span><span class="sxs-lookup"><span data-stu-id="dd0e0-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="dd0e0-140">È possibile uscire da un ciclo se si rileva una condizione che rende inutili o impossibili da continuare a eseguire iterazioni, ad esempio un valore errato o una richiesta di terminazione.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="dd0e0-141">È possibile usare `Exit While` quando si testa una condizione che potrebbe causare un' *ciclo infinito*, ovvero un ciclo che è stato possibile eseguire un numero estremamente grande o infinito di volte.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="dd0e0-142">È quindi possibile usare `Exit While` per interrompere il ciclo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="dd0e0-143">È possibile inserire un numero qualsiasi di `Exit While` istruzioni in qualsiasi punto nel `While` ciclo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="dd0e0-144">Quando usata all'interno di cicli `While` cicli, `Exit While` trasferisce il controllo all'esterno del ciclo più interno e nel livello superiore successivo di annidamento.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="dd0e0-145">Il `Continue While` istruzione immediatamente trasferisce il controllo all'iterazione successiva del ciclo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="dd0e0-146">Per altre informazioni, vedere [istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dd0e0-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd0e0-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd0e0-147">Example</span></span>  
 <span data-ttu-id="dd0e0-148">Nell'esempio seguente, le istruzioni nel ciclo continuano fino a incontrare il `index` variabile è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="dd0e0-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd0e0-149">Example</span></span>  
 <span data-ttu-id="dd0e0-150">Nell'esempio seguente viene illustrato l'utilizzo dei `Continue While` e `Exit While` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="dd0e0-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd0e0-151">Example</span></span>  
 <span data-ttu-id="dd0e0-152">Nell'esempio seguente legge tutte le righe in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="dd0e0-153">Il <xref:System.IO.File.OpenText%2A> metodo apre il file e restituisce un <xref:System.IO.StreamReader> che legge i caratteri.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="dd0e0-154">Nel `While` condizione, il <xref:System.IO.StreamReader.Peek%2A> metodo il `StreamReader` determina se il file contiene caratteri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="dd0e0-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="dd0e0-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd0e0-155">See also</span></span>

- [<span data-ttu-id="dd0e0-156">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="dd0e0-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="dd0e0-157">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="dd0e0-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="dd0e0-158">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="dd0e0-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="dd0e0-159">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="dd0e0-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="dd0e0-160">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="dd0e0-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="dd0e0-161">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="dd0e0-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="dd0e0-162">Istruzione Continue</span><span class="sxs-lookup"><span data-stu-id="dd0e0-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
