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
ms.openlocfilehash: fe53ea58dc98a4de793fe9dad1c3ceeac71622fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843201"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="aa205-102">Istruzione Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa205-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="aa205-103">Dichiara l'inizio di un `Using` in blocchi e, facoltativamente, acquisisce le risorse di sistema che controlla il blocco.</span><span class="sxs-lookup"><span data-stu-id="aa205-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa205-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa205-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="aa205-105">Parti</span><span class="sxs-lookup"><span data-stu-id="aa205-105">Parts</span></span>  
  
|<span data-ttu-id="aa205-106">Termine</span><span class="sxs-lookup"><span data-stu-id="aa205-106">Term</span></span>|<span data-ttu-id="aa205-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="aa205-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="aa205-108">Obbligatorio se non si fornisce `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="aa205-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="aa205-109">Elenco di uno o più risorse di sistema che questo `Using` blocco dei controlli, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="aa205-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="aa205-110">Obbligatorio se non si fornisce `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="aa205-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="aa205-111">Variabile di riferimento o un'espressione che fa riferimento a una risorsa di sistema da parte di questo `Using` blocco.</span><span class="sxs-lookup"><span data-stu-id="aa205-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="aa205-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="aa205-112">Optional.</span></span> <span data-ttu-id="aa205-113">Blocco di istruzioni che la `Using` bloccare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aa205-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="aa205-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="aa205-114">Required.</span></span> <span data-ttu-id="aa205-115">Termina la definizione del `Using` blocco ed Elimina tutte le risorse da essa controllati.</span><span class="sxs-lookup"><span data-stu-id="aa205-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="aa205-116">Ogni risorsa nel `resourcelist` parte ha la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa205-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="aa205-117">-oppure-</span><span class="sxs-lookup"><span data-stu-id="aa205-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="aa205-118">Parti resourcelist</span><span class="sxs-lookup"><span data-stu-id="aa205-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="aa205-119">Termine</span><span class="sxs-lookup"><span data-stu-id="aa205-119">Term</span></span>|<span data-ttu-id="aa205-120">Definizione</span><span class="sxs-lookup"><span data-stu-id="aa205-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="aa205-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="aa205-121">Required.</span></span> <span data-ttu-id="aa205-122">Variabile di riferimento che fa riferimento a una risorsa di sistema che la `Using` blocco dei controlli.</span><span class="sxs-lookup"><span data-stu-id="aa205-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="aa205-123">Obbligatorio se il `Using` istruzione acquisisce la risorsa.</span><span class="sxs-lookup"><span data-stu-id="aa205-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="aa205-124">Se la risorsa è già stata acquisita, usare la seconda alternativa di sintassi.</span><span class="sxs-lookup"><span data-stu-id="aa205-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="aa205-125">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="aa205-125">Required.</span></span> <span data-ttu-id="aa205-126">La classe della risorsa.</span><span class="sxs-lookup"><span data-stu-id="aa205-126">The class of the resource.</span></span> <span data-ttu-id="aa205-127">La classe deve implementare il <xref:System.IDisposable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aa205-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="aa205-128">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="aa205-128">Optional.</span></span> <span data-ttu-id="aa205-129">Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="aa205-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="aa205-130">Visualizzare [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="aa205-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="aa205-131">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="aa205-131">Required.</span></span> <span data-ttu-id="aa205-132">Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfano i requisiti di `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="aa205-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="aa205-133">Se si usa la seconda alternativa di sintassi, è necessario acquisire la risorsa prima di passare il controllo al `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="aa205-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa205-134">Note</span><span class="sxs-lookup"><span data-stu-id="aa205-134">Remarks</span></span>  
 <span data-ttu-id="aa205-135">In alcuni casi il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="aa205-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="aa205-136">Oggetto `Using` blocco garantisce l'eliminazione di uno o più di tali risorse al termine del codice con essi.</span><span class="sxs-lookup"><span data-stu-id="aa205-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="aa205-137">Ciò li rende disponibili per altro codice da usare.</span><span class="sxs-lookup"><span data-stu-id="aa205-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="aa205-138">Le risorse gestite vengono eliminate dal garbage collector (GC) di .NET Framework senza scrivere codice aggiuntivo da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="aa205-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="aa205-139">Non è necessario un `Using` blocco per le risorse gestite.</span><span class="sxs-lookup"><span data-stu-id="aa205-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="aa205-140">Tuttavia, è comunque possibile usare un `Using` blocco per forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.</span><span class="sxs-lookup"><span data-stu-id="aa205-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="aa205-141">Oggetto `Using` blocco è costituito da tre parti: acquisizione, utilizzo ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="aa205-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="aa205-142">*Acquisizione* implica la creazione di una variabile e inizializzarla per fare riferimento alla risorsa di sistema.</span><span class="sxs-lookup"><span data-stu-id="aa205-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="aa205-143">Il `Using` istruzione può acquisire una o più risorse, oppure è possibile acquisire esattamente una risorsa prima di immettere il blocco e forniscono al `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="aa205-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="aa205-144">Se si specificano `resourceexpression`, è necessario acquisire la risorsa prima di passare il controllo al `Using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="aa205-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="aa205-145">*Utilizzo* significa accedere alle risorse e l'esecuzione di operazioni su tali elementi.</span><span class="sxs-lookup"><span data-stu-id="aa205-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="aa205-146">Le istruzioni comprese tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="aa205-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="aa205-147">*Disposizione* significa che la chiamata di <xref:System.IDisposable.Dispose%2A> metodo sull'oggetto nelle `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="aa205-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="aa205-148">In questo modo l'oggetto di terminare correttamente le relative risorse.</span><span class="sxs-lookup"><span data-stu-id="aa205-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="aa205-149">Il `End Using` istruzione elimina le risorse sotto il `Using` controllo del blocco.</span><span class="sxs-lookup"><span data-stu-id="aa205-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="aa205-150">Comportamento</span><span class="sxs-lookup"><span data-stu-id="aa205-150">Behavior</span></span>  
 <span data-ttu-id="aa205-151">Oggetto `Using` blocco si comporta come un `Try`... `Finally` costruzione in cui la `Try` blocco Usa le risorse e il `Finally` blocco le Elimina.</span><span class="sxs-lookup"><span data-stu-id="aa205-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="aa205-152">Per questo motivo, il `Using` blocco garantisce l'eliminazione delle risorse, indipendentemente dal modo in cui si esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="aa205-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="aa205-153">Questo vale anche in caso di un'eccezione non gestita, ad eccezione di un <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="aa205-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="aa205-154">L'ambito di ogni variabile di risorsa acquisita dal `Using` istruzione è limitata al `Using` blocco.</span><span class="sxs-lookup"><span data-stu-id="aa205-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="aa205-155">Se si specifica più di una risorsa di sistema nel `Using` istruzione, l'effetto è lo stesso come se annidati `Using` blocca l'uno all'interno di altra.</span><span class="sxs-lookup"><span data-stu-id="aa205-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="aa205-156">Se `resourcename` viene `Nothing`, nessuna chiamata a <xref:System.IDisposable.Dispose%2A> viene effettuata, e viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="aa205-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="aa205-157">All'interno di un blocco tramite gestione strutturata delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="aa205-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="aa205-158">Se è necessario gestire un'eccezione che potrebbe verificarsi all'interno di `Using` blocco, è possibile aggiungere una completa `Try`... `Finally` costruzione a esso.</span><span class="sxs-lookup"><span data-stu-id="aa205-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="aa205-159">Se è necessario gestire il caso in cui il `Using` istruzione non ha esito positivo l'acquisizione di una risorsa, è possibile verificare se `resourcename` è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="aa205-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="aa205-160">Invece di un blocco tramite gestione strutturata delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="aa205-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="aa205-161">Se è necessario un controllo più preciso l'acquisizione delle risorse oppure è necessario codice aggiuntivo nel `Finally` blocco, è possibile riscrivere il `Using` block come un `Try`... `Finally` costruzione.</span><span class="sxs-lookup"><span data-stu-id="aa205-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="aa205-162">L'esempio seguente mostra scheletro `Try` e `Using` costruzioni equivalenti nell'acquisizione e l'eliminazione di `resource`.</span><span class="sxs-lookup"><span data-stu-id="aa205-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
