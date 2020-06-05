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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404589"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="f04c0-102">Istruzione If...Then...Else (Visual Basic) |</span><span class="sxs-lookup"><span data-stu-id="f04c0-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="f04c0-103">Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f04c0-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="f04c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f04c0-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="f04c0-105">Collegamenti rapidi al codice di esempio</span><span class="sxs-lookup"><span data-stu-id="f04c0-105">Quick links to example code</span></span>

<span data-ttu-id="f04c0-106">Questo articolo include diversi esempi che illustrano gli usi del `If` ... `Then` ...`Else` istruzione</span><span class="sxs-lookup"><span data-stu-id="f04c0-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="f04c0-107">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="f04c0-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="f04c0-108">Esempio di sintassi annidata</span><span class="sxs-lookup"><span data-stu-id="f04c0-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="f04c0-109">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="f04c0-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="f04c0-110">Parti</span><span class="sxs-lookup"><span data-stu-id="f04c0-110">Parts</span></span>

`condition` \
<span data-ttu-id="f04c0-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f04c0-111">Required.</span></span> <span data-ttu-id="f04c0-112">Espressione.</span><span class="sxs-lookup"><span data-stu-id="f04c0-112">Expression.</span></span> <span data-ttu-id="f04c0-113">Deve restituire `True` o oppure `False` a un tipo di dati convertibile in modo implicito in `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="f04c0-114">Se l'espressione è una variabile [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` che non restituisce [alcun](../nothing.md)valore, la condizione viene considerata come se l'espressione è `False` e i `ElseIf` blocchi vengono valutati se esistono oppure il `Else` blocco viene eseguito se esistente.</span><span class="sxs-lookup"><span data-stu-id="f04c0-114">If the expression is a [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="f04c0-115">Obbligatorio nella sintassi a riga singola; facoltativo nella sintassi su più righe.</span><span class="sxs-lookup"><span data-stu-id="f04c0-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="f04c0-116">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f04c0-116">Optional.</span></span> <span data-ttu-id="f04c0-117">Una o più istruzioni `If` che seguono... `Then` che vengono eseguite se `condition` restituisce `True` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="f04c0-118">Obbligatorio se `ElseIf` è presente.</span><span class="sxs-lookup"><span data-stu-id="f04c0-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="f04c0-119">Espressione.</span><span class="sxs-lookup"><span data-stu-id="f04c0-119">Expression.</span></span> <span data-ttu-id="f04c0-120">Deve restituire `True` o oppure `False` a un tipo di dati convertibile in modo implicito in `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="f04c0-121">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f04c0-121">Optional.</span></span> <span data-ttu-id="f04c0-122">Una o più istruzioni `ElseIf` che seguono... `Then` che vengono eseguite se `elseifcondition` restituisce `True` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="f04c0-123">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f04c0-123">Optional.</span></span> <span data-ttu-id="f04c0-124">Una o più istruzioni eseguite se nessuna `condition` espressione o precedente `elseifcondition` restituisce `True` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="f04c0-125">Termina la versione multiriga di `If` ... `Then` ...`Else` blocco.</span><span class="sxs-lookup"><span data-stu-id="f04c0-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="f04c0-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="f04c0-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="f04c0-127">Sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="f04c0-127">Multiline syntax</span></span>

