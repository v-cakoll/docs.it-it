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
ms.openlocfilehash: eb6f48d04b7d14591003e340464451da7df45cd6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404615"
---
# <a name="goto-statement"></a><span data-ttu-id="92d8a-102">Istruzione GoTo</span><span class="sxs-lookup"><span data-stu-id="92d8a-102">GoTo Statement</span></span>
<span data-ttu-id="92d8a-103">Viene diramato in modo incondizionato a una riga specificata in una procedura.</span><span class="sxs-lookup"><span data-stu-id="92d8a-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92d8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92d8a-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="92d8a-105">Parte</span><span class="sxs-lookup"><span data-stu-id="92d8a-105">Part</span></span>  
 `line`  
 <span data-ttu-id="92d8a-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="92d8a-106">Required.</span></span> <span data-ttu-id="92d8a-107">Qualsiasi etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="92d8a-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92d8a-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="92d8a-108">Remarks</span></span>  
 <span data-ttu-id="92d8a-109">L' `GoTo` istruzione può creare un ramo solo per le righe della routine in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="92d8a-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="92d8a-110">La riga deve avere un'etichetta di linea `GoTo` a cui può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="92d8a-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="92d8a-111">Per altre informazioni, vedere [How to: Label statements](../../programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="92d8a-111">For more information, see [How to: Label Statements](../../programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92d8a-112">`GoTo`le istruzioni possono rendere difficile la lettura e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="92d8a-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="92d8a-113">Quando possibile, usare invece una struttura di controllo.</span><span class="sxs-lookup"><span data-stu-id="92d8a-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="92d8a-114">Per altre informazioni, vedere [Flusso di controllo](../../programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="92d8a-114">For more information, see [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="92d8a-115">Non è possibile usare un' `GoTo` istruzione per creare un ramo dall'esterno di `For` ... `Next` , `For Each` ... `Next` ,. `SyncLock` .. `End SyncLock` , `Try` .. `Catch` . ... `Finally` , `With` ... `End With` o `Using` ... `End Using` costruzione in un'etichetta all'interno di.</span><span class="sxs-lookup"><span data-stu-id="92d8a-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="92d8a-116">Creazione di rami e tentativi di costruzione</span><span class="sxs-lookup"><span data-stu-id="92d8a-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="92d8a-117">All'interno di `Try` .. `Catch` . ...`Finally` costruzione, le regole seguenti si applicano alla diramazione con l' `GoTo` istruzione.</span><span class="sxs-lookup"><span data-stu-id="92d8a-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="92d8a-118">Blocco o area</span><span class="sxs-lookup"><span data-stu-id="92d8a-118">Block or region</span></span>|<span data-ttu-id="92d8a-119">Diramazione in dall'esterno</span><span class="sxs-lookup"><span data-stu-id="92d8a-119">Branching in from outside</span></span>|<span data-ttu-id="92d8a-120">Diramazione dall'interno</span><span class="sxs-lookup"><span data-stu-id="92d8a-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="92d8a-121">`Try`blocco</span><span class="sxs-lookup"><span data-stu-id="92d8a-121">`Try` block</span></span>|<span data-ttu-id="92d8a-122">Solo da un `Catch` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92d8a-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="92d8a-123">Solo all'esterno dell'intera costruzione</span><span class="sxs-lookup"><span data-stu-id="92d8a-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="92d8a-124">`Catch`blocco</span><span class="sxs-lookup"><span data-stu-id="92d8a-124">`Catch` block</span></span>|<span data-ttu-id="92d8a-125">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="92d8a-125">Never allowed</span></span>|<span data-ttu-id="92d8a-126">Solo all'esterno dell'intera costruzione o al `Try` blocco della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92d8a-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="92d8a-127">`Finally`blocco</span><span class="sxs-lookup"><span data-stu-id="92d8a-127">`Finally` block</span></span>|<span data-ttu-id="92d8a-128">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="92d8a-128">Never allowed</span></span>|<span data-ttu-id="92d8a-129">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="92d8a-129">Never allowed</span></span>|  
  
 <span data-ttu-id="92d8a-130"><sup>1</sup> se uno `Try` ... `Catch` ...`Finally` la costruzione è annidata all'interno di un'altra, un `Catch` blocco può creare rami nel `Try` blocco al proprio livello di annidamento, ma non in un altro `Try` blocco.</span><span class="sxs-lookup"><span data-stu-id="92d8a-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="92d8a-131">Oggetto annidato `Try` ... `Catch` ...`Finally` la costruzione deve essere completamente inclusa in `Try` un `Catch` blocco o della costruzione all'interno della quale è annidata.</span><span class="sxs-lookup"><span data-stu-id="92d8a-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="92d8a-132">Nella figura seguente viene illustrata una `Try` costruzione annidata all'interno di un'altra.</span><span class="sxs-lookup"><span data-stu-id="92d8a-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="92d8a-133">Vari rami tra i blocchi delle due costruzioni sono indicati come validi o non validi.</span><span class="sxs-lookup"><span data-stu-id="92d8a-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagramma grafico dei rami in costruzioni Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="92d8a-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="92d8a-135">Example</span></span>  
 <span data-ttu-id="92d8a-136">Nell'esempio seguente viene utilizzata l' `GoTo` istruzione per creare un ramo delle etichette di riga in una procedura.</span><span class="sxs-lookup"><span data-stu-id="92d8a-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="92d8a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92d8a-137">See also</span></span>

- [<span data-ttu-id="92d8a-138">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="92d8a-138">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="92d8a-139">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="92d8a-139">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="92d8a-140">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="92d8a-140">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="92d8a-141">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="92d8a-141">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="92d8a-142">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="92d8a-142">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="92d8a-143">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="92d8a-143">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="92d8a-144">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="92d8a-144">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="92d8a-145">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="92d8a-145">With...End With Statement</span></span>](with-end-with-statement.md)
