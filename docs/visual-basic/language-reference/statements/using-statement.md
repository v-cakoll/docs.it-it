---
title: Istruzione Using (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="5fe31-102">Istruzione Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fe31-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="5fe31-103">Dichiara l'inizio di un `Using` blocco e facoltativamente acquisisce le risorse di sistema che controlla il blocco.</span><span class="sxs-lookup"><span data-stu-id="5fe31-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fe31-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="5fe31-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5fe31-105">Parts</span></span>  
  
|<span data-ttu-id="5fe31-106">Termine</span><span class="sxs-lookup"><span data-stu-id="5fe31-106">Term</span></span>|<span data-ttu-id="5fe31-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="5fe31-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="5fe31-108">Obbligatoria se non viene fornito `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="5fe31-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="5fe31-109">Elenco di uno o più risorse di sistema da questo `Using` blocco dei controlli, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="5fe31-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="5fe31-110">Obbligatoria se non viene fornito `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="5fe31-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="5fe31-111">Variabile di riferimento o un'espressione che fa riferimento a una risorsa di sistema per essere controllato da questo `Using` blocco.</span><span class="sxs-lookup"><span data-stu-id="5fe31-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="5fe31-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5fe31-112">Optional.</span></span> <span data-ttu-id="5fe31-113">Blocco di istruzioni che il `Using` bloccare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5fe31-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="5fe31-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5fe31-114">Required.</span></span> <span data-ttu-id="5fe31-115">Termina la definizione del `Using` blocco ed Elimina tutte le risorse da essa controllati.</span><span class="sxs-lookup"><span data-stu-id="5fe31-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="5fe31-116">Ogni risorsa di `resourcelist` parte con la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe31-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="5fe31-117">-oppure-</span><span class="sxs-lookup"><span data-stu-id="5fe31-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="5fe31-118">Parti di resourcelist</span><span class="sxs-lookup"><span data-stu-id="5fe31-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="5fe31-119">Termine</span><span class="sxs-lookup"><span data-stu-id="5fe31-119">Term</span></span>|<span data-ttu-id="5fe31-120">Definizione</span><span class="sxs-lookup"><span data-stu-id="5fe31-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="5fe31-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5fe31-121">Required.</span></span> <span data-ttu-id="5fe31-122">Variabile di riferimento che fa riferimento a una risorsa di sistema che il `Using` blocco dei controlli.</span><span class="sxs-lookup"><span data-stu-id="5fe31-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="5fe31-123">Obbligatorio se il `Using` istruzione acquisisce la risorsa.</span><span class="sxs-lookup"><span data-stu-id="5fe31-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="5fe31-124">Se la risorsa è già stata acquisita, utilizzare la seconda alternativa di sintassi.</span><span class="sxs-lookup"><span data-stu-id="5fe31-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="5fe31-125">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5fe31-125">Required.</span></span> <span data-ttu-id="5fe31-126">La classe della risorsa.</span><span class="sxs-lookup"><span data-stu-id="5fe31-126">The class of the resource.</span></span> <span data-ttu-id="5fe31-127">La classe deve implementare il <xref:System.IDisposable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5fe31-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="5fe31-128">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5fe31-128">Optional.</span></span> <span data-ttu-id="5fe31-129">Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="5fe31-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="5fe31-130">Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="5fe31-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="5fe31-131">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5fe31-131">Required.</span></span> <span data-ttu-id="5fe31-132">Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfano i requisiti di `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="5fe31-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="5fe31-133">Se si utilizza la seconda alternativa di sintassi, è necessario acquisire la risorsa prima di passare il controllo per il `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="5fe31-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fe31-134">Note</span><span class="sxs-lookup"><span data-stu-id="5fe31-134">Remarks</span></span>  
 <span data-ttu-id="5fe31-135">In alcuni casi il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="5fe31-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="5fe31-136">Oggetto `Using` blocco garantisce di tali risorse al termine del codice con essi.</span><span class="sxs-lookup"><span data-stu-id="5fe31-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="5fe31-137">Questo li rende disponibile per altro codice.</span><span class="sxs-lookup"><span data-stu-id="5fe31-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="5fe31-138">Le risorse gestite vengano eliminate dal garbage collector (GC) di .NET Framework senza alcuna codifica aggiuntiva da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5fe31-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="5fe31-139">Non è necessario un `Using` blocco per le risorse gestite.</span><span class="sxs-lookup"><span data-stu-id="5fe31-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="5fe31-140">Tuttavia, è comunque possibile usare un `Using` blocco per forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.</span><span class="sxs-lookup"><span data-stu-id="5fe31-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="5fe31-141">Oggetto `Using` blocco è costituito da tre parti: acquisizione, utilizzo ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="5fe31-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="5fe31-142">*Acquisizione* implica la creazione di una variabile e inizializzarlo per fare riferimento alla risorsa di sistema.</span><span class="sxs-lookup"><span data-stu-id="5fe31-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="5fe31-143">Il `Using` istruzione può acquisire una o più risorse, o è possibile acquisire esattamente una risorsa prima di immettere il blocco e per fornire il `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="5fe31-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="5fe31-144">Se si fornisce `resourceexpression`, è necessario acquisire la risorsa prima di passare il controllo per il `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="5fe31-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="5fe31-145">*Utilizzo* si intende l'accesso alle risorse e di eseguire operazioni su tali.</span><span class="sxs-lookup"><span data-stu-id="5fe31-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="5fe31-146">Le istruzioni comprese tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5fe31-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="5fe31-147">*Eliminazione* indica la chiamata di <xref:System.IDisposable.Dispose%2A> metodo sull'oggetto in `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="5fe31-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="5fe31-148">In questo modo l'oggetto di terminare correttamente le risorse.</span><span class="sxs-lookup"><span data-stu-id="5fe31-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="5fe31-149">Il `End Using` istruzione elimina le risorse sotto il `Using` controllo del blocco.</span><span class="sxs-lookup"><span data-stu-id="5fe31-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="5fe31-150">Comportamento</span><span class="sxs-lookup"><span data-stu-id="5fe31-150">Behavior</span></span>  
 <span data-ttu-id="5fe31-151">Oggetto `Using` blocco si comporta come un `Try`... `Finally` costruzione in cui il `Try` blocco utilizza le risorse e `Finally` blocco le Elimina.</span><span class="sxs-lookup"><span data-stu-id="5fe31-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="5fe31-152">Per questo motivo, il `Using` blocco garantisce l'eliminazione delle risorse, indipendentemente da come si esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="5fe31-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="5fe31-153">Questo vale anche nel caso di un'eccezione non gestita, ad eccezione di un <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="5fe31-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="5fe31-154">L'ambito di ogni variabile di risorsa acquisita dal `Using` istruzione è limitata al `Using` blocco.</span><span class="sxs-lookup"><span data-stu-id="5fe31-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="5fe31-155">Se si specifica più di una risorsa di sistema nel `Using` istruzione, l'effetto è lo stesso nidificando `Using` blocca l'uno all'interno di altra.</span><span class="sxs-lookup"><span data-stu-id="5fe31-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="5fe31-156">Se `resourcename` è `Nothing`, nessuna chiamata a <xref:System.IDisposable.Dispose%2A> viene eseguita e viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="5fe31-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="5fe31-157">Strutturata delle eccezioni all'interno di un blocco Using</span><span class="sxs-lookup"><span data-stu-id="5fe31-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="5fe31-158">Se è necessario gestire un'eccezione che potrebbe verificarsi all'interno di `Using` blocco, è possibile aggiungere completa `Try`... `Finally` costruzione a esso.</span><span class="sxs-lookup"><span data-stu-id="5fe31-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="5fe31-159">Se è necessario gestire il caso in cui il `Using` istruzione non è riuscita durante l'acquisizione di una risorsa, è possibile verificare se `resourcename` è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="5fe31-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="5fe31-160">Strutturata delle eccezioni anziché un blocco Using</span><span class="sxs-lookup"><span data-stu-id="5fe31-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="5fe31-161">Se è necessario un controllo più preciso l'acquisizione delle risorse, oppure è necessario codice aggiuntivo nel `Finally` blocco, è possibile riscrivere la `Using` blocco come un `Try`... `Finally` costruzione.</span><span class="sxs-lookup"><span data-stu-id="5fe31-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="5fe31-162">Nell'esempio seguente viene illustrato scheletro `Try` e `Using` costruzioni, equivalenti per l'acquisizione e l'eliminazione di `resource`.</span><span class="sxs-lookup"><span data-stu-id="5fe31-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
>  <span data-ttu-id="5fe31-163">Il codice all'interno di `Using` blocco non è necessario assegnare l'oggetto in `resourcename` a un'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="5fe31-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="5fe31-164">Quando si esce dal `Using` blocco, la risorsa viene eliminato e l'altra variabile non è possibile accedere alla risorsa a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="5fe31-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fe31-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="5fe31-165">Example</span></span>  
 <span data-ttu-id="5fe31-166">Nell'esempio seguente crea un file denominato >.log.txt e scrive nel file di due righe di testo.</span><span class="sxs-lookup"><span data-stu-id="5fe31-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="5fe31-167">Nell'esempio viene inoltre legge di tale file e visualizza le righe di testo.</span><span class="sxs-lookup"><span data-stu-id="5fe31-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="5fe31-168">Poiché il <xref:System.IO.TextWriter> e <xref:System.IO.TextReader> sono classi che implementano il <xref:System.IDisposable> interfaccia, è possibile utilizzare il codice `Using` istruzioni per assicurarsi che il file viene chiuso dopo la scrittura e operazioni di lettura correttamente.</span><span class="sxs-lookup"><span data-stu-id="5fe31-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5fe31-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fe31-169">See Also</span></span>  
 <xref:System.IDisposable>  
 [<span data-ttu-id="5fe31-170">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="5fe31-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="5fe31-171">Procedura: Eliminare una risorsa di sistema</span><span class="sxs-lookup"><span data-stu-id="5fe31-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
