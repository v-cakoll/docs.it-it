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
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351079"
---
# <a name="goto-statement"></a><span data-ttu-id="389bb-102">Istruzione GoTo</span><span class="sxs-lookup"><span data-stu-id="389bb-102">GoTo Statement</span></span>
<span data-ttu-id="389bb-103">Viene diramato in modo incondizionato a una riga specificata in una procedura.</span><span class="sxs-lookup"><span data-stu-id="389bb-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="389bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="389bb-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="389bb-105">Parte</span><span class="sxs-lookup"><span data-stu-id="389bb-105">Part</span></span>  
 `line`  
 <span data-ttu-id="389bb-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="389bb-106">Required.</span></span> <span data-ttu-id="389bb-107">Qualsiasi etichetta di riga.</span><span class="sxs-lookup"><span data-stu-id="389bb-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="389bb-108">Note</span><span class="sxs-lookup"><span data-stu-id="389bb-108">Remarks</span></span>  
 <span data-ttu-id="389bb-109">L'istruzione `GoTo` può creare branch solo per le righe della procedura in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="389bb-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="389bb-110">La riga deve avere un'etichetta di linea a cui `GoTo` può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="389bb-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="389bb-111">Per altre informazioni, vedere [How to: Label statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="389bb-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="389bb-112">le istruzioni `GoTo` possono rendere difficile la lettura e la gestione del codice.</span><span class="sxs-lookup"><span data-stu-id="389bb-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="389bb-113">Quando possibile, usare invece una struttura di controllo.</span><span class="sxs-lookup"><span data-stu-id="389bb-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="389bb-114">Per altre informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="389bb-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="389bb-115">Non è possibile usare un'istruzione `GoTo` per creare un ramo dall'esterno di un `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`o `Using`...`End Using` costruzione in un'etichetta all'interno di.</span><span class="sxs-lookup"><span data-stu-id="389bb-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="389bb-116">Creazione di rami e tentativi di costruzione</span><span class="sxs-lookup"><span data-stu-id="389bb-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="389bb-117">All'interno di una `Try`...`Catch`...`Finally` costruzione, le regole seguenti si applicano alla diramazione con l'istruzione `GoTo`.</span><span class="sxs-lookup"><span data-stu-id="389bb-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="389bb-118">Blocco o area</span><span class="sxs-lookup"><span data-stu-id="389bb-118">Block or region</span></span>|<span data-ttu-id="389bb-119">Diramazione in dall'esterno</span><span class="sxs-lookup"><span data-stu-id="389bb-119">Branching in from outside</span></span>|<span data-ttu-id="389bb-120">Diramazione dall'interno</span><span class="sxs-lookup"><span data-stu-id="389bb-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="389bb-121">blocco `Try`</span><span class="sxs-lookup"><span data-stu-id="389bb-121">`Try` block</span></span>|<span data-ttu-id="389bb-122">Solo da un blocco `Catch` della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="389bb-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="389bb-123">Solo all'esterno dell'intera costruzione</span><span class="sxs-lookup"><span data-stu-id="389bb-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="389bb-124">blocco `Catch`</span><span class="sxs-lookup"><span data-stu-id="389bb-124">`Catch` block</span></span>|<span data-ttu-id="389bb-125">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="389bb-125">Never allowed</span></span>|<span data-ttu-id="389bb-126">Solo all'esterno dell'intera costruzione o al blocco `Try` della stessa costruzione <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="389bb-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="389bb-127">blocco `Finally`</span><span class="sxs-lookup"><span data-stu-id="389bb-127">`Finally` block</span></span>|<span data-ttu-id="389bb-128">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="389bb-128">Never allowed</span></span>|<span data-ttu-id="389bb-129">Mai consentito</span><span class="sxs-lookup"><span data-stu-id="389bb-129">Never allowed</span></span>|  
  
 <span data-ttu-id="389bb-130"><sup>1</sup> se una `Try`...`Catch`...`Finally` costruzione è annidata all'interno di un'altra, un blocco `Catch` può creare un ramo nel blocco `Try` al proprio livello di annidamento, ma non in un altro blocco di `Try`.</span><span class="sxs-lookup"><span data-stu-id="389bb-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="389bb-131">Una costruzione annidata `Try`...`Catch`...`Finally` deve essere completamente inclusa in un blocco `Try` o `Catch` della costruzione all'interno della quale è annidato.</span><span class="sxs-lookup"><span data-stu-id="389bb-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="389bb-132">Nella figura seguente viene illustrato un `Try` costruzione annidata all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="389bb-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="389bb-133">Vari rami tra i blocchi delle due costruzioni sono indicati come validi o non validi.</span><span class="sxs-lookup"><span data-stu-id="389bb-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagramma grafico dei rami in costruzioni Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="389bb-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="389bb-135">Example</span></span>  
 <span data-ttu-id="389bb-136">Nell'esempio seguente viene utilizzata l'istruzione `GoTo` per creare rami di etichette di riga in una procedura.</span><span class="sxs-lookup"><span data-stu-id="389bb-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="389bb-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="389bb-137">See also</span></span>

- [<span data-ttu-id="389bb-138">Istruzione Do...Loop</span><span class="sxs-lookup"><span data-stu-id="389bb-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="389bb-139">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="389bb-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="389bb-140">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="389bb-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="389bb-141">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="389bb-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="389bb-142">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="389bb-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="389bb-143">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="389bb-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="389bb-144">Istruzione While...End While</span><span class="sxs-lookup"><span data-stu-id="389bb-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="389bb-145">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="389bb-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
