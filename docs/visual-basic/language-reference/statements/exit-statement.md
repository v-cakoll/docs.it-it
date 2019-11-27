---
title: Istruzione Exit
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
ms.openlocfilehash: 1bfe81428fd3c50663fd8978e05c6a945cd47df8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345932"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="2f925-102">Istruzione Exit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f925-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="2f925-103">Esce da una routine o da un blocco e trasferisce immediatamente il controllo all'istruzione successiva alla chiamata di routine o alla definizione del blocco.</span><span class="sxs-lookup"><span data-stu-id="2f925-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f925-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f925-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="2f925-105">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="2f925-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="2f925-106">Chiude immediatamente il `Do` ciclo in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2f925-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="2f925-107">L'esecuzione continua con l'istruzione che segue l'istruzione `Loop`.</span><span class="sxs-lookup"><span data-stu-id="2f925-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="2f925-108">`Exit Do` può essere utilizzato solo all'interno di un ciclo di `Do`.</span><span class="sxs-lookup"><span data-stu-id="2f925-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="2f925-109">Quando viene usato all'interno di cicli di `Do` annidati, `Exit Do` esce dal ciclo più interno e trasferisce il controllo al livello di nidificazione successivo.</span><span class="sxs-lookup"><span data-stu-id="2f925-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="2f925-110">Chiude immediatamente il `For` ciclo in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2f925-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="2f925-111">L'esecuzione continua con l'istruzione che segue l'istruzione `Next`.</span><span class="sxs-lookup"><span data-stu-id="2f925-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="2f925-112">`Exit For` può essere utilizzato solo all'interno di un ciclo `For`...`Next` o `For Each`...`Next`.</span><span class="sxs-lookup"><span data-stu-id="2f925-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="2f925-113">Quando viene usato all'interno di cicli di `For` annidati, `Exit For` esce dal ciclo più interno e trasferisce il controllo al livello di nidificazione successivo.</span><span class="sxs-lookup"><span data-stu-id="2f925-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="2f925-114">Chiude immediatamente la `Function` routine in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2f925-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="2f925-115">L'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura `Function`.</span><span class="sxs-lookup"><span data-stu-id="2f925-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="2f925-116">`Exit Function` può essere utilizzato solo all'interno di una routine di `Function`.</span><span class="sxs-lookup"><span data-stu-id="2f925-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="2f925-117">Per specificare un valore restituito, è possibile assegnare il valore al nome della funzione su una riga prima dell'istruzione `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="2f925-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="2f925-118">Per assegnare il valore restituito e uscire dalla funzione in un'unica istruzione, è possibile usare invece l' [istruzione return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2f925-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="2f925-119">Chiude immediatamente la `Property` routine in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2f925-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="2f925-120">L'esecuzione continua con l'istruzione che ha chiamato la procedura `Property`, ovvero con l'istruzione che richiede o imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f925-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="2f925-121">`Exit Property` può essere utilizzato solo all'interno di una routine `Get` o `Set` della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f925-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="2f925-122">Per specificare un valore restituito in una procedura di `Get`, è possibile assegnare il valore al nome della funzione su una riga prima dell'istruzione `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="2f925-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="2f925-123">Per assegnare il valore restituito e uscire dalla procedura `Get` in un'unica istruzione, è possibile usare l'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="2f925-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="2f925-124">In una `Set` routine, l'istruzione `Exit Property` è equivalente all'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="2f925-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="2f925-125">Chiude immediatamente il `Select Case` blocco in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2f925-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="2f925-126">L'esecuzione continua con l'istruzione che segue l'istruzione `End Select`.</span><span class="sxs-lookup"><span data-stu-id="2f925-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="2f925-127">`Exit Select` può essere utilizzato solo all'interno di un'istruzione `Select Case`.</span><span class="sxs-lookup"><span data-stu-id="2f925-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="2f925-128">Chiude immediatamente la `Sub` routine in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2f925-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="2f925-129">L'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura `Sub`.</span><span class="sxs-lookup"><span data-stu-id="2f925-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="2f925-130">`Exit Sub` può essere utilizzato solo all'interno di una routine di `Sub`.</span><span class="sxs-lookup"><span data-stu-id="2f925-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="2f925-131">In una `Sub` routine, l'istruzione `Exit Sub` è equivalente all'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="2f925-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="2f925-132">Chiude immediatamente il `Try` o `Catch` blocco in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2f925-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="2f925-133">L'esecuzione continua con il blocco `Finally` se ne esiste uno oppure con l'istruzione che segue l'istruzione `End Try` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="2f925-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="2f925-134">`Exit Try` può essere utilizzato solo all'interno di un blocco `Try` o `Catch` e non all'interno di un blocco `Finally`.</span><span class="sxs-lookup"><span data-stu-id="2f925-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="2f925-135">Chiude immediatamente il `While` ciclo in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2f925-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="2f925-136">L'esecuzione continua con l'istruzione che segue l'istruzione `End While`.</span><span class="sxs-lookup"><span data-stu-id="2f925-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="2f925-137">`Exit While` può essere utilizzato solo all'interno di un ciclo di `While`.</span><span class="sxs-lookup"><span data-stu-id="2f925-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="2f925-138">Quando viene usato all'interno di cicli di `While` annidati, `Exit While` trasferisce il controllo al ciclo che è un livello annidato al di sopra del ciclo in cui si verifica `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="2f925-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f925-139">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2f925-139">Remarks</span></span>

<span data-ttu-id="2f925-140">Non confondere `Exit` istruzioni con istruzioni `End`.</span><span class="sxs-lookup"><span data-stu-id="2f925-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="2f925-141">`Exit` non definisce la fine di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="2f925-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="2f925-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f925-142">Example</span></span>

<span data-ttu-id="2f925-143">Nell'esempio seguente, la condizione del ciclo arresta il ciclo quando la variabile di `index` è maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="2f925-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="2f925-144">L'istruzione `If` nel ciclo, tuttavia, causa l'arresto del ciclo da parte dell'istruzione `Exit Do` quando la variabile di indice è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="2f925-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="2f925-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f925-145">Example</span></span>

<span data-ttu-id="2f925-146">Nell'esempio seguente il valore restituito viene assegnato al nome della funzione `myFunction`, quindi utilizza `Exit Function` per restituire dalla funzione:</span><span class="sxs-lookup"><span data-stu-id="2f925-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="2f925-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f925-147">Example</span></span>

<span data-ttu-id="2f925-148">Nell'esempio seguente viene utilizzata l' [istruzione return](return-statement.md) per assegnare il valore restituito e uscire dalla funzione:</span><span class="sxs-lookup"><span data-stu-id="2f925-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="2f925-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f925-149">See also</span></span>

- [<span data-ttu-id="2f925-150">Istruzione Continue</span><span class="sxs-lookup"><span data-stu-id="2f925-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="2f925-151">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="2f925-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="2f925-152">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="2f925-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="2f925-153">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="2f925-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="2f925-154">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="2f925-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="2f925-155">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="2f925-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="2f925-156">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="2f925-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="2f925-157">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="2f925-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="2f925-158">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="2f925-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="2f925-159">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="2f925-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
