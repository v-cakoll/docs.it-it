---
title: Istruzione If...Then...Else
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351168"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="ea7ff-102">Istruzione If...Then...Else (Visual Basic) |</span><span class="sxs-lookup"><span data-stu-id="ea7ff-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="ea7ff-103">Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea7ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea7ff-104">Syntax</span></span>

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a><span data-ttu-id="ea7ff-105">Collegamenti rapidi al codice di esempio</span><span class="sxs-lookup"><span data-stu-id="ea7ff-105">Quick links to example code</span></span>

<span data-ttu-id="ea7ff-106">Questo articolo include diversi esempi che illustrano gli usi dell'istruzione `If`...`Then`...`Else`:</span><span class="sxs-lookup"><span data-stu-id="ea7ff-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="ea7ff-107">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="ea7ff-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="ea7ff-108">Esempio di sintassi annidata</span><span class="sxs-lookup"><span data-stu-id="ea7ff-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="ea7ff-109">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="ea7ff-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="ea7ff-110">Parti</span><span class="sxs-lookup"><span data-stu-id="ea7ff-110">Parts</span></span>

`condition` \
<span data-ttu-id="ea7ff-111">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-111">Required.</span></span> <span data-ttu-id="ea7ff-112">Espressione.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-112">Expression.</span></span> <span data-ttu-id="ea7ff-113">Deve restituire `True` o `False`o a un tipo di dati convertibile in modo implicito in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="ea7ff-114">Se l'espressione è una variabile di `Boolean` [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) che non restituisce [alcun](../../../visual-basic/language-reference/nothing.md)valore, la condizione viene considerata come se l'espressione venisse `False`e i blocchi di `ElseIf` vengono valutati se esistono o se il `Else` blocco viene eseguito se esiste.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="ea7ff-115">Obbligatorio nella sintassi a riga singola; facoltativo nella sintassi su più righe.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="ea7ff-116">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-116">Optional.</span></span> <span data-ttu-id="ea7ff-117">Una o più istruzioni che seguono `If`...`Then` che vengono eseguite se `condition` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="ea7ff-118">Obbligatorio se è presente `ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="ea7ff-119">Espressione.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-119">Expression.</span></span> <span data-ttu-id="ea7ff-120">Deve restituire `True` o `False`o a un tipo di dati convertibile in modo implicito in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="ea7ff-121">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-121">Optional.</span></span> <span data-ttu-id="ea7ff-122">Una o più istruzioni che seguono `ElseIf`...`Then` che vengono eseguite se `elseifcondition` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="ea7ff-123">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-123">Optional.</span></span> <span data-ttu-id="ea7ff-124">Una o più istruzioni eseguite se nessuna `condition` o espressione `elseifcondition` precedente restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="ea7ff-125">Termina la versione multiriga del blocco `If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea7ff-126">Note</span><span class="sxs-lookup"><span data-stu-id="ea7ff-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="ea7ff-127">Sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="ea7ff-127">Multiline syntax</span></span>

<span data-ttu-id="ea7ff-128">Quando viene rilevata un'istruzione `If`...`Then`...`Else`, `condition` viene testato.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="ea7ff-129">Se `condition` è `True`, vengono eseguite le istruzioni che seguono `Then`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="ea7ff-130">Se `condition` è `False`, ogni istruzione `ElseIf`, se presente, viene valutata in ordine.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="ea7ff-131">Quando viene individuato un `True` `elseifcondition`, vengono eseguite le istruzioni immediatamente successive al `ElseIf` associato.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="ea7ff-132">Se nessuna `elseifcondition` restituisce `True`o se non sono presenti istruzioni `ElseIf`, vengono eseguite le istruzioni che seguono `Else`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="ea7ff-133">Dopo aver eseguito le istruzioni che seguono `Then`, `ElseIf`o `Else`, l'esecuzione continua con l'istruzione che segue `End If`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="ea7ff-134">Le clausole `ElseIf` e `Else` sono entrambe facoltative.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="ea7ff-135">In un'istruzione `If`...`Then`...`Else` è possibile avere un numero di clausole di `ElseIf`, ma non è possibile visualizzare una clausola `ElseIf` dopo una clausola `Else`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="ea7ff-136">le istruzioni `If`...`Then`...`Else` possono essere annidate l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="ea7ff-137">Nella sintassi su più righe, l'istruzione `If` deve essere l'unica istruzione nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="ea7ff-138">Le istruzioni `ElseIf`, `Else`e `End If` possono essere precedute solo da un'etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="ea7ff-139">Il blocco `If`...`Then`...`Else` deve terminare con un'istruzione `End If`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="ea7ff-140">L'oggetto [Select... L'istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) può essere più utile quando si valuta una singola espressione con diversi valori possibili.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="ea7ff-141">Sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="ea7ff-141">Single-Line syntax</span></span>

<span data-ttu-id="ea7ff-142">È possibile utilizzare la sintassi a riga singola per una singola condizione con codice da eseguire se è true.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="ea7ff-143">Tuttavia, la sintassi a più righe fornisce maggiore struttura e flessibilità ed è più facile da leggere, gestire ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="ea7ff-144">Di seguito viene esaminata la parola chiave `Then` per determinare se un'istruzione è una `If`a riga singola.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="ea7ff-145">Se non viene visualizzato alcun commento dopo `Then` sulla stessa riga, l'istruzione viene considerata come un'istruzione `If` a riga singola.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="ea7ff-146">Se `Then` è assente, deve essere l'inizio di un `If`a più righe...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="ea7ff-147">Nella sintassi a riga singola è possibile avere più istruzioni eseguite come risultato di una decisione `If`...`Then`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="ea7ff-148">Tutte le istruzioni devono trovarsi sulla stessa riga ed essere separate da due punti.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="ea7ff-149">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="ea7ff-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="ea7ff-150">Nell'esempio seguente viene illustrato l'utilizzo della sintassi su più righe dell'istruzione `If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="ea7ff-151">Esempio di sintassi annidata</span><span class="sxs-lookup"><span data-stu-id="ea7ff-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="ea7ff-152">Nell'esempio seguente sono contenute le istruzioni annidate `If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="ea7ff-153">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="ea7ff-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="ea7ff-154">Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.</span><span class="sxs-lookup"><span data-stu-id="ea7ff-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="ea7ff-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea7ff-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="ea7ff-156">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="ea7ff-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="ea7ff-157">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="ea7ff-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="ea7ff-158">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="ea7ff-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="ea7ff-159">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="ea7ff-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="ea7ff-160">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea7ff-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="ea7ff-161">Operatore If</span><span class="sxs-lookup"><span data-stu-id="ea7ff-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
