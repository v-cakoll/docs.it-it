---
title: Istruzione For...Next (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: cafd59482036a598814dcd4815fa67a791580045
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046304"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="4793b-102">Istruzione For...Next (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4793b-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="4793b-103">Ripete un gruppo di istruzioni per un numero di volte specificato.</span><span class="sxs-lookup"><span data-stu-id="4793b-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="4793b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4793b-104">Syntax</span></span>

```
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="4793b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4793b-105">Parts</span></span>

|<span data-ttu-id="4793b-106">Parte</span><span class="sxs-lookup"><span data-stu-id="4793b-106">Part</span></span>|<span data-ttu-id="4793b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4793b-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="4793b-108">Obbligatorio nell' `For` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4793b-108">Required in the `For` statement.</span></span> <span data-ttu-id="4793b-109">Variabile numerica.</span><span class="sxs-lookup"><span data-stu-id="4793b-109">Numeric variable.</span></span> <span data-ttu-id="4793b-110">Variabile di controllo per il ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-110">The control variable for the loop.</span></span> <span data-ttu-id="4793b-111">Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4793b-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="4793b-112">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4793b-112">Optional.</span></span> <span data-ttu-id="4793b-113">Tipo di dati `counter`di.</span><span class="sxs-lookup"><span data-stu-id="4793b-113">Data type of `counter`.</span></span> <span data-ttu-id="4793b-114">Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4793b-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="4793b-115">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="4793b-115">Required.</span></span> <span data-ttu-id="4793b-116">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4793b-116">Numeric expression.</span></span> <span data-ttu-id="4793b-117">Il valore iniziale di `counter`.</span><span class="sxs-lookup"><span data-stu-id="4793b-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="4793b-118">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="4793b-118">Required.</span></span> <span data-ttu-id="4793b-119">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4793b-119">Numeric expression.</span></span> <span data-ttu-id="4793b-120">Valore finale di `counter`.</span><span class="sxs-lookup"><span data-stu-id="4793b-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="4793b-121">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4793b-121">Optional.</span></span> <span data-ttu-id="4793b-122">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="4793b-122">Numeric expression.</span></span> <span data-ttu-id="4793b-123">Importo in base al `counter` quale viene incrementato ogni volta nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="4793b-124">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4793b-124">Optional.</span></span> <span data-ttu-id="4793b-125">Una o più istruzioni tra `For` e `Next` che eseguono il numero di volte specificato.</span><span class="sxs-lookup"><span data-stu-id="4793b-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="4793b-126">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4793b-126">Optional.</span></span> <span data-ttu-id="4793b-127">Trasferisce il controllo alla successiva iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="4793b-128">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4793b-128">Optional.</span></span> <span data-ttu-id="4793b-129">Trasferisce il controllo all' `For` esterno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="4793b-130">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="4793b-130">Required.</span></span> <span data-ttu-id="4793b-131">Termina la definizione del `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="4793b-132">La `To` parola chiave viene utilizzata in questa istruzione per specificare l'intervallo per il contatore.</span><span class="sxs-lookup"><span data-stu-id="4793b-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="4793b-133">È anche possibile usare questa parola chiave nell'oggetto [Select... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) e nelle dichiarazioni di matrici.</span><span class="sxs-lookup"><span data-stu-id="4793b-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="4793b-134">Per ulteriori informazioni sulle dichiarazioni di matrici, vedere [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4793b-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="4793b-135">Esempi semplici</span><span class="sxs-lookup"><span data-stu-id="4793b-135">Simple Examples</span></span>

<span data-ttu-id="4793b-136">Usare `For`... `Next` struttura quando si desidera ripetere un set di istruzioni impostando un numero di volte.</span><span class="sxs-lookup"><span data-stu-id="4793b-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="4793b-137">Nell'esempio seguente, la `index` variabile inizia con un valore pari a 1 e viene incrementata a ogni iterazione del ciclo, terminando dopo il valore di `index` raggiunge 5.</span><span class="sxs-lookup"><span data-stu-id="4793b-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="4793b-138">Nell'esempio seguente, la `number` variabile inizia da 2 e viene ridotta di 0,25 in ogni iterazione del ciclo, terminando dopo il valore di `number` raggiunge 0.</span><span class="sxs-lookup"><span data-stu-id="4793b-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="4793b-139">L' `Step` argomento di `-.25` riduce il valore di 0,25 a ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="4793b-140">Un [po'... Istruzione End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [do... L'istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md) funziona bene se non si conosce in anticipo il numero di volte in cui eseguire le istruzioni nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="4793b-141">Tuttavia, quando si prevede di eseguire il ciclo un numero specifico di volte, a `For`... `Next` il ciclo è una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="4793b-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="4793b-142">Il numero di iterazioni viene determinato quando si immette il ciclo per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="4793b-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="4793b-143">Annidamento di cicli</span><span class="sxs-lookup"><span data-stu-id="4793b-143">Nesting Loops</span></span>

<span data-ttu-id="4793b-144">È possibile annidare `For` cicli inserendo un ciclo all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="4793b-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="4793b-145">Nell'esempio seguente viene illustrato `For`l'oggetto annidato... `Next` strutture con valori di passaggio diversi.</span><span class="sxs-lookup"><span data-stu-id="4793b-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="4793b-146">Il ciclo esterno crea una stringa per ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="4793b-147">Il ciclo interno decrementa una variabile del contatore di cicli per ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="4793b-148">Quando si annidano cicli, ogni ciclo deve avere una `counter` variabile univoca.</span><span class="sxs-lookup"><span data-stu-id="4793b-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="4793b-149">È anche possibile annidare strutture di controllo di tipi diversi l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="4793b-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="4793b-150">Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="4793b-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="4793b-151">Esci per e continua per</span><span class="sxs-lookup"><span data-stu-id="4793b-151">Exit For and Continue For</span></span>

<span data-ttu-id="4793b-152">L' `Exit For` istruzione esce `For`immediatamente da...`Next`</span><span class="sxs-lookup"><span data-stu-id="4793b-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="4793b-153">esegue il ciclo e trasferisce il controllo all'istruzione `Next` che segue l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4793b-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="4793b-154">L' `Continue For` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="4793b-155">Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4793b-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>

<span data-ttu-id="4793b-156">Nell'esempio seguente viene illustrato l'utilizzo delle `Continue For` istruzioni e. `Exit For`</span><span class="sxs-lookup"><span data-stu-id="4793b-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="4793b-157">È possibile inserire un numero qualsiasi `Exit For` di istruzioni in `For`un...`Next`</span><span class="sxs-lookup"><span data-stu-id="4793b-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="4793b-158">ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-158">loop.</span></span> <span data-ttu-id="4793b-159">Se utilizzato all'interno `For`di...`Next`</span><span class="sxs-lookup"><span data-stu-id="4793b-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="4793b-160">esegue il `Exit For` loop, esce dal ciclo più interno e trasferisce il controllo al successivo livello di nidificazione.</span><span class="sxs-lookup"><span data-stu-id="4793b-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="4793b-161">`Exit For`viene spesso usato dopo la valutazione di una condizione, ad esempio in un `If`... `Then`... `Else` struttura).</span><span class="sxs-lookup"><span data-stu-id="4793b-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="4793b-162">Può essere utile usare `Exit For` per le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4793b-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="4793b-163">La continuazione dell'iterazione non è necessaria o impossibile.</span><span class="sxs-lookup"><span data-stu-id="4793b-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="4793b-164">Questa condizione può essere creata da un valore errato o da una richiesta di terminazione.</span><span class="sxs-lookup"><span data-stu-id="4793b-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="4793b-165">A `Try`... `Catch`... `Finally` l'istruzione rileva un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4793b-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="4793b-166">È possibile utilizzare `Exit For` alla fine `Finally` del blocco.</span><span class="sxs-lookup"><span data-stu-id="4793b-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="4793b-167">Si dispone di un ciclo infinito, ovvero un ciclo che può eseguire un numero di volte elevato o addirittura infinito.</span><span class="sxs-lookup"><span data-stu-id="4793b-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="4793b-168">Se si rileva una condizione di questo tipo, è `Exit For` possibile utilizzare per eseguire l'escape del ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="4793b-169">Per ulteriori informazioni, vedere [... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4793b-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="4793b-170">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="4793b-170">Technical Implementation</span></span>

<span data-ttu-id="4793b-171">Quando un `For`... il ciclo viene avviato, Visual Basic `start`valuta `end`, e `step`. `Next`</span><span class="sxs-lookup"><span data-stu-id="4793b-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="4793b-172">Visual Basic valuta questi valori solo in questo momento e quindi assegna `start` a. `counter`</span><span class="sxs-lookup"><span data-stu-id="4793b-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="4793b-173">Prima dell'esecuzione del blocco `counter` di istruzioni, Visual Basic viene confrontato con. `end`</span><span class="sxs-lookup"><span data-stu-id="4793b-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="4793b-174">Se `counter` è già maggiore del `end` valore (o minore se `step` è negativo), il `For` ciclo termina e il controllo passa all'istruzione che segue l' `Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4793b-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="4793b-175">In caso contrario, viene eseguito il blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="4793b-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="4793b-176">Ogni volta `Next` che Visual Basic rileva l'istruzione, viene `counter` incrementato `For` di `step` e viene restituito all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4793b-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="4793b-177">Anche in questo caso `counter` viene `end`confrontato con e di nuovo esegue il blocco o esce dal ciclo, a seconda del risultato.</span><span class="sxs-lookup"><span data-stu-id="4793b-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="4793b-178">Questo processo continua fino `counter` a `end` quando non `Exit For` vengono rilevati i passaggi o un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4793b-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="4793b-179">Il ciclo non viene arrestato `counter` fino a `end`quando non viene superato.</span><span class="sxs-lookup"><span data-stu-id="4793b-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="4793b-180">Se `counter` è uguale a `end`, il ciclo continua.</span><span class="sxs-lookup"><span data-stu-id="4793b-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="4793b-181">`counter` Il confronto che determina se eseguire il blocco è `end` `counter` `end`  <=  se `step` è positivo e  >=  se `step` è negativo.</span><span class="sxs-lookup"><span data-stu-id="4793b-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="4793b-182">Se si modifica il valore di `counter` all'interno di un ciclo, il codice potrebbe essere più difficile da leggere ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="4793b-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="4793b-183">La modifica del valore `start`di `end`, o `step` non influisce sui valori di iterazione che sono stati determinati quando il ciclo è stato immesso per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="4793b-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="4793b-184">Se si annidano i cicli, il compilatore segnala un errore se rileva l' `Next` istruzione di un livello di nidificazione esterno prima dell' `Next` istruzione di un livello interno.</span><span class="sxs-lookup"><span data-stu-id="4793b-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="4793b-185">Tuttavia, il compilatore può rilevare questo errore di sovrapposizione solo se si specifica `counter` in ogni `Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4793b-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="4793b-186">Argomento Step</span><span class="sxs-lookup"><span data-stu-id="4793b-186">Step Argument</span></span>

<span data-ttu-id="4793b-187">Il valore di `step` può essere positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4793b-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="4793b-188">Questo parametro determina l'elaborazione del ciclo in base alla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4793b-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="4793b-189">**Valore passaggio**</span><span class="sxs-lookup"><span data-stu-id="4793b-189">**Step value**</span></span>|<span data-ttu-id="4793b-190">**Il ciclo viene eseguito se**</span><span class="sxs-lookup"><span data-stu-id="4793b-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="4793b-191">Positivo o zero</span><span class="sxs-lookup"><span data-stu-id="4793b-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="4793b-192">Negativo</span><span class="sxs-lookup"><span data-stu-id="4793b-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="4793b-193">Il valore predefinito di `step` è 1.</span><span class="sxs-lookup"><span data-stu-id="4793b-193">The default value of `step` is 1.</span></span>

### <a name="BKMK_Counter"></a><span data-ttu-id="4793b-194">Argomento contatore</span><span class="sxs-lookup"><span data-stu-id="4793b-194">Counter Argument</span></span>

<span data-ttu-id="4793b-195">La tabella seguente indica se `counter` definisce una nuova variabile locale con ambito per l'intero `For…Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="4793b-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="4793b-196">Questa decisione dipende dal fatto `datatype` che sia presente e che `counter` sia già definito.</span><span class="sxs-lookup"><span data-stu-id="4793b-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="4793b-197">È `datatype` presente?</span><span class="sxs-lookup"><span data-stu-id="4793b-197">Is `datatype` present?</span></span>|<span data-ttu-id="4793b-198">È `counter` già definito?</span><span class="sxs-lookup"><span data-stu-id="4793b-198">Is `counter` already defined?</span></span>|<span data-ttu-id="4793b-199">Risultato (se `counter` definisce una nuova variabile locale con ambito per l'intero `For...Next` ciclo)</span><span class="sxs-lookup"><span data-stu-id="4793b-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="4793b-200">No</span><span class="sxs-lookup"><span data-stu-id="4793b-200">No</span></span>|<span data-ttu-id="4793b-201">Sì</span><span class="sxs-lookup"><span data-stu-id="4793b-201">Yes</span></span>|<span data-ttu-id="4793b-202">No, perché `counter` è già definito.</span><span class="sxs-lookup"><span data-stu-id="4793b-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="4793b-203">Se l'ambito di `counter` non è locale alla routine, viene generato un avviso in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4793b-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="4793b-204">No</span><span class="sxs-lookup"><span data-stu-id="4793b-204">No</span></span>|<span data-ttu-id="4793b-205">No</span><span class="sxs-lookup"><span data-stu-id="4793b-205">No</span></span>|<span data-ttu-id="4793b-206">Sì.</span><span class="sxs-lookup"><span data-stu-id="4793b-206">Yes.</span></span> <span data-ttu-id="4793b-207">Il tipo di dati viene dedotto dalle `start`espressioni, `end`e. `step`</span><span class="sxs-lookup"><span data-stu-id="4793b-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="4793b-208">Per informazioni sull'inferenza del tipo, vedere [istruzione Option deduce](../../../visual-basic/language-reference/statements/option-infer-statement.md) e inferenza [del tipo locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="4793b-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="4793b-209">Sì</span><span class="sxs-lookup"><span data-stu-id="4793b-209">Yes</span></span>|<span data-ttu-id="4793b-210">Yes</span><span class="sxs-lookup"><span data-stu-id="4793b-210">Yes</span></span>|<span data-ttu-id="4793b-211">Sì, ma solo se la variabile `counter` esistente è definita all'esterno della routine.</span><span class="sxs-lookup"><span data-stu-id="4793b-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="4793b-212">Tale variabile rimane separata.</span><span class="sxs-lookup"><span data-stu-id="4793b-212">That variable remains separate.</span></span> <span data-ttu-id="4793b-213">Se l'ambito della variabile esistente `counter` è locale alla procedura, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4793b-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="4793b-214">Yes</span><span class="sxs-lookup"><span data-stu-id="4793b-214">Yes</span></span>|<span data-ttu-id="4793b-215">No</span><span class="sxs-lookup"><span data-stu-id="4793b-215">No</span></span>|<span data-ttu-id="4793b-216">Sì.</span><span class="sxs-lookup"><span data-stu-id="4793b-216">Yes.</span></span>|

<span data-ttu-id="4793b-217">Il tipo di dati `counter` di determina il tipo di iterazione, che deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4793b-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="4793b-218">`Byte` ,`SByte` ,,`UInteger`,, ,`ULong`,,, O.`Single` `Decimal` `Integer` `Short` `UShort` `Long` `Double`</span><span class="sxs-lookup"><span data-stu-id="4793b-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="4793b-219">Enumerazione dichiarata tramite un' [istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4793b-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

- <span data-ttu-id="4793b-220">Oggetto `Object`.</span><span class="sxs-lookup"><span data-stu-id="4793b-220">An `Object`.</span></span>

- <span data-ttu-id="4793b-221">Tipo `T` che dispone degli operatori seguenti, dove `B` è un tipo che può essere utilizzato in un' `Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="4793b-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="4793b-222">Facoltativamente, è possibile specificare `counter` la variabile `Next` nell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4793b-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="4793b-223">Questa sintassi migliora la leggibilità del programma, soprattutto se sono presenti cicli nidificati `For` .</span><span class="sxs-lookup"><span data-stu-id="4793b-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="4793b-224">È necessario specificare la variabile visualizzata nell'istruzione corrispondente `For` .</span><span class="sxs-lookup"><span data-stu-id="4793b-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="4793b-225">Le `start`espressioni `end`, `counter`e `step` possono restituire qualsiasi tipo di dati che viene ampliato al tipo di.</span><span class="sxs-lookup"><span data-stu-id="4793b-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="4793b-226">Se si utilizza un tipo definito dall'utente per `counter`, potrebbe essere necessario definire l' `CType` operatore di conversione per convertire i tipi di `start`, `end`o `step` nel tipo di `counter`.</span><span class="sxs-lookup"><span data-stu-id="4793b-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="4793b-227">Esempio</span><span class="sxs-lookup"><span data-stu-id="4793b-227">Example</span></span>

<span data-ttu-id="4793b-228">Nell'esempio seguente vengono rimossi tutti gli elementi da un elenco generico.</span><span class="sxs-lookup"><span data-stu-id="4793b-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="4793b-229">Anziché [per ogni... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md), l'esempio mostra un `For`... `Next` istruzione che esegue l'iterazione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="4793b-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="4793b-230">L'esempio usa questa tecnica perché il `removeAt` metodo fa sì che gli elementi dopo l'elemento rimosso abbiano un valore di indice inferiore.</span><span class="sxs-lookup"><span data-stu-id="4793b-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="4793b-231">Esempio</span><span class="sxs-lookup"><span data-stu-id="4793b-231">Example</span></span>

<span data-ttu-id="4793b-232">Nell'esempio seguente viene iterata un'enumerazione dichiarata tramite un' [istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4793b-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="4793b-233">Esempio</span><span class="sxs-lookup"><span data-stu-id="4793b-233">Example</span></span>

<span data-ttu-id="4793b-234">Nell'esempio seguente, i parametri dell'istruzione usano una classe con overload di `+`operatori per gli operatori, `-`, `>=`e `<=` .</span><span class="sxs-lookup"><span data-stu-id="4793b-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="4793b-235">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4793b-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="4793b-236">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="4793b-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="4793b-237">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="4793b-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="4793b-238">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="4793b-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="4793b-239">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="4793b-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="4793b-240">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="4793b-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="4793b-241">Raccolte</span><span class="sxs-lookup"><span data-stu-id="4793b-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
