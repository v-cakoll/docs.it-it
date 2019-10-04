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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956938"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="df681-102">Istruzione Exit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df681-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="df681-103">Esce da una routine o da un blocco e trasferisce immediatamente il controllo all'istruzione successiva alla chiamata di routine o alla definizione del blocco.</span><span class="sxs-lookup"><span data-stu-id="df681-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="df681-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df681-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="df681-105">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="df681-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="df681-106">Chiude immediatamente il ciclo `Do` in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="df681-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="df681-107">L'esecuzione continua con l'istruzione che segue l'istruzione `Loop`.</span><span class="sxs-lookup"><span data-stu-id="df681-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="df681-108">`Exit Do` può essere utilizzato solo all'interno di un ciclo `Do`.</span><span class="sxs-lookup"><span data-stu-id="df681-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="df681-109">Quando viene usato all'interno di cicli `Do` annidati, `Exit Do` esce dal ciclo più interno e trasferisce il controllo al livello di nidificazione successivo.</span><span class="sxs-lookup"><span data-stu-id="df681-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="df681-110">Chiude immediatamente il ciclo `For` in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="df681-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="df681-111">L'esecuzione continua con l'istruzione che segue l'istruzione `Next`.</span><span class="sxs-lookup"><span data-stu-id="df681-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="df681-112">`Exit For` può essere utilizzato solo all'interno di un ciclo `For`... `Next` o `For Each`... `Next`.</span><span class="sxs-lookup"><span data-stu-id="df681-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="df681-113">Quando viene usato all'interno di cicli `For` annidati, `Exit For` esce dal ciclo più interno e trasferisce il controllo al livello di nidificazione successivo.</span><span class="sxs-lookup"><span data-stu-id="df681-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="df681-114">Esce immediatamente dalla procedura @no__t 0 in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="df681-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="df681-115">L'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura `Function`.</span><span class="sxs-lookup"><span data-stu-id="df681-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="df681-116">`Exit Function` può essere utilizzato solo all'interno di una procedura `Function`.</span><span class="sxs-lookup"><span data-stu-id="df681-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="df681-117">Per specificare un valore restituito, è possibile assegnare il valore al nome della funzione in una riga prima dell'istruzione `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="df681-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="df681-118">Per assegnare il valore restituito e uscire dalla funzione in un'unica istruzione, è possibile usare invece l' [istruzione return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="df681-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="df681-119">Esce immediatamente dalla procedura @no__t 0 in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="df681-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="df681-120">L'esecuzione continua con l'istruzione che ha chiamato la procedura `Property`, ovvero con l'istruzione che richiede o imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="df681-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="df681-121">`Exit Property` può essere utilizzato solo all'interno di una routine `Get` o `Set` di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="df681-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="df681-122">Per specificare un valore restituito in una procedura `Get`, è possibile assegnare il valore al nome della funzione su una riga prima dell'istruzione `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="df681-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="df681-123">Per assegnare il valore restituito e uscire dalla procedura `Get` in un'unica istruzione, è possibile usare invece l'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="df681-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="df681-124">In una procedura `Set`, l'istruzione `Exit Property` è equivalente all'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="df681-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="df681-125">Esce immediatamente dal blocco `Select Case` in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="df681-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="df681-126">L'esecuzione continua con l'istruzione che segue l'istruzione `End Select`.</span><span class="sxs-lookup"><span data-stu-id="df681-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="df681-127">`Exit Select` può essere utilizzato solo all'interno di un'istruzione `Select Case`.</span><span class="sxs-lookup"><span data-stu-id="df681-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="df681-128">Esce immediatamente dalla procedura @no__t 0 in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="df681-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="df681-129">L'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura `Sub`.</span><span class="sxs-lookup"><span data-stu-id="df681-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="df681-130">`Exit Sub` può essere utilizzato solo all'interno di una procedura `Sub`.</span><span class="sxs-lookup"><span data-stu-id="df681-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="df681-131">In una procedura `Sub`, l'istruzione `Exit Sub` è equivalente all'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="df681-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="df681-132">Esce immediatamente dal blocco `Try` o `Catch` in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="df681-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="df681-133">L'esecuzione continua con il blocco `Finally` se ne esiste uno oppure con l'istruzione che segue l'istruzione `End Try` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="df681-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="df681-134">`Exit Try` può essere utilizzato solo all'interno di un blocco `Try` o `Catch`, non all'interno di un blocco `Finally`.</span><span class="sxs-lookup"><span data-stu-id="df681-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="df681-135">Chiude immediatamente il ciclo `While` in cui viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="df681-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="df681-136">L'esecuzione continua con l'istruzione che segue l'istruzione `End While`.</span><span class="sxs-lookup"><span data-stu-id="df681-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="df681-137">`Exit While` può essere utilizzato solo all'interno di un ciclo `While`.</span><span class="sxs-lookup"><span data-stu-id="df681-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="df681-138">Quando viene utilizzato all'interno di cicli `While` annidati, `Exit While` trasferisce il controllo al ciclo che è un livello annidato sopra il ciclo in cui si verifica `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="df681-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="df681-139">Note</span><span class="sxs-lookup"><span data-stu-id="df681-139">Remarks</span></span>

<span data-ttu-id="df681-140">Non confondere le istruzioni `Exit` con le istruzioni `End`.</span><span class="sxs-lookup"><span data-stu-id="df681-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="df681-141">`Exit` non definisce la fine di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="df681-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="df681-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="df681-142">Example</span></span>

<span data-ttu-id="df681-143">Nell'esempio seguente, la condizione del ciclo arresta il ciclo quando la variabile `index` è maggiore di 100.</span><span class="sxs-lookup"><span data-stu-id="df681-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="df681-144">L'istruzione `If` del ciclo, tuttavia, fa sì che l'istruzione `Exit Do` interrompa il ciclo quando la variabile di indice è maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="df681-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="df681-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="df681-145">Example</span></span>

<span data-ttu-id="df681-146">Nell'esempio seguente viene assegnato il valore restituito al nome della funzione `myFunction`, quindi viene utilizzato `Exit Function` per restituire dalla funzione:</span><span class="sxs-lookup"><span data-stu-id="df681-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="df681-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="df681-147">Example</span></span>

<span data-ttu-id="df681-148">Nell'esempio seguente viene utilizzata l' [istruzione return](return-statement.md) per assegnare il valore restituito e uscire dalla funzione:</span><span class="sxs-lookup"><span data-stu-id="df681-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="df681-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df681-149">See also</span></span>

- [<span data-ttu-id="df681-150">Istruzione Continue</span><span class="sxs-lookup"><span data-stu-id="df681-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="df681-151">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="df681-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="df681-152">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="df681-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="df681-153">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="df681-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="df681-154">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="df681-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="df681-155">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="df681-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="df681-156">Istruzione Return</span><span class="sxs-lookup"><span data-stu-id="df681-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="df681-157">Istruzione Stop</span><span class="sxs-lookup"><span data-stu-id="df681-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="df681-158">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="df681-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="df681-159">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="df681-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
