---
title: Istruzione Using (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957538"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="6ca41-102">Istruzione Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ca41-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="6ca41-103">Dichiara l'inizio di un `Using` blocco e, facoltativamente, acquisisce le risorse di sistema controllate dal blocco.</span><span class="sxs-lookup"><span data-stu-id="6ca41-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca41-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ca41-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="6ca41-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6ca41-105">Parts</span></span>  
  
|<span data-ttu-id="6ca41-106">Termine</span><span class="sxs-lookup"><span data-stu-id="6ca41-106">Term</span></span>|<span data-ttu-id="6ca41-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6ca41-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="6ca41-108">Obbligatorio se non si specifica `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="6ca41-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="6ca41-109">Elenco di una o più risorse di sistema che `Using` questo blocco controlla, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="6ca41-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="6ca41-110">Obbligatorio se non si specifica `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="6ca41-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="6ca41-111">Variabile di riferimento o espressione che fa riferimento a una risorsa di sistema che deve essere `Using` controllata da questo blocco.</span><span class="sxs-lookup"><span data-stu-id="6ca41-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="6ca41-112">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6ca41-112">Optional.</span></span> <span data-ttu-id="6ca41-113">Blocco di istruzioni eseguite dal `Using` blocco.</span><span class="sxs-lookup"><span data-stu-id="6ca41-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="6ca41-114">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="6ca41-114">Required.</span></span> <span data-ttu-id="6ca41-115">Termina la definizione del `Using` blocco ed Elimina tutte le risorse che controlla.</span><span class="sxs-lookup"><span data-stu-id="6ca41-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="6ca41-116">Ogni risorsa `resourcelist` della parte presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ca41-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="6ca41-117">-oppure-</span><span class="sxs-lookup"><span data-stu-id="6ca41-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="6ca41-118">Parti Resources</span><span class="sxs-lookup"><span data-stu-id="6ca41-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="6ca41-119">Termine</span><span class="sxs-lookup"><span data-stu-id="6ca41-119">Term</span></span>|<span data-ttu-id="6ca41-120">Definizione</span><span class="sxs-lookup"><span data-stu-id="6ca41-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="6ca41-121">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="6ca41-121">Required.</span></span> <span data-ttu-id="6ca41-122">Variabile di riferimento che fa riferimento a una risorsa di `Using` sistema controllata dal blocco.</span><span class="sxs-lookup"><span data-stu-id="6ca41-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="6ca41-123">Obbligatorio se l' `Using` istruzione acquisisce la risorsa.</span><span class="sxs-lookup"><span data-stu-id="6ca41-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="6ca41-124">Se la risorsa è già stata acquisita, utilizzare la seconda alternativa della sintassi.</span><span class="sxs-lookup"><span data-stu-id="6ca41-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="6ca41-125">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="6ca41-125">Required.</span></span> <span data-ttu-id="6ca41-126">Classe della risorsa.</span><span class="sxs-lookup"><span data-stu-id="6ca41-126">The class of the resource.</span></span> <span data-ttu-id="6ca41-127">La classe deve implementare l' <xref:System.IDisposable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6ca41-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="6ca41-128">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6ca41-128">Optional.</span></span> <span data-ttu-id="6ca41-129">Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="6ca41-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="6ca41-130">Vedere [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="6ca41-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="6ca41-131">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="6ca41-131">Required.</span></span> <span data-ttu-id="6ca41-132">Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfa i `resourcetype`requisiti di.</span><span class="sxs-lookup"><span data-stu-id="6ca41-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="6ca41-133">Se si usa la seconda sintassi alternativa, è necessario acquisire la risorsa prima di passare il `Using` controllo all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6ca41-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ca41-134">Note</span><span class="sxs-lookup"><span data-stu-id="6ca41-134">Remarks</span></span>  
 <span data-ttu-id="6ca41-135">A volte il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="6ca41-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="6ca41-136">Un `Using` blocco garantisce l'eliminazione di una o più risorse di questo tipo al termine del codice.</span><span class="sxs-lookup"><span data-stu-id="6ca41-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="6ca41-137">In modo da renderli disponibili per l'utilizzo da altro codice.</span><span class="sxs-lookup"><span data-stu-id="6ca41-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="6ca41-138">Le risorse gestite vengono eliminate dal .NET Framework Garbage Collector (GC) senza alcuna codifica aggiuntiva da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6ca41-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="6ca41-139">Non è necessario un `Using` blocco per le risorse gestite.</span><span class="sxs-lookup"><span data-stu-id="6ca41-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="6ca41-140">Tuttavia, è comunque possibile usare un `Using` blocco per forzare l'eliminazione di una risorsa gestita anziché attendere il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="6ca41-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="6ca41-141">Un `Using` blocco è costituito da tre parti: acquisizione, utilizzo e eliminazione.</span><span class="sxs-lookup"><span data-stu-id="6ca41-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
- <span data-ttu-id="6ca41-142">L' *acquisizione* significa creare una variabile e inizializzarla per fare riferimento alla risorsa di sistema.</span><span class="sxs-lookup"><span data-stu-id="6ca41-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="6ca41-143">L' `Using` istruzione può acquisire una o più risorse oppure è possibile acquisire esattamente una risorsa prima `Using` di immettere il blocco e fornirla all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6ca41-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="6ca41-144">Se si specifica `resourceexpression`, è necessario acquisire la risorsa prima di passare il `Using` controllo all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="6ca41-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
- <span data-ttu-id="6ca41-145">L' *utilizzo* indica l'accesso alle risorse e l'esecuzione di azioni con loro.</span><span class="sxs-lookup"><span data-stu-id="6ca41-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="6ca41-146">Le istruzioni tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="6ca41-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
- <span data-ttu-id="6ca41-147">Per *eliminazione* si intende <xref:System.IDisposable.Dispose%2A> la chiamata al metodo sull' `resourcename`oggetto in.</span><span class="sxs-lookup"><span data-stu-id="6ca41-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="6ca41-148">Questo consente all'oggetto di terminare in modo corretto le risorse.</span><span class="sxs-lookup"><span data-stu-id="6ca41-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="6ca41-149">L' `End Using` istruzione Elimina le risorse sotto il `Using` controllo del blocco.</span><span class="sxs-lookup"><span data-stu-id="6ca41-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="6ca41-150">Comportamento</span><span class="sxs-lookup"><span data-stu-id="6ca41-150">Behavior</span></span>  
 <span data-ttu-id="6ca41-151">Un `Using` blocco si comporta `Try`come... costruzione in cui il `Try` blocco utilizza le risorse e il `Finally` blocco ne comporta l'eliminazione. `Finally`</span><span class="sxs-lookup"><span data-stu-id="6ca41-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="6ca41-152">Per questo motivo, il `Using` blocco garantisce l'eliminazione delle risorse, indipendentemente dal modo in cui si esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="6ca41-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="6ca41-153">Questo vale anche nel caso di un'eccezione non gestita, ad eccezione di <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="6ca41-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="6ca41-154">L'ambito di ogni variabile di risorsa acquisita `Using` dall'istruzione è limitato `Using` al blocco.</span><span class="sxs-lookup"><span data-stu-id="6ca41-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="6ca41-155">Se nell' `Using` istruzione si specifica più di una risorsa di sistema, l'effetto sarà identico a quello di un `Using` blocco annidato in un altro.</span><span class="sxs-lookup"><span data-stu-id="6ca41-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="6ca41-156">Se `resourcename` <xref:System.IDisposable.Dispose%2A> è `Nothing`, non viene effettuata alcuna chiamata a e non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ca41-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="6ca41-157">Gestione strutturata delle eccezioni in un blocco using</span><span class="sxs-lookup"><span data-stu-id="6ca41-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="6ca41-158">Se è necessario gestire un'eccezione che può verificarsi all'interno del `Using` blocco, è possibile aggiungere `Try`un... `Finally` creazione.</span><span class="sxs-lookup"><span data-stu-id="6ca41-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="6ca41-159">Se è necessario gestire il caso in cui l' `Using` istruzione non riesce ad acquisire una risorsa, è possibile verificare se `resourcename` è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6ca41-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="6ca41-160">Gestione strutturata delle eccezioni anziché un blocco using</span><span class="sxs-lookup"><span data-stu-id="6ca41-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="6ca41-161">Se è necessario un `Finally` `Try`controllo più preciso sull'acquisizione delle risorse o se è necessario codice aggiuntivo nel blocco, è possibile riscrivere il `Using` blocco come... `Finally` creazione.</span><span class="sxs-lookup"><span data-stu-id="6ca41-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="6ca41-162">Nell'esempio seguente vengono illustrati `Using` scheletri `Try` e costruzioni equivalenti nell'acquisizione e nell'eliminazione di `resource`.</span><span class="sxs-lookup"><span data-stu-id="6ca41-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
> <span data-ttu-id="6ca41-163">Il codice all'interno `Using` del blocco non deve assegnare l'oggetto `resourcename` in a un'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="6ca41-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="6ca41-164">Quando si esce dal `Using` blocco, la risorsa viene eliminata e l'altra variabile non può accedere alla risorsa a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="6ca41-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ca41-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ca41-165">Example</span></span>  
 <span data-ttu-id="6ca41-166">Nell'esempio seguente viene creato un file denominato log. txt che scrive due righe di testo nel file.</span><span class="sxs-lookup"><span data-stu-id="6ca41-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="6ca41-167">Nell'esempio viene inoltre letto lo stesso file e vengono visualizzate le righe di testo.</span><span class="sxs-lookup"><span data-stu-id="6ca41-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="6ca41-168">Poiché le classi <xref:System.IO.TextReader>eimplementano l' <xref:System.IDisposable> interfaccia, il codice può `Using` utilizzare le istruzioni per garantire che il file venga chiuso correttamente dopo le operazioni di scrittura e lettura. <xref:System.IO.TextWriter></span><span class="sxs-lookup"><span data-stu-id="6ca41-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="6ca41-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ca41-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="6ca41-170">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="6ca41-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="6ca41-171">Procedura: Eliminare una risorsa di sistema</span><span class="sxs-lookup"><span data-stu-id="6ca41-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