<span data-ttu-id="f04c0-128">Quando un `If` ... `Then` ...`Else` viene rilevata l'istruzione, `condition` viene testata.</span><span class="sxs-lookup"><span data-stu-id="f04c0-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="f04c0-129">Se `condition` è `True` , vengono eseguite le istruzioni seguenti `Then` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="f04c0-130">Se `condition` è `False` , ogni `ElseIf` istruzione, se presente, viene valutata in ordine.</span><span class="sxs-lookup"><span data-stu-id="f04c0-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="f04c0-131">Quando `True` `elseifcondition` viene trovato un oggetto, vengono eseguite le istruzioni immediatamente successive all'oggetto associato `ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="f04c0-132">Se nessun `elseifcondition` `True` oggetto restituisce o se non sono presenti `ElseIf` istruzioni, verranno eseguite le istruzioni seguenti `Else` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="f04c0-133">Dopo l'esecuzione delle istruzioni che seguono `Then` , `ElseIf` o `Else` , l'esecuzione continua con l'istruzione seguente `End If` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="f04c0-134">Le `ElseIf` `Else` clausole e sono entrambe facoltative.</span><span class="sxs-lookup"><span data-stu-id="f04c0-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="f04c0-135">È possibile avere tutte le `ElseIf` clausole desiderate in `If` ... `Then` ...`Else` ma non `ElseIf` può comparire dopo una `Else` clausola.</span><span class="sxs-lookup"><span data-stu-id="f04c0-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="f04c0-136">`If`...`Then` ...`Else` le istruzioni possono essere nidificate l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="f04c0-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="f04c0-137">Nella sintassi su più righe, l' `If` istruzione deve essere l'unica istruzione nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="f04c0-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="f04c0-138">Le `ElseIf` `Else` istruzioni, e `End If` possono essere precedute solo da un'etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="f04c0-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="f04c0-139">.. `If` . `Then` ...`Else` il blocco deve terminare con un' `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f04c0-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="f04c0-140">L'oggetto [Select... L'istruzione case](select-case-statement.md) può essere più utile quando si valuta una singola espressione con diversi valori possibili.</span><span class="sxs-lookup"><span data-stu-id="f04c0-140">The [Select...Case Statement](select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="f04c0-141">Sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="f04c0-141">Single-Line syntax</span></span>

<span data-ttu-id="f04c0-142">È possibile utilizzare la sintassi a riga singola per una singola condizione con codice da eseguire se è true.</span><span class="sxs-lookup"><span data-stu-id="f04c0-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="f04c0-143">Tuttavia, la sintassi a più righe fornisce maggiore struttura e flessibilità ed è più facile da leggere, gestire ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="f04c0-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="f04c0-144">`Then`Di seguito viene esaminata la parola chiave per determinare se un'istruzione è a riga singola `If` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="f04c0-145">Se viene visualizzato un valore diverso da un commento dopo `Then` sulla stessa riga, l'istruzione viene considerata come un'istruzione a riga singola `If` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="f04c0-146">Se `Then` è assente, deve essere l'inizio di una riga a più righe `If` ... `Then` ...`Else`.</span><span class="sxs-lookup"><span data-stu-id="f04c0-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="f04c0-147">Nella sintassi a riga singola è possibile eseguire più istruzioni come risultato di una `If` decisione... `Then` .</span><span class="sxs-lookup"><span data-stu-id="f04c0-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="f04c0-148">Tutte le istruzioni devono trovarsi sulla stessa riga ed essere separate da due punti.</span><span class="sxs-lookup"><span data-stu-id="f04c0-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="f04c0-149">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="f04c0-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="f04c0-150">Nell'esempio seguente viene illustrato l'utilizzo della sintassi multiriga di `If` ... `Then` ...`Else` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f04c0-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="f04c0-151">Esempio di sintassi annidata</span><span class="sxs-lookup"><span data-stu-id="f04c0-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="f04c0-152">L'esempio seguente contiene un oggetto annidato `If` ... `Then` ...`Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f04c0-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="f04c0-153">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="f04c0-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="f04c0-154">Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.</span><span class="sxs-lookup"><span data-stu-id="f04c0-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="f04c0-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f04c0-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="f04c0-156">#If... Direttive then... #Else</span><span class="sxs-lookup"><span data-stu-id="f04c0-156">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
- [<span data-ttu-id="f04c0-157">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="f04c0-157">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="f04c0-158">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="f04c0-158">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="f04c0-159">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="f04c0-159">Decision Structures</span></span>](../../programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="f04c0-160">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f04c0-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="f04c0-161">Operatore If</span><span class="sxs-lookup"><span data-stu-id="f04c0-161">If Operator</span></span>](../operators/if-operator.md)
