---
title: Istruzione If...Then...Else (Visual Basic) |
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
ms.openlocfilehash: 97ac8c82df14eb5ddc5e26fdaddf61cc774a0476
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046578"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="0b600-102">Istruzione If...Then...Else (Visual Basic) |</span><span class="sxs-lookup"><span data-stu-id="0b600-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="0b600-103">Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="0b600-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b600-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b600-104">Syntax</span></span>

```
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="0b600-105">Collegamenti rapidi al codice di esempio</span><span class="sxs-lookup"><span data-stu-id="0b600-105">Quick links to example code</span></span>

<span data-ttu-id="0b600-106">Questo articolo include diversi esempi che illustrano gli `If`usi del... `Then`... `Else` istruzione:</span><span class="sxs-lookup"><span data-stu-id="0b600-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="0b600-107">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="0b600-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="0b600-108">Esempio di sintassi annidata</span><span class="sxs-lookup"><span data-stu-id="0b600-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="0b600-109">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="0b600-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="0b600-110">Parti</span><span class="sxs-lookup"><span data-stu-id="0b600-110">Parts</span></span>

`condition` \
<span data-ttu-id="0b600-111">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="0b600-111">Required.</span></span> <span data-ttu-id="0b600-112">Espressione.</span><span class="sxs-lookup"><span data-stu-id="0b600-112">Expression.</span></span> <span data-ttu-id="0b600-113">Deve restituire `True` o `False`oppure a un tipo di dati convertibile in modo implicito in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0b600-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="0b600-114">Se l'espressione è una variabile [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` che restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), la condizione viene considerata come se l'espressione è `False` e il `Else` blocco viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0b600-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>

`Then` \
<span data-ttu-id="0b600-115">Obbligatorio nella sintassi a riga singola; facoltativo nella sintassi su più righe.</span><span class="sxs-lookup"><span data-stu-id="0b600-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="0b600-116">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b600-116">Optional.</span></span> <span data-ttu-id="0b600-117">Una o più istruzioni che `If`seguono... che vengono eseguite se `condition` restituisce `True`. `Then`</span><span class="sxs-lookup"><span data-stu-id="0b600-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="0b600-118">Obbligatorio se `ElseIf` è presente.</span><span class="sxs-lookup"><span data-stu-id="0b600-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="0b600-119">Espressione.</span><span class="sxs-lookup"><span data-stu-id="0b600-119">Expression.</span></span> <span data-ttu-id="0b600-120">Deve restituire `True` o `False`oppure a un tipo di dati convertibile in modo implicito in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0b600-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="0b600-121">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b600-121">Optional.</span></span> <span data-ttu-id="0b600-122">Una o più istruzioni che `ElseIf`seguono... che vengono eseguite se `elseifcondition` restituisce `True`. `Then`</span><span class="sxs-lookup"><span data-stu-id="0b600-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="0b600-123">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0b600-123">Optional.</span></span> <span data-ttu-id="0b600-124">Una o più istruzioni eseguite se nessuna espressione o `condition` `elseifcondition` precedente restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="0b600-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="0b600-125">Termina la versione multiriga di `If`... `Then`... `Else` blocca.</span><span class="sxs-lookup"><span data-stu-id="0b600-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b600-126">Note</span><span class="sxs-lookup"><span data-stu-id="0b600-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="0b600-127">Sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="0b600-127">Multiline syntax</span></span>

