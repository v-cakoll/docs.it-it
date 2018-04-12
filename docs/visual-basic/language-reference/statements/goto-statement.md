---
title: Istruzione GoTo
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22a6315e69cd6c797d462d0835e85bb1dde67dcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="goto-statement"></a><span data-ttu-id="9bfa8-102">Istruzione GoTo</span><span class="sxs-lookup"><span data-stu-id="9bfa8-102">GoTo Statement</span></span>
<span data-ttu-id="9bfa8-103">Branch in modo non condizionale in una riga specificata in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bfa8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bfa8-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="9bfa8-105">Parte</span><span class="sxs-lookup"><span data-stu-id="9bfa8-105">Part</span></span>  
 `line`  
 <span data-ttu-id="9bfa8-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-106">Required.</span></span> <span data-ttu-id="9bfa8-107">Qualsiasi etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bfa8-108">Note</span><span class="sxs-lookup"><span data-stu-id="9bfa8-108">Remarks</span></span>  
 <span data-ttu-id="9bfa8-109">Il `GoTo` istruzione di diramazione solo righe della routine in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="9bfa8-110">La riga deve avere un'etichetta che una riga `GoTo` può fare riferimento a.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="9bfa8-111">Per ulteriori informazioni, vedere [come: etichetta istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="9bfa8-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bfa8-112">`GoTo`istruzioni possono ostacolare la lettura e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="9bfa8-113">Se possibile, è possibile utilizzare una struttura di controllo.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="9bfa8-114">Per ulteriori informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="9bfa8-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="9bfa8-115">Non è possibile utilizzare un `GoTo` istruzione branch all'esterno di un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` in un'etichetta all'interno.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="9bfa8-116">Creazione di rami e costruzioni Try</span><span class="sxs-lookup"><span data-stu-id="9bfa8-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="9bfa8-117">All'interno di un `Try`... `Catch`... `Finally` costruzione, le regole seguenti si applicano a creare un ramo con il `GoTo` istruzione.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="9bfa8-118">Blocco o area geografica</span><span class="sxs-lookup"><span data-stu-id="9bfa8-118">Block or region</span></span>|<span data-ttu-id="9bfa8-119">Branching dall'esterno</span><span class="sxs-lookup"><span data-stu-id="9bfa8-119">Branching in from outside</span></span>|<span data-ttu-id="9bfa8-120">Branching all'esterno</span><span class="sxs-lookup"><span data-stu-id="9bfa8-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="9bfa8-121">`Try`blocco</span><span class="sxs-lookup"><span data-stu-id="9bfa8-121">`Try` block</span></span>|<span data-ttu-id="9bfa8-122">Solo da un `Catch` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9bfa8-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="9bfa8-123">Solo di fuori dell'intera costruzione</span><span class="sxs-lookup"><span data-stu-id="9bfa8-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="9bfa8-124">`Catch`blocco</span><span class="sxs-lookup"><span data-stu-id="9bfa8-124">`Catch` block</span></span>|<span data-ttu-id="9bfa8-125">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="9bfa8-125">Never allowed</span></span>|<span data-ttu-id="9bfa8-126">Solo di fuori dell'intera costruzione oppure il `Try` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9bfa8-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="9bfa8-127">`Finally`blocco</span><span class="sxs-lookup"><span data-stu-id="9bfa8-127">`Finally` block</span></span>|<span data-ttu-id="9bfa8-128">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="9bfa8-128">Never allowed</span></span>|<span data-ttu-id="9bfa8-129">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="9bfa8-129">Never allowed</span></span>|  
  
 <span data-ttu-id="9bfa8-130"><sup>1</sup> eventuale `Try`... `Catch`... `Finally` costruzione viene nidificata all'interno di un altro, un `Catch` può creare un ramo in blocco il `Try` blocco al proprio livello di nidificazione, ma non in qualsiasi altro `Try` blocco.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="9bfa8-131">Nidificate `Try`... `Catch`... `Finally` costruzione deve essere completamente contenuta in un `Try` o `Catch` blocco di costruzione entro il quale è annidata.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="9bfa8-132">La figura seguente mostra uno `Try` costruzione annidati all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="9bfa8-133">Vari rami tra i blocchi delle due costruzioni vengono indicati come validi o non valido.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="9bfa8-134">![Diagramma grafico dei rami in costruzioni Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="9bfa8-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="9bfa8-135">Validi e non validi i rami in costruzioni Try</span><span class="sxs-lookup"><span data-stu-id="9bfa8-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bfa8-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bfa8-136">Example</span></span>  
 <span data-ttu-id="9bfa8-137">L'esempio seguente usa il `GoTo` istruzione branch etichette di riga in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="9bfa8-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9bfa8-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bfa8-138">See Also</span></span>  
 [<span data-ttu-id="9bfa8-139">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="9bfa8-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="9bfa8-140">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="9bfa8-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="9bfa8-141">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="9bfa8-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="9bfa8-142">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="9bfa8-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="9bfa8-143">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="9bfa8-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="9bfa8-144">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="9bfa8-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="9bfa8-145">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="9bfa8-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="9bfa8-146">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="9bfa8-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
