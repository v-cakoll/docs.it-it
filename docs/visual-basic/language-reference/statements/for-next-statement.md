---
title: Istruzione For...Next
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
ms.openlocfilehash: 6896c6cfb4ec5d6207011e56b72639c459120e53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404641"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="3e6c9-102">Istruzione For...Next (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e6c9-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="3e6c9-103">Ripete un gruppo di istruzioni per un numero di volte specificato.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e6c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e6c9-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="3e6c9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="3e6c9-105">Parts</span></span>

|<span data-ttu-id="3e6c9-106">Parte</span><span class="sxs-lookup"><span data-stu-id="3e6c9-106">Part</span></span>|<span data-ttu-id="3e6c9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e6c9-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="3e6c9-108">Obbligatorio nell' `For` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-108">Required in the `For` statement.</span></span> <span data-ttu-id="3e6c9-109">Variabile numerica.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-109">Numeric variable.</span></span> <span data-ttu-id="3e6c9-110">Variabile di controllo per il ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-110">The control variable for the loop.</span></span> <span data-ttu-id="3e6c9-111">Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="3e6c9-112">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-112">Optional.</span></span> <span data-ttu-id="3e6c9-113">Tipo di dati di `counter` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-113">Data type of `counter`.</span></span> <span data-ttu-id="3e6c9-114">Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="3e6c9-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-115">Required.</span></span> <span data-ttu-id="3e6c9-116">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-116">Numeric expression.</span></span> <span data-ttu-id="3e6c9-117">Il valore iniziale di `counter`.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="3e6c9-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-118">Required.</span></span> <span data-ttu-id="3e6c9-119">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-119">Numeric expression.</span></span> <span data-ttu-id="3e6c9-120">Valore finale di `counter` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="3e6c9-121">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-121">Optional.</span></span> <span data-ttu-id="3e6c9-122">Espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-122">Numeric expression.</span></span> <span data-ttu-id="3e6c9-123">Importo in base al quale `counter` viene incrementato ogni volta nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="3e6c9-124">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-124">Optional.</span></span> <span data-ttu-id="3e6c9-125">Una o più istruzioni tra `For` e `Next` che eseguono il numero di volte specificato.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="3e6c9-126">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-126">Optional.</span></span> <span data-ttu-id="3e6c9-127">Trasferisce il controllo alla successiva iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="3e6c9-128">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-128">Optional.</span></span> <span data-ttu-id="3e6c9-129">Trasferisce il controllo all'esterno del `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="3e6c9-130">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-130">Required.</span></span> <span data-ttu-id="3e6c9-131">Termina la definizione del `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="3e6c9-132">La `To` parola chiave viene utilizzata in questa istruzione per specificare l'intervallo per il contatore.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="3e6c9-133">È anche possibile usare questa parola chiave nell'oggetto [Select... Istruzione case](select-case-statement.md) e nelle dichiarazioni di matrici.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-133">You can also use this keyword in the [Select...Case Statement](select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="3e6c9-134">Per ulteriori informazioni sulle dichiarazioni di matrici, vedere [istruzione Dim](dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-134">For more information about array declarations, see [Dim Statement](dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="3e6c9-135"> Semplici esempi</span><span class="sxs-lookup"><span data-stu-id="3e6c9-135">Simple Examples</span></span>

<span data-ttu-id="3e6c9-136">Utilizzare una `For` struttura... `Next` quando si desidera ripetere un set di istruzioni per un numero di volte.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="3e6c9-137">Nell'esempio seguente, la `index` variabile inizia con un valore pari a 1 e viene incrementata a ogni iterazione del ciclo, terminando dopo il valore di `index` raggiunge 5.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="3e6c9-138">Nell'esempio seguente, la `number` variabile inizia da 2 e viene ridotta di 0,25 in ogni iterazione del ciclo, terminando dopo il valore di `number` raggiunge 0.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="3e6c9-139">L' `Step` argomento di `-.25` riduce il valore di 0,25 a ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="3e6c9-140">Un [po'... Istruzione End While](while-end-while-statement.md) o [do... L'istruzione Loop](do-loop-statement.md) funziona bene se non si conosce in anticipo il numero di volte in cui eseguire le istruzioni nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-140">A [While...End While Statement](while-end-while-statement.md) or [Do...Loop Statement](do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="3e6c9-141">Tuttavia, quando si prevede di eseguire il ciclo un numero specifico di volte, un `For` ciclo... `Next` rappresenta una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="3e6c9-142">Il numero di iterazioni viene determinato quando si immette il ciclo per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="3e6c9-143">Annidamento di cicli</span><span class="sxs-lookup"><span data-stu-id="3e6c9-143">Nesting Loops</span></span>

<span data-ttu-id="3e6c9-144">È possibile annidare `For` cicli inserendo un ciclo all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="3e6c9-145">Nell'esempio seguente vengono illustrate le strutture annidate con `For` `Next` valori di passaggio diversi.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="3e6c9-146">Il ciclo esterno crea una stringa per ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="3e6c9-147">Il ciclo interno decrementa una variabile del contatore di cicli per ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="3e6c9-148">Quando si annidano cicli, ogni ciclo deve avere una `counter` variabile univoca.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="3e6c9-149">È anche possibile annidare strutture di controllo di tipi diversi l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="3e6c9-150">Per altre informazioni, vedere [strutture di controlli annidati](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-150">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="3e6c9-151">Esci per e continua per</span><span class="sxs-lookup"><span data-stu-id="3e6c9-151">Exit For and Continue For</span></span>

<span data-ttu-id="3e6c9-152">L' `Exit For` istruzione esce immediatamente da `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="3e6c9-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="3e6c9-153">esegue il ciclo e trasferisce il controllo all'istruzione che segue l' `Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="3e6c9-154">L' `Continue For` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="3e6c9-155">Per ulteriori informazioni, vedere [istruzione continue](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-155">For more information, see [Continue Statement](continue-statement.md).</span></span>

