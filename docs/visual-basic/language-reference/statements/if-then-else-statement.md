---
title: Istruzione If...Then...Else (Visual Basic) |
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="8ecec-102">Istruzione If...Then...Else (Visual Basic) |</span><span class="sxs-lookup"><span data-stu-id="8ecec-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="8ecec-103">Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="8ecec-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ecec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ecec-104">Syntax</span></span>  
  
```  
' Multiple-line syntax:  
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
  
## <a name="parts"></a><span data-ttu-id="8ecec-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8ecec-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="8ecec-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ecec-106">Required.</span></span> <span data-ttu-id="8ecec-107">Espressione.</span><span class="sxs-lookup"><span data-stu-id="8ecec-107">Expression.</span></span> <span data-ttu-id="8ecec-108">Deve restituire `True` o `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-108">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="8ecec-109">Se l'espressione è un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variabile che restituisce [nulla](../../../visual-basic/language-reference/nothing.md), la condizione viene considerata come se l'espressione non è `True`e `Else` blocco eseguito.</span><span class="sxs-lookup"><span data-stu-id="8ecec-109">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is not `True`, and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="8ecec-110">Richiesto nella sintassi a riga singola; facoltativo per la sintassi di più righe.</span><span class="sxs-lookup"><span data-stu-id="8ecec-110">Required in the single-line syntax; optional in the multiple-line syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="8ecec-111">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8ecec-111">Optional.</span></span> <span data-ttu-id="8ecec-112">Uno o più istruzioni che seguono `If`... `Then` che vengono eseguite se `condition` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-112">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="8ecec-113">Obbligatorio se `ElseIf` è presente.</span><span class="sxs-lookup"><span data-stu-id="8ecec-113">Required if `ElseIf` is present.</span></span> <span data-ttu-id="8ecec-114">Espressione.</span><span class="sxs-lookup"><span data-stu-id="8ecec-114">Expression.</span></span> <span data-ttu-id="8ecec-115">Deve restituire `True` o `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-115">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="8ecec-116">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8ecec-116">Optional.</span></span> <span data-ttu-id="8ecec-117">Uno o più istruzioni che seguono `ElseIf`... `Then` che vengono eseguite se `elseifcondition` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-117">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="8ecec-118">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8ecec-118">Optional.</span></span> <span data-ttu-id="8ecec-119">Una o più istruzioni eseguite se non precedente `condition` o `elseifcondition` espressione viene valutata `True`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-119">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="8ecec-120">Termina il `If`... `Then`... `Else` blocco.</span><span class="sxs-lookup"><span data-stu-id="8ecec-120">Terminates the `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ecec-121">Note</span><span class="sxs-lookup"><span data-stu-id="8ecec-121">Remarks</span></span>  
  
## <a name="multiple-line-syntax"></a><span data-ttu-id="8ecec-122">Sintassi di più righe</span><span class="sxs-lookup"><span data-stu-id="8ecec-122">Multiple-Line Syntax</span></span>  
 <span data-ttu-id="8ecec-123">Quando un `If`... `Then`... `Else` viene rilevata l'istruzione, `condition` viene eseguito il test.</span><span class="sxs-lookup"><span data-stu-id="8ecec-123">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="8ecec-124">Se `condition` è `True`, le istruzioni che seguono `Then` vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="8ecec-124">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="8ecec-125">Se `condition` è `False`, ogni `ElseIf` istruzione (se presenti) viene considerata nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="8ecec-125">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="8ecec-126">Quando un `True``elseifcondition` viene trovato, le istruzioni che seguono immediatamente associato `ElseIf` vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="8ecec-126">When a `True``elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="8ecec-127">Se non `elseifcondition` restituisce `True`, o se non esistono alcun `ElseIf` istruzioni, le istruzioni che seguono `Else` vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="8ecec-127">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="8ecec-128">Dopo l'esecuzione di istruzioni che seguono `Then`, `ElseIf`, o `Else`, l'esecuzione continua con la seguente istruzione `End If`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-128">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="8ecec-129">Il `ElseIf` e `Else` clausole sono entrambi facoltativi.</span><span class="sxs-lookup"><span data-stu-id="8ecec-129">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="8ecec-130">È possibile specificare qualsiasi numero `ElseIf` clausole come si desidera che un `If`... `Then`... `Else` istruzione, ma non `ElseIf` clausola può comparire dopo un `Else` clausola.</span><span class="sxs-lookup"><span data-stu-id="8ecec-130">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="8ecec-131">`If`... `Then`... `Else` possono essere annidate all'interno di altro.</span><span class="sxs-lookup"><span data-stu-id="8ecec-131">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="8ecec-132">Nella sintassi di più righe, il `If` istruzione deve essere l'unica istruzione nella prima riga.</span><span class="sxs-lookup"><span data-stu-id="8ecec-132">In the multiple-line syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="8ecec-133">Il `ElseIf`, `Else`, e `End If` istruzioni possono essere precedute solo da un'etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="8ecec-133">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="8ecec-134">Il `If`... `Then`... `Else` blocco deve terminare con un `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8ecec-134">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="8ecec-135">Il [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) potrebbero essere più utili quando si valuta una singola espressione che dispone di più valori.</span><span class="sxs-lookup"><span data-stu-id="8ecec-135">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
