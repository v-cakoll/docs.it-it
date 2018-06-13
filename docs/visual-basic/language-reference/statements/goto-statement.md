---
title: Istruzione GoTo
ms.date: 07/20/2015
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
ms.openlocfilehash: 27ebc677bab8b7f61a02408fddb30a6ec21c43cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604744"
---
# <a name="goto-statement"></a><span data-ttu-id="3c95a-102">Istruzione GoTo</span><span class="sxs-lookup"><span data-stu-id="3c95a-102">GoTo Statement</span></span>
<span data-ttu-id="3c95a-103">Branch in modo non condizionale in una riga specificata in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="3c95a-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c95a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c95a-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="3c95a-105">Parte</span><span class="sxs-lookup"><span data-stu-id="3c95a-105">Part</span></span>  
 `line`  
 <span data-ttu-id="3c95a-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3c95a-106">Required.</span></span> <span data-ttu-id="3c95a-107">Qualsiasi etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="3c95a-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c95a-108">Note</span><span class="sxs-lookup"><span data-stu-id="3c95a-108">Remarks</span></span>  
 <span data-ttu-id="3c95a-109">Il `GoTo` istruzione di diramazione solo righe della routine in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="3c95a-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="3c95a-110">La riga deve avere un'etichetta che una riga `GoTo` può fare riferimento a.</span><span class="sxs-lookup"><span data-stu-id="3c95a-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="3c95a-111">Per ulteriori informazioni, vedere [come: etichetta istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="3c95a-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c95a-112">`GoTo` le istruzioni possono rendere difficile da leggere e gestire codice.</span><span class="sxs-lookup"><span data-stu-id="3c95a-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="3c95a-113">Se possibile, è possibile utilizzare una struttura di controllo.</span><span class="sxs-lookup"><span data-stu-id="3c95a-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="3c95a-114">Per ulteriori informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c95a-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="3c95a-115">Non è possibile utilizzare un `GoTo` istruzione branch all'esterno di un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` in un'etichetta all'interno.</span><span class="sxs-lookup"><span data-stu-id="3c95a-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="3c95a-116">Creazione di rami e costruzioni Try</span><span class="sxs-lookup"><span data-stu-id="3c95a-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="3c95a-117">All'interno di un `Try`... `Catch`... `Finally` costruzione, le regole seguenti si applicano a creare un ramo con il `GoTo` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3c95a-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="3c95a-118">Blocco o area geografica</span><span class="sxs-lookup"><span data-stu-id="3c95a-118">Block or region</span></span>|<span data-ttu-id="3c95a-119">Branching dall'esterno</span><span class="sxs-lookup"><span data-stu-id="3c95a-119">Branching in from outside</span></span>|<span data-ttu-id="3c95a-120">Branching all'esterno</span><span class="sxs-lookup"><span data-stu-id="3c95a-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="3c95a-121">`Try` Blocco</span><span class="sxs-lookup"><span data-stu-id="3c95a-121">`Try` block</span></span>|<span data-ttu-id="3c95a-122">Solo da un `Catch` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3c95a-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="3c95a-123">Solo di fuori dell'intera costruzione</span><span class="sxs-lookup"><span data-stu-id="3c95a-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="3c95a-124">`Catch` Blocco</span><span class="sxs-lookup"><span data-stu-id="3c95a-124">`Catch` block</span></span>|<span data-ttu-id="3c95a-125">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="3c95a-125">Never allowed</span></span>|<span data-ttu-id="3c95a-126">Solo all'esterno dell'intera costruzione o per il `Try` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3c95a-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="3c95a-127">`Finally` Blocco</span><span class="sxs-lookup"><span data-stu-id="3c95a-127">`Finally` block</span></span>|<span data-ttu-id="3c95a-128">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="3c95a-128">Never allowed</span></span>|<span data-ttu-id="3c95a-129">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="3c95a-129">Never allowed</span></span>|  
  
 <span data-ttu-id="3c95a-130"><sup>1</sup> eventuale `Try`... `Catch`... `Finally` costruzione viene nidificata all'interno di un altro, una `Catch` blocco può creare rami nel `Try` blocco al proprio livello di nidificazione, ma non in qualsiasi altro `Try` blocco.</span><span class="sxs-lookup"><span data-stu-id="3c95a-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="3c95a-131">Nidificate `Try`... `Catch`... `Finally` costruzione deve essere completamente contenuta in un `Try` o `Catch` blocco di costruzione entro il quale è annidata.</span><span class="sxs-lookup"><span data-stu-id="3c95a-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="3c95a-132">La figura seguente mostra uno `Try` costruzione annidati all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="3c95a-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="3c95a-133">Vari rami tra i blocchi delle due costruzioni vengono indicati come validi o non valido.</span><span class="sxs-lookup"><span data-stu-id="3c95a-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="3c95a-134">![Diagramma grafico dei rami in costruzioni Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="3c95a-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="3c95a-135">Validi e non validi i rami in costruzioni Try</span><span class="sxs-lookup"><span data-stu-id="3c95a-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c95a-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c95a-136">Example</span></span>  
 <span data-ttu-id="3c95a-137">L'esempio seguente usa il `GoTo` istruzione branch etichette di riga in una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="3c95a-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3c95a-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c95a-138">See Also</span></span>  
 [<span data-ttu-id="3c95a-139">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="3c95a-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="3c95a-140">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="3c95a-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="3c95a-141">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="3c95a-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="3c95a-142">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="3c95a-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="3c95a-143">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="3c95a-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="3c95a-144">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="3c95a-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="3c95a-145">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="3c95a-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="3c95a-146">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="3c95a-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