<span data-ttu-id="3e6c9-156">Nell'esempio seguente viene illustrato l'utilizzo delle `Continue For` istruzioni e `Exit For` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="3e6c9-157">È possibile inserire un numero qualsiasi di `Exit For` istruzioni in un `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="3e6c9-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="3e6c9-158">loop.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-158">loop.</span></span> <span data-ttu-id="3e6c9-159">Se utilizzato all'interno di `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="3e6c9-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="3e6c9-160">esegue il loop, `Exit For` esce dal ciclo più interno e trasferisce il controllo al successivo livello di nidificazione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="3e6c9-161">`Exit For`viene spesso usato dopo la valutazione di una condizione, ad esempio in un `If` ... `Then` ...`Else` struttura).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="3e6c9-162">Può essere utile usare `Exit For` per le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e6c9-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="3e6c9-163">La continuazione dell'iterazione non è necessaria o impossibile.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="3e6c9-164">Questa condizione può essere creata da un valore errato o da una richiesta di terminazione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="3e6c9-165">A `Try` ... `Catch` ...`Finally` l'istruzione rileva un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="3e6c9-166">È possibile utilizzare `Exit For` alla fine del `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="3e6c9-167">Si dispone di un ciclo infinito, ovvero un ciclo che può eseguire un numero di volte elevato o addirittura infinito.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="3e6c9-168">Se si rileva una condizione di questo tipo, è possibile utilizzare `Exit For` per eseguire l'escape del ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="3e6c9-169">Per ulteriori informazioni, vedere [... Istruzione Loop](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-169">For more information, see [Do...Loop Statement](do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="3e6c9-170">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="3e6c9-170">Technical Implementation</span></span>

<span data-ttu-id="3e6c9-171">Quando `For` viene avviato un ciclo... `Next` , Visual Basic valuta `start` , `end` e `step` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="3e6c9-172">Visual Basic valuta questi valori solo in questo momento e quindi assegna `start` a `counter` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="3e6c9-173">Prima dell'esecuzione del blocco di istruzioni, Visual Basic viene confrontato `counter` con `end` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="3e6c9-174">Se `counter` è già maggiore del `end` valore (o minore se `step` è negativo), il `For` ciclo termina e il controllo passa all'istruzione che segue l' `Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="3e6c9-175">In caso contrario, viene eseguito il blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="3e6c9-176">Ogni volta che Visual Basic rileva l' `Next` istruzione, viene incrementato `counter` di e viene `step` restituito all' `For` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="3e6c9-177">Anche in questo caso viene confrontato `counter` con `end` e di nuovo esegue il blocco o esce dal ciclo, a seconda del risultato.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="3e6c9-178">Questo processo continua fino a quando non `counter` `end` `Exit For` vengono rilevati i passaggi o un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="3e6c9-179">Il ciclo non viene arrestato fino a quando non `counter` viene superato `end` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="3e6c9-180">Se `counter` è uguale a `end` , il ciclo continua.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="3e6c9-181">Il confronto che determina se eseguire il blocco è `counter`  <=  `end` se `step` è positivo e `counter`  >=  `end` se `step` è negativo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="3e6c9-182">Se si modifica il valore di `counter` all'interno di un ciclo, il codice potrebbe essere più difficile da leggere ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="3e6c9-183">La modifica del valore di `start` , `end` o `step` non influisce sui valori di iterazione che sono stati determinati quando il ciclo è stato immesso per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="3e6c9-184">Se si annidano i cicli, il compilatore segnala un errore se rileva l' `Next` istruzione di un livello di nidificazione esterno prima dell' `Next` istruzione di un livello interno.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="3e6c9-185">Tuttavia, il compilatore può rilevare questo errore di sovrapposizione solo se si specifica `counter` in ogni `Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="3e6c9-186">Argomento Step</span><span class="sxs-lookup"><span data-stu-id="3e6c9-186">Step Argument</span></span>

<span data-ttu-id="3e6c9-187">Il valore di `step` può essere positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="3e6c9-188">Questo parametro determina l'elaborazione del ciclo in base alla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="3e6c9-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="3e6c9-189">**Valore passaggio**</span><span class="sxs-lookup"><span data-stu-id="3e6c9-189">**Step value**</span></span>|<span data-ttu-id="3e6c9-190">**Il ciclo viene eseguito se**</span><span class="sxs-lookup"><span data-stu-id="3e6c9-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="3e6c9-191">Positivo o zero</span><span class="sxs-lookup"><span data-stu-id="3e6c9-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="3e6c9-192">Negative</span><span class="sxs-lookup"><span data-stu-id="3e6c9-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="3e6c9-193">Il valore predefinito di `step` è 1.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-193">The default value of `step` is 1.</span></span>

### <a name="counter-argument"></a><a name="BKMK_Counter"></a><span data-ttu-id="3e6c9-194">Argomento contatore</span><span class="sxs-lookup"><span data-stu-id="3e6c9-194">Counter Argument</span></span>

<span data-ttu-id="3e6c9-195">La tabella seguente indica se `counter` definisce una nuova variabile locale con ambito per l'intero `For…Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="3e6c9-196">Questa decisione dipende dal fatto che `datatype` sia presente e che sia `counter` già definito.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="3e6c9-197">È `datatype` presente?</span><span class="sxs-lookup"><span data-stu-id="3e6c9-197">Is `datatype` present?</span></span>|<span data-ttu-id="3e6c9-198">È `counter` già definito?</span><span class="sxs-lookup"><span data-stu-id="3e6c9-198">Is `counter` already defined?</span></span>|<span data-ttu-id="3e6c9-199">Risultato (se `counter` definisce una nuova variabile locale con ambito per l'intero `For...Next` ciclo)</span><span class="sxs-lookup"><span data-stu-id="3e6c9-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="3e6c9-200">No</span><span class="sxs-lookup"><span data-stu-id="3e6c9-200">No</span></span>|<span data-ttu-id="3e6c9-201">Sì</span><span class="sxs-lookup"><span data-stu-id="3e6c9-201">Yes</span></span>|<span data-ttu-id="3e6c9-202">No, perché `counter` è già definito.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="3e6c9-203">Se l'ambito di `counter` non è locale alla routine, viene generato un avviso in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="3e6c9-204">No</span><span class="sxs-lookup"><span data-stu-id="3e6c9-204">No</span></span>|<span data-ttu-id="3e6c9-205">No</span><span class="sxs-lookup"><span data-stu-id="3e6c9-205">No</span></span>|<span data-ttu-id="3e6c9-206">Sì.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-206">Yes.</span></span> <span data-ttu-id="3e6c9-207">Il tipo di dati viene dedotto dalle `start` espressioni, `end` e `step` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="3e6c9-208">Per informazioni sull'inferenza del tipo, vedere [istruzione Option deduce](option-infer-statement.md) e [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-208">For information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="3e6c9-209">Sì</span><span class="sxs-lookup"><span data-stu-id="3e6c9-209">Yes</span></span>|<span data-ttu-id="3e6c9-210">Sì</span><span class="sxs-lookup"><span data-stu-id="3e6c9-210">Yes</span></span>|<span data-ttu-id="3e6c9-211">Sì, ma solo se la `counter` variabile esistente è definita all'esterno della routine.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="3e6c9-212">Tale variabile rimane separata.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-212">That variable remains separate.</span></span> <span data-ttu-id="3e6c9-213">Se l'ambito della variabile esistente `counter` è locale alla procedura, si verificherà un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="3e6c9-214">Sì</span><span class="sxs-lookup"><span data-stu-id="3e6c9-214">Yes</span></span>|<span data-ttu-id="3e6c9-215">No</span><span class="sxs-lookup"><span data-stu-id="3e6c9-215">No</span></span>|<span data-ttu-id="3e6c9-216">Sì.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-216">Yes.</span></span>|

<span data-ttu-id="3e6c9-217">Il tipo di dati di `counter` determina il tipo di iterazione, che deve essere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e6c9-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="3e6c9-218">`Byte`,, `SByte` , `UShort` `Short` , `UInteger` , `Integer` , `ULong` , `Long` , `Decimal` , `Single` O `Double` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="3e6c9-219">Enumerazione dichiarata tramite un' [istruzione enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-219">An enumeration that you declare by using an [Enum Statement](enum-statement.md).</span></span>

- <span data-ttu-id="3e6c9-220">Valore `Object`.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-220">An `Object`.</span></span>

- <span data-ttu-id="3e6c9-221">Tipo `T` che dispone degli operatori seguenti, dove `B` è un tipo che può essere utilizzato in un' `Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="3e6c9-222">Facoltativamente, è possibile specificare la `counter` variabile nell' `Next` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="3e6c9-223">Questa sintassi migliora la leggibilità del programma, soprattutto se sono presenti cicli nidificati `For` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="3e6c9-224">È necessario specificare la variabile visualizzata nell' `For` istruzione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="3e6c9-225">Le `start` `end` espressioni, e `step` possono restituire qualsiasi tipo di dati che viene ampliato al tipo di `counter` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="3e6c9-226">Se si utilizza un tipo definito dall'utente per `counter` , potrebbe essere necessario definire l' `CType` operatore di conversione per convertire i tipi di `start` , `end` o nel `step` tipo di `counter` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="3e6c9-227">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e6c9-227">Example</span></span>

<span data-ttu-id="3e6c9-228">Nell'esempio seguente vengono rimossi tutti gli elementi da un elenco generico.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="3e6c9-229">Anziché [per ogni... Nell'istruzione successiva](for-each-next-statement.md), nell'esempio viene illustrata un' `For` istruzione... che esegue l' `Next` iterazione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-229">Instead of a [For Each...Next Statement](for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="3e6c9-230">L'esempio usa questa tecnica perché il `removeAt` metodo fa sì che gli elementi dopo l'elemento rimosso abbiano un valore di indice inferiore.</span><span class="sxs-lookup"><span data-stu-id="3e6c9-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="3e6c9-231">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e6c9-231">Example</span></span>

<span data-ttu-id="3e6c9-232">Nell'esempio seguente viene iterata un'enumerazione dichiarata tramite un' [istruzione enum](enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3e6c9-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="3e6c9-233">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e6c9-233">Example</span></span>

<span data-ttu-id="3e6c9-234">Nell'esempio seguente, i parametri dell'istruzione usano una classe con overload di operatori per gli `+` `-` operatori,, `>=` e `<=` .</span><span class="sxs-lookup"><span data-stu-id="3e6c9-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="3e6c9-235">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e6c9-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="3e6c9-236">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="3e6c9-236">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="3e6c9-237">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="3e6c9-237">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="3e6c9-238">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="3e6c9-238">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="3e6c9-239">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="3e6c9-239">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="3e6c9-240">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="3e6c9-240">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="3e6c9-241">raccolte</span><span class="sxs-lookup"><span data-stu-id="3e6c9-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