## <a name="single-line-syntax"></a><span data-ttu-id="8ecec-136">Sintassi a riga singola</span><span class="sxs-lookup"><span data-stu-id="8ecec-136">Single-Line Syntax</span></span>  
 <span data-ttu-id="8ecec-137">Per eseguire test breve e semplice, è possibile utilizzare la sintassi a riga singola.</span><span class="sxs-lookup"><span data-stu-id="8ecec-137">You can use the single-line syntax for short, simple tests.</span></span> <span data-ttu-id="8ecec-138">Tuttavia, la sintassi di più righe offre maggiore flessibilità e struttura e viene in genere più facile leggere, gestione e debug.</span><span class="sxs-lookup"><span data-stu-id="8ecec-138">However, the multiple-line syntax provides more structure and flexibility and is usually easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="8ecec-139">Di seguito il `Then` parola chiave viene esaminato per determinare se un'istruzione è una riga singola `If`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-139">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="8ecec-140">Se diverso da un commento viene visualizzato dopo `Then` sulla stessa riga, l'istruzione viene considerato come una riga singola `If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8ecec-140">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="8ecec-141">Se `Then` è assente, deve essere l'inizio di una riga di più `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="8ecec-141">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="8ecec-142">Nella sintassi a riga singola, è possibile inserire più istruzioni eseguite come risultato di un `If`... `Then` delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="8ecec-142">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="8ecec-143">Tutte le istruzioni devono essere nella stessa riga e di essere separate da virgola.</span><span class="sxs-lookup"><span data-stu-id="8ecec-143">All statements must be on the same line and be separated by colons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ecec-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ecec-144">Example</span></span>  
 <span data-ttu-id="8ecec-145">Nell'esempio seguente viene illustrato l'utilizzo della sintassi di più righe di `If`... `Then`... `Else` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8ecec-145">The following example illustrates the use of the multiple-line syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="8ecec-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ecec-146">Example</span></span>  
 <span data-ttu-id="8ecec-147">Nell'esempio seguente viene nidificata `If`... `Then`... `Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8ecec-147">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="8ecec-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ecec-148">Example</span></span>  
 <span data-ttu-id="8ecec-149">Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.</span><span class="sxs-lookup"><span data-stu-id="8ecec-149">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8ecec-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ecec-150">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="8ecec-151">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="8ecec-151">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="8ecec-152">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="8ecec-152">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="8ecec-153">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="8ecec-153">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="8ecec-154">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="8ecec-154">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="8ecec-155">Operatori logici e bit per bit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ecec-155">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="8ecec-156">Operatore If</span><span class="sxs-lookup"><span data-stu-id="8ecec-156">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
