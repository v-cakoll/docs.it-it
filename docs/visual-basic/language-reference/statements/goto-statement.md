---
title: Istruzione GoTo (Visual Basic)
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
ms.openlocfilehash: c4dd249620ba1bf445642ce4600498f6beb30461
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637968"
---
# <a name="goto-statement"></a><span data-ttu-id="0fda9-102">Istruzione GoTo</span><span class="sxs-lookup"><span data-stu-id="0fda9-102">GoTo Statement</span></span>
<span data-ttu-id="0fda9-103">Rami in modo incondizionato a una determinata riga in una procedura.</span><span class="sxs-lookup"><span data-stu-id="0fda9-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fda9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fda9-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="0fda9-105">Parte</span><span class="sxs-lookup"><span data-stu-id="0fda9-105">Part</span></span>  
 `line`  
 <span data-ttu-id="0fda9-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0fda9-106">Required.</span></span> <span data-ttu-id="0fda9-107">Qualsiasi etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="0fda9-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fda9-108">Note</span><span class="sxs-lookup"><span data-stu-id="0fda9-108">Remarks</span></span>  
 <span data-ttu-id="0fda9-109">Il `GoTo` istruzione può creare rami solo righe della routine in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="0fda9-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="0fda9-110">La riga deve avere una riga di etichetta che `GoTo` farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="0fda9-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="0fda9-111">Per altre informazioni, vedere [Procedura: Etichettare le istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="0fda9-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fda9-112">`GoTo` le istruzioni possono ostacolare la lettura e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="0fda9-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="0fda9-113">Se possibile, usare invece una struttura di controllo.</span><span class="sxs-lookup"><span data-stu-id="0fda9-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="0fda9-114">Per altre informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="0fda9-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="0fda9-115">Non è possibile usare una `GoTo` branch dall'esterno dell'istruzione un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` costruzione a un'etichetta all'interno.</span><span class="sxs-lookup"><span data-stu-id="0fda9-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="0fda9-116">Creazione di rami e costruzioni Try</span><span class="sxs-lookup"><span data-stu-id="0fda9-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="0fda9-117">All'interno di un `Try`... `Catch`... `Finally` costruzione, le regole seguenti si applicano alla creazione di rami con le `GoTo` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0fda9-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="0fda9-118">Blocco o area geografica</span><span class="sxs-lookup"><span data-stu-id="0fda9-118">Block or region</span></span>|<span data-ttu-id="0fda9-119">Diramazione dall'esterno</span><span class="sxs-lookup"><span data-stu-id="0fda9-119">Branching in from outside</span></span>|<span data-ttu-id="0fda9-120">Diramazione all'esterno</span><span class="sxs-lookup"><span data-stu-id="0fda9-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="0fda9-121">`Try` Blocco</span><span class="sxs-lookup"><span data-stu-id="0fda9-121">`Try` block</span></span>|<span data-ttu-id="0fda9-122">Solo da un `Catch` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0fda9-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="0fda9-123">Solo di fuori dell'intera costruzione</span><span class="sxs-lookup"><span data-stu-id="0fda9-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="0fda9-124">`Catch` Blocco</span><span class="sxs-lookup"><span data-stu-id="0fda9-124">`Catch` block</span></span>|<span data-ttu-id="0fda9-125">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="0fda9-125">Never allowed</span></span>|<span data-ttu-id="0fda9-126">Solo all'esterno della costruzione intera o al `Try` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0fda9-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="0fda9-127">`Finally` Blocco</span><span class="sxs-lookup"><span data-stu-id="0fda9-127">`Finally` block</span></span>|<span data-ttu-id="0fda9-128">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="0fda9-128">Never allowed</span></span>|<span data-ttu-id="0fda9-129">Non è consentito</span><span class="sxs-lookup"><span data-stu-id="0fda9-129">Never allowed</span></span>|  
  
 <span data-ttu-id="0fda9-130"><sup>1</sup> eventuale `Try`... `Catch`... `Finally` costruzione viene nidificata all'interno di un altro, un `Catch` blocco può creare rami nel `Try` blocca il proprio livello di annidamento, ma non in qualsiasi altro `Try` blocco.</span><span class="sxs-lookup"><span data-stu-id="0fda9-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="0fda9-131">Nidificato `Try`... `Catch`... `Finally` costruzione deve essere completamente contenuta in un `Try` o `Catch` blocco di costruzione all'interno del quale area è nidificata.</span><span class="sxs-lookup"><span data-stu-id="0fda9-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="0fda9-132">Nell'illustrazione seguente uno `Try` costruzione annidato in un altro.</span><span class="sxs-lookup"><span data-stu-id="0fda9-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="0fda9-133">Vari rami tra blocchi di due costruzioni sono indicati come validi o non valido.</span><span class="sxs-lookup"><span data-stu-id="0fda9-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagramma grafico dei rami in costruzioni Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="0fda9-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="0fda9-135">Example</span></span>  
 <span data-ttu-id="0fda9-136">L'esempio seguente usa il `GoTo` istruzione al ramo in etichette di riga in una procedura.</span><span class="sxs-lookup"><span data-stu-id="0fda9-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="0fda9-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fda9-137">See also</span></span>

- [<span data-ttu-id="0fda9-138">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="0fda9-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="0fda9-139">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="0fda9-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="0fda9-140">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="0fda9-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="0fda9-141">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="0fda9-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="0fda9-142">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="0fda9-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="0fda9-143">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="0fda9-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="0fda9-144">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="0fda9-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="0fda9-145">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="0fda9-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
