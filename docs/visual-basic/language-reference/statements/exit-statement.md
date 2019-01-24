---
title: Istruzione Exit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 63bcc5d5205681917ba30bdb73bc496307a6322a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672513"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="d80f0-102">Istruzione Exit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d80f0-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="d80f0-103">Esce da una routine o un blocco e trasferisce immediatamente il controllo all'istruzione che segue la chiamata di routine o la definizione di blocco.</span><span class="sxs-lookup"><span data-stu-id="d80f0-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d80f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d80f0-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="d80f0-105">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="d80f0-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="d80f0-106">Chiude immediatamente il `Do` ciclo in cui compare.</span><span class="sxs-lookup"><span data-stu-id="d80f0-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="d80f0-107">L'esecuzione continua con l'istruzione che segue il `Loop` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="d80f0-108">`Exit Do` può essere usato solo all'interno di un `Do` ciclo.</span><span class="sxs-lookup"><span data-stu-id="d80f0-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="d80f0-109">Quando usata all'interno di cicli `Do` cicli, `Exit Do` esce dal ciclo più interno e trasferisce il controllo al successivo livello superiore di annidamento.</span><span class="sxs-lookup"><span data-stu-id="d80f0-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="d80f0-110">Chiude immediatamente il `For` ciclo in cui compare.</span><span class="sxs-lookup"><span data-stu-id="d80f0-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="d80f0-111">L'esecuzione continua con l'istruzione che segue il `Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="d80f0-112">`Exit For` può essere usato solo all'interno di un `For`... `Next` o `For Each`... `Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="d80f0-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="d80f0-113">Quando usata all'interno di cicli `For` cicli, `Exit For` esce dal ciclo più interno e trasferisce il controllo al successivo livello superiore di annidamento.</span><span class="sxs-lookup"><span data-stu-id="d80f0-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="d80f0-114">Chiude immediatamente il `Function` procedure in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="d80f0-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="d80f0-115">L'esecuzione continua con l'istruzione successiva all'istruzione che ha chiamato la `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="d80f0-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="d80f0-116">`Exit Function` può essere usato solo all'interno di un `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="d80f0-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="d80f0-117">Per specificare un valore restituito, è possibile assegnare il valore per il nome della funzione in una riga prima di `Exit Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="d80f0-118">Per assegnare il valore restituito e chiudere la funzione in un'unica istruzione, è possibile usare la [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d80f0-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="d80f0-119">Chiude immediatamente il `Property` procedure in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="d80f0-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="d80f0-120">L'esecuzione continua con l'istruzione che ha chiamato la `Property` procedure, vale a dire, con l'istruzione che richiede o imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d80f0-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="d80f0-121">`Exit Property` può essere usato solo all'interno di una proprietà `Get` o `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="d80f0-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="d80f0-122">Per specificare un valore restituito in un `Get` procedure, è possibile assegnare il valore per il nome della funzione in una riga prima di `Exit Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="d80f0-123">Per assegnare il valore restituito e uscita il `Get` procedure in un'unica istruzione, è possibile utilizzare invece il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="d80f0-124">In un `Set` procedure, il `Exit Property` equivale all'istruzione il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="d80f0-125">Chiude immediatamente il `Select Case` blocco in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d80f0-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="d80f0-126">L'esecuzione continua con l'istruzione che segue il `End Select` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="d80f0-127">`Exit Select` può essere usato solo all'interno di un `Select Case` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="d80f0-128">Chiude immediatamente il `Sub` procedure in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="d80f0-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="d80f0-129">L'esecuzione continua con l'istruzione successiva all'istruzione che ha chiamato la `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="d80f0-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="d80f0-130">`Exit Sub` può essere usato solo all'interno di un `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="d80f0-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="d80f0-131">In un `Sub` procedure, il `Exit Sub` equivale all'istruzione il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="d80f0-132">Chiude immediatamente i `Try` o `Catch` blocco in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d80f0-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="d80f0-133">L'esecuzione continua con il `Finally` bloccare se presente, o con l'istruzione che segue il `End Try` istruzione in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="d80f0-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="d80f0-134">`Exit Try` può essere usato solo all'interno di un `Try` oppure `Catch` blocco e non all'interno un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="d80f0-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="d80f0-135">Chiude immediatamente il `While` ciclo in cui compare.</span><span class="sxs-lookup"><span data-stu-id="d80f0-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="d80f0-136">L'esecuzione continua con l'istruzione che segue il `End While` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="d80f0-137">`Exit While` può essere usato solo all'interno di un `While` ciclo.</span><span class="sxs-lookup"><span data-stu-id="d80f0-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="d80f0-138">Quando usata all'interno di cicli `While` cicli `Exit While` trasferisce il controllo al ciclo di un livello nidificato di sopra del ciclo in cui `Exit While` si verifica.</span><span class="sxs-lookup"><span data-stu-id="d80f0-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d80f0-139">Note</span><span class="sxs-lookup"><span data-stu-id="d80f0-139">Remarks</span></span>  
 <span data-ttu-id="d80f0-140">Non confondere `Exit` istruzioni con `End` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d80f0-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="d80f0-141">`Exit` definisce la fine di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d80f0-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="d80f0-142">Example</span></span>  
 <span data-ttu-id="d80f0-143">Nell'esempio seguente, la condizione di ciclo viene arrestato il ciclo quando il `index` variabile è maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="d80f0-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="d80f0-144">Il `If` istruzione del ciclo, tuttavia, provoca la `Exit Do` istruzione per interrompere il ciclo quando la variabile di indice è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="d80f0-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="d80f0-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="d80f0-145">Example</span></span>  
 <span data-ttu-id="d80f0-146">L'esempio seguente assegna il valore restituito per il nome della funzione `myFunction`e quindi Usa `Exit Function` da restituire dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="d80f0-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="d80f0-147">Example</span></span>  
 <span data-ttu-id="d80f0-148">L'esempio seguente usa il [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) assegnare il valore restituito e uscire dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="d80f0-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d80f0-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d80f0-149">See also</span></span>
- [<span data-ttu-id="d80f0-150">Istruzione Continue</span><span class="sxs-lookup"><span data-stu-id="d80f0-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
- [<span data-ttu-id="d80f0-151">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="d80f0-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="d80f0-152">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="d80f0-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="d80f0-153">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="d80f0-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="d80f0-154">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="d80f0-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="d80f0-155">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="d80f0-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="d80f0-156">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="d80f0-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="d80f0-157">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="d80f0-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="d80f0-158">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="d80f0-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d80f0-159">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="d80f0-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
