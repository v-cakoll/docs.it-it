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
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581822"
---
# <a name="goto-statement"></a><span data-ttu-id="52b14-102">Istruzione GoTo</span><span class="sxs-lookup"><span data-stu-id="52b14-102">GoTo Statement</span></span>
<span data-ttu-id="52b14-103">Viene diramato in modo incondizionato a una riga specificata in una procedura.</span><span class="sxs-lookup"><span data-stu-id="52b14-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52b14-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="52b14-105">Parte</span><span class="sxs-lookup"><span data-stu-id="52b14-105">Part</span></span>  
 `line`  
 <span data-ttu-id="52b14-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="52b14-106">Required.</span></span> <span data-ttu-id="52b14-107">Qualsiasi etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="52b14-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52b14-108">Note</span><span class="sxs-lookup"><span data-stu-id="52b14-108">Remarks</span></span>  
 <span data-ttu-id="52b14-109">L'istruzione `GoTo` può creare branch solo per le righe della procedura in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="52b14-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="52b14-110">La riga deve avere un'etichetta di linea a cui `GoTo` può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="52b14-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="52b14-111">Per altre informazioni, vedere [How to: Label statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="52b14-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52b14-112">le istruzioni `GoTo` possono rendere difficile la lettura e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="52b14-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="52b14-113">Quando possibile, usare invece una struttura di controllo.</span><span class="sxs-lookup"><span data-stu-id="52b14-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="52b14-114">Per altre informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="52b14-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="52b14-115">Non è possibile usare un'istruzione `GoTo` per creare un ramo dall'esterno di un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, 0... 1 o 2... 3 costruzione in un'etichetta all'interno di.</span><span class="sxs-lookup"><span data-stu-id="52b14-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="52b14-116">Creazione di rami e tentativi di costruzione</span><span class="sxs-lookup"><span data-stu-id="52b14-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="52b14-117">All'interno di un `Try`... `Catch`... `Finally` costruzione, le regole seguenti si applicano alla diramazione con l'istruzione `GoTo`.</span><span class="sxs-lookup"><span data-stu-id="52b14-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="52b14-118">Blocco o area</span><span class="sxs-lookup"><span data-stu-id="52b14-118">Block or region</span></span>|<span data-ttu-id="52b14-119">Diramazione in dall'esterno</span><span class="sxs-lookup"><span data-stu-id="52b14-119">Branching in from outside</span></span>|<span data-ttu-id="52b14-120">Diramazione dall'interno</span><span class="sxs-lookup"><span data-stu-id="52b14-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="52b14-121">blocco `Try`</span><span class="sxs-lookup"><span data-stu-id="52b14-121">`Try` block</span></span>|<span data-ttu-id="52b14-122">Solo da un blocco `Catch` della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="52b14-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="52b14-123">Solo all'esterno dell'intera costruzione</span><span class="sxs-lookup"><span data-stu-id="52b14-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="52b14-124">blocco `Catch`</span><span class="sxs-lookup"><span data-stu-id="52b14-124">`Catch` block</span></span>|<span data-ttu-id="52b14-125">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="52b14-125">Never allowed</span></span>|<span data-ttu-id="52b14-126">Solo all'esterno dell'intera costruzione o al blocco `Try` della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="52b14-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="52b14-127">blocco `Finally`</span><span class="sxs-lookup"><span data-stu-id="52b14-127">`Finally` block</span></span>|<span data-ttu-id="52b14-128">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="52b14-128">Never allowed</span></span>|<span data-ttu-id="52b14-129">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="52b14-129">Never allowed</span></span>|  
  
 <span data-ttu-id="52b14-130"><sup>1</sup> se una `Try`... `Catch`... `Finally` costruzione è annidata all'interno di un'altra, un blocco di `Catch` può creare rami nel blocco `Try` a livello di annidamento, ma non in altri blocchi `Try`.</span><span class="sxs-lookup"><span data-stu-id="52b14-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="52b14-131">@No__t_0 annidato... `Catch`... la costruzione di `Finally` deve essere completamente inclusa in un blocco `Try` o `Catch` della costruzione all'interno della quale è annidata.</span><span class="sxs-lookup"><span data-stu-id="52b14-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="52b14-132">Nella figura seguente viene illustrato un `Try` costruzione annidata all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="52b14-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="52b14-133">Vari rami tra i blocchi delle due costruzioni sono indicati come validi o non validi.</span><span class="sxs-lookup"><span data-stu-id="52b14-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagramma grafico dei rami in costruzioni Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="52b14-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="52b14-135">Example</span></span>  
 <span data-ttu-id="52b14-136">Nell'esempio seguente viene utilizzata l'istruzione `GoTo` per creare rami di etichette di riga in una procedura.</span><span class="sxs-lookup"><span data-stu-id="52b14-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="52b14-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52b14-137">See also</span></span>

- [<span data-ttu-id="52b14-138">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="52b14-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="52b14-139">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="52b14-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="52b14-140">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="52b14-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="52b14-141">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="52b14-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="52b14-142">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="52b14-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="52b14-143">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="52b14-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="52b14-144">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="52b14-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="52b14-145">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="52b14-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