>  <span data-ttu-id="aa205-163">Il codice all'interno di `Using` blocco non è necessario assegnare l'oggetto in `resourcename` a un'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="aa205-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="aa205-164">Quando si esce dal `Using` blocco, la risorsa viene eliminato e l'altra variabile non è possibile accedere alla risorsa a cui punta.</span><span class="sxs-lookup"><span data-stu-id="aa205-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa205-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa205-165">Example</span></span>  
 <span data-ttu-id="aa205-166">L'esempio seguente crea un file denominato log. txt e scrive due righe di testo nel file.</span><span class="sxs-lookup"><span data-stu-id="aa205-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="aa205-167">Nell'esempio viene inoltre legge tale file e visualizza le righe di testo.</span><span class="sxs-lookup"><span data-stu-id="aa205-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="aa205-168">Poiché il <xref:System.IO.TextWriter> e <xref:System.IO.TextReader> sono classi che implementano le <xref:System.IDisposable> interfaccia, è possibile usare il codice `Using` istruzioni per assicurarsi che il file viene chiuso dopo l'operazione di scrittura correttamente e le operazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="aa205-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="aa205-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa205-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="aa205-170">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="aa205-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="aa205-171">Procedura: Eliminare una risorsa di sistema</span><span class="sxs-lookup"><span data-stu-id="aa205-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