<span data-ttu-id="0b600-128">Quando un `If`... `Then`... viene rilevata `condition` l'istruzione, viene testata. `Else`</span><span class="sxs-lookup"><span data-stu-id="0b600-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="0b600-129">Se `condition` `Then` è `True`, vengono eseguite le istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0b600-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="0b600-130">Se `condition` è `False`, ogni`ElseIf` istruzione, se presente, viene valutata in ordine.</span><span class="sxs-lookup"><span data-stu-id="0b600-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="0b600-131">Quando viene `True` trovato un oggetto `elseifcondition` , vengono eseguite le istruzioni immediatamente `ElseIf` successive all'oggetto associato.</span><span class="sxs-lookup"><span data-stu-id="0b600-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="0b600-132">Se nessun `elseifcondition` oggetto restituisce `True` ose`Else` non sono presenti istruzioni,verrannoeseguiteleistruzioniseguenti.`ElseIf`</span><span class="sxs-lookup"><span data-stu-id="0b600-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="0b600-133">Dopo l'esecuzione delle istruzioni che `Then`seguono `ElseIf`, o `Else`, l'esecuzione continua con l'istruzione `End If`seguente.</span><span class="sxs-lookup"><span data-stu-id="0b600-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="0b600-134">Le `ElseIf` clausole e `Else` sono entrambe facoltative.</span><span class="sxs-lookup"><span data-stu-id="0b600-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="0b600-135">È possibile avere `ElseIf` tutte le clausole desiderate `If`in... `Then`... `Else` ma `Else` non `ElseIf` può comparire dopo una clausola.</span><span class="sxs-lookup"><span data-stu-id="0b600-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="0b600-136">`If`... `Then`... `Else` le istruzioni possono essere nidificate l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="0b600-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="0b600-137">Nella sintassi su più righe, `If` l'istruzione deve essere l'unica istruzione nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="0b600-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="0b600-138">Le `ElseIf`istruzioni `Else`, e`End If` possono essere precedute solo da un'etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="0b600-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="0b600-139">`If`... `Then`... il blocco deve terminare con `End If` un'istruzione. `Else`</span><span class="sxs-lookup"><span data-stu-id="0b600-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="0b600-140">L'oggetto [Select... L'istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) può essere più utile quando si valuta una singola espressione con diversi valori possibili.</span><span class="sxs-lookup"><span data-stu-id="0b600-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="0b600-141">Sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="0b600-141">Single-Line syntax</span></span>

<span data-ttu-id="0b600-142">È possibile utilizzare la sintassi a riga singola per una singola condizione con codice da eseguire se è true.</span><span class="sxs-lookup"><span data-stu-id="0b600-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="0b600-143">Tuttavia, la sintassi a più righe fornisce maggiore struttura e flessibilità ed è più facile da leggere, gestire ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="0b600-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="0b600-144">Di seguito viene `Then` esaminata la parola chiave per determinare se un'istruzione è a riga `If`singola.</span><span class="sxs-lookup"><span data-stu-id="0b600-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="0b600-145">Se viene visualizzato un valore diverso da un `Then` commento dopo sulla stessa riga, l'istruzione viene considerata come un'istruzione a `If` riga singola.</span><span class="sxs-lookup"><span data-stu-id="0b600-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="0b600-146">Se `Then` è assente, deve essere l'inizio di una riga a più `If`righe... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="0b600-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="0b600-147">Nella sintassi a riga singola è possibile eseguire più istruzioni come risultato di `If`... `Then` decisione.</span><span class="sxs-lookup"><span data-stu-id="0b600-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="0b600-148">Tutte le istruzioni devono trovarsi sulla stessa riga ed essere separate da due punti.</span><span class="sxs-lookup"><span data-stu-id="0b600-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="0b600-149">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="0b600-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="0b600-150">Nell'esempio seguente viene illustrato l'utilizzo della sintassi multiriga di `If`... `Then`... `Else` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0b600-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="0b600-151">Esempio di sintassi annidata</span><span class="sxs-lookup"><span data-stu-id="0b600-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="0b600-152">L'esempio seguente contiene un `If`oggetto annidato... `Then`... `Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="0b600-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="0b600-153">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="0b600-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="0b600-154">Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.</span><span class="sxs-lookup"><span data-stu-id="0b600-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="0b600-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b600-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="0b600-156">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="0b600-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="0b600-157">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="0b600-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="0b600-158">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="0b600-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="0b600-159">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="0b600-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="0b600-160">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b600-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="0b600-161">Operatore If</span><span class="sxs-lookup"><span data-stu-id="0b600-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
