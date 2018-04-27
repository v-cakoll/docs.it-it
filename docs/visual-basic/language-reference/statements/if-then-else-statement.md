---
title: Istruzione If...Then...Else (Visual Basic) |
ms.date: 04/16/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: conceptual
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
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1080a17cfcc493175c1e2f3527837030b4254bc2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="61ea1-102">Istruzione If...Then...Else (Visual Basic) |</span><span class="sxs-lookup"><span data-stu-id="61ea1-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="61ea1-103">Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="61ea1-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ea1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61ea1-104">Syntax</span></span>  
  
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="61ea1-105">Collegamenti rapidi a codice di esempio</span><span class="sxs-lookup"><span data-stu-id="61ea1-105">Quick links to example code</span></span>

<span data-ttu-id="61ea1-106">In questo articolo include diversi esempi che illustrano utilizzi del `If`... `Then`... `Else` istruzione:</span><span class="sxs-lookup"><span data-stu-id="61ea1-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="61ea1-107">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="61ea1-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="61ea1-108">Esempio di sintassi annidati</span><span class="sxs-lookup"><span data-stu-id="61ea1-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="61ea1-109">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="61ea1-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="61ea1-110">Parti</span><span class="sxs-lookup"><span data-stu-id="61ea1-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="61ea1-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="61ea1-111">Required.</span></span> <span data-ttu-id="61ea1-112">Espressione.</span><span class="sxs-lookup"><span data-stu-id="61ea1-112">Expression.</span></span> <span data-ttu-id="61ea1-113">Deve restituire `True` o `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="61ea1-114">Se l'espressione è un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variabile che restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), la condizione viene considerata come se l'espressione è `False` e il `Else` blocco viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="61ea1-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="61ea1-115">Obbligatorio nella sintassi a riga singola; parametro facoltativo nella sintassi su più righe.</span><span class="sxs-lookup"><span data-stu-id="61ea1-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="61ea1-116">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="61ea1-116">Optional.</span></span> <span data-ttu-id="61ea1-117">Uno o più istruzioni che seguono `If`... `Then` che vengono eseguite se `condition` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="61ea1-118">Obbligatorio se `ElseIf` è presente.</span><span class="sxs-lookup"><span data-stu-id="61ea1-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="61ea1-119">Espressione.</span><span class="sxs-lookup"><span data-stu-id="61ea1-119">Expression.</span></span> <span data-ttu-id="61ea1-120">Deve restituire `True` o `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="61ea1-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="61ea1-121">Optional.</span></span> <span data-ttu-id="61ea1-122">Uno o più istruzioni che seguono `ElseIf`... `Then` che vengono eseguite se `elseifcondition` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="61ea1-123">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="61ea1-123">Optional.</span></span> <span data-ttu-id="61ea1-124">Una o più istruzioni eseguite se non precedente `condition` o `elseifcondition` espressione viene valutata `True`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="61ea1-125">Termina la versione su più righe di `If`... `Then`... `Else` blocco.</span><span class="sxs-lookup"><span data-stu-id="61ea1-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61ea1-126">Note</span><span class="sxs-lookup"><span data-stu-id="61ea1-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="61ea1-127">Sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="61ea1-127">Multiline syntax</span></span>  
 <span data-ttu-id="61ea1-128">Quando un `If`... `Then`... `Else` viene rilevata l'istruzione, `condition` viene eseguito il test.</span><span class="sxs-lookup"><span data-stu-id="61ea1-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="61ea1-129">Se `condition` è `True`, le istruzioni che seguono `Then` vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="61ea1-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="61ea1-130">Se `condition` è `False`, ogni `ElseIf` istruzione (se presenti) viene considerata nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="61ea1-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="61ea1-131">Quando un `True` `elseifcondition` viene trovato, le istruzioni che seguono immediatamente associato `ElseIf` vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="61ea1-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="61ea1-132">Se non `elseifcondition` restituisce `True`, o se non esistono alcun `ElseIf` istruzioni, le istruzioni che seguono `Else` vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="61ea1-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="61ea1-133">Dopo l'esecuzione di istruzioni che seguono `Then`, `ElseIf`, o `Else`, l'esecuzione continua con la seguente istruzione `End If`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="61ea1-134">Il `ElseIf` e `Else` clausole sono entrambi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="61ea1-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="61ea1-135">È possibile specificare qualsiasi numero `ElseIf` clausole come si desidera che un `If`... `Then`... `Else` istruzione, ma non `ElseIf` clausola può comparire dopo un `Else` clausola.</span><span class="sxs-lookup"><span data-stu-id="61ea1-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="61ea1-136">`If`... `Then`... `Else` possono essere annidate all'interno di altro.</span><span class="sxs-lookup"><span data-stu-id="61ea1-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="61ea1-137">Nella sintassi su più righe, il `If` istruzione deve essere l'unica istruzione nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="61ea1-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="61ea1-138">Il `ElseIf`, `Else`, e `End If` istruzioni possono essere precedute solo da un'etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="61ea1-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="61ea1-139">Il `If`... `Then`... `Else` blocco deve terminare con un `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="61ea1-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="61ea1-140">Il [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) potrebbero essere più utili quando si valuta una singola espressione che dispone di più valori.</span><span class="sxs-lookup"><span data-stu-id="61ea1-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="61ea1-141">Sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="61ea1-141">Single-Line syntax</span></span>  
 <span data-ttu-id="61ea1-142">È possibile utilizzare la sintassi a riga singola per una singola condizione con il codice da eseguire se è true.</span><span class="sxs-lookup"><span data-stu-id="61ea1-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="61ea1-143">Tuttavia, la sintassi di più righe fornisce maggiore flessibilità e struttura ed è più facile da leggere, gestire ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="61ea1-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="61ea1-144">Di seguito il `Then` parola chiave viene esaminato per determinare se un'istruzione è una riga singola `If`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="61ea1-145">Se diverso da un commento viene visualizzato dopo `Then` sulla stessa riga, l'istruzione viene considerato come una riga singola `If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="61ea1-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="61ea1-146">Se `Then` è assente, deve essere l'inizio di una riga di più `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="61ea1-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="61ea1-147">Nella sintassi a riga singola, è possibile inserire più istruzioni eseguite come risultato di un `If`... `Then` delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="61ea1-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="61ea1-148">Tutte le istruzioni devono essere nella stessa riga e di essere separate da virgola.</span><span class="sxs-lookup"><span data-stu-id="61ea1-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="61ea1-149">Esempio di sintassi su più righe</span><span class="sxs-lookup"><span data-stu-id="61ea1-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="61ea1-150">Nell'esempio seguente viene illustrato l'utilizzo della sintassi di più righe il `If`... `Then`... `Else` istruzione.</span><span class="sxs-lookup"><span data-stu-id="61ea1-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a><span data-ttu-id="61ea1-151">Esempio di sintassi annidati</span><span class="sxs-lookup"><span data-stu-id="61ea1-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="61ea1-152">Nell'esempio seguente viene nidificata `If`... `Then`... `Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="61ea1-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="61ea1-153">Esempio di sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="61ea1-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="61ea1-154">Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.</span><span class="sxs-lookup"><span data-stu-id="61ea1-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a><span data-ttu-id="61ea1-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61ea1-155">See also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="61ea1-156">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="61ea1-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="61ea1-157">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="61ea1-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="61ea1-158">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="61ea1-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="61ea1-159">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="61ea1-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="61ea1-160">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61ea1-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="61ea1-161">Operatore If</span><span class="sxs-lookup"><span data-stu-id="61ea1-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
