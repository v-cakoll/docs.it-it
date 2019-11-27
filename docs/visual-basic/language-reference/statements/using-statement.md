---
title: Istruzione Using
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352764"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="70c48-102">Istruzione Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70c48-102">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="70c48-103">Dichiara l'inizio di un blocco di `Using` e, facoltativamente, acquisisce le risorse di sistema controllate dal blocco.</span><span class="sxs-lookup"><span data-stu-id="70c48-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="70c48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70c48-104">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="70c48-105">Parti</span><span class="sxs-lookup"><span data-stu-id="70c48-105">Parts</span></span>

|<span data-ttu-id="70c48-106">Termine</span><span class="sxs-lookup"><span data-stu-id="70c48-106">Term</span></span>|<span data-ttu-id="70c48-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="70c48-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="70c48-108">Obbligatorio se non si specifica `resourceexpression`.</span><span class="sxs-lookup"><span data-stu-id="70c48-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="70c48-109">Elenco di una o più risorse di sistema che questa `Using` blocca i controlli, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="70c48-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="70c48-110">Obbligatorio se non si specifica `resourcelist`.</span><span class="sxs-lookup"><span data-stu-id="70c48-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="70c48-111">Una variabile di riferimento o un'espressione che fa riferimento a una risorsa di sistema che deve essere controllata da questo blocco `Using`.</span><span class="sxs-lookup"><span data-stu-id="70c48-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="70c48-112">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="70c48-112">Optional.</span></span> <span data-ttu-id="70c48-113">Blocco di istruzioni eseguite dal blocco `Using`.</span><span class="sxs-lookup"><span data-stu-id="70c48-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="70c48-114">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="70c48-114">Required.</span></span> <span data-ttu-id="70c48-115">Termina la definizione del blocco `Using` ed Elimina tutte le risorse che controlla.</span><span class="sxs-lookup"><span data-stu-id="70c48-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="70c48-116">Ogni risorsa della parte `resourcelist` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="70c48-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="70c48-117">-oppure-</span><span class="sxs-lookup"><span data-stu-id="70c48-117">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="70c48-118">Parti Resources</span><span class="sxs-lookup"><span data-stu-id="70c48-118">resourcelist Parts</span></span>

|<span data-ttu-id="70c48-119">Termine</span><span class="sxs-lookup"><span data-stu-id="70c48-119">Term</span></span>|<span data-ttu-id="70c48-120">Definizione</span><span class="sxs-lookup"><span data-stu-id="70c48-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="70c48-121">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="70c48-121">Required.</span></span> <span data-ttu-id="70c48-122">Variabile di riferimento che fa riferimento a una risorsa di sistema che la `Using` blocca i controlli.</span><span class="sxs-lookup"><span data-stu-id="70c48-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="70c48-123">Obbligatorio se l'istruzione `Using` acquisisce la risorsa.</span><span class="sxs-lookup"><span data-stu-id="70c48-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="70c48-124">Se la risorsa è già stata acquisita, utilizzare la seconda alternativa della sintassi.</span><span class="sxs-lookup"><span data-stu-id="70c48-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="70c48-125">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="70c48-125">Required.</span></span> <span data-ttu-id="70c48-126">Classe della risorsa.</span><span class="sxs-lookup"><span data-stu-id="70c48-126">The class of the resource.</span></span> <span data-ttu-id="70c48-127">La classe deve implementare l'interfaccia <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="70c48-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="70c48-128">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="70c48-128">Optional.</span></span> <span data-ttu-id="70c48-129">Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="70c48-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="70c48-130">Vedere [elenco di parametri](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="70c48-130">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="70c48-131">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="70c48-131">Required.</span></span> <span data-ttu-id="70c48-132">Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfa i requisiti di `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="70c48-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="70c48-133">Se si usa la seconda sintassi alternativa, è necessario acquisire la risorsa prima di passare il controllo all'istruzione `Using`.</span><span class="sxs-lookup"><span data-stu-id="70c48-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70c48-134">Note</span><span class="sxs-lookup"><span data-stu-id="70c48-134">Remarks</span></span>

 <span data-ttu-id="70c48-135">A volte il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="70c48-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="70c48-136">Un blocco `Using` garantisce l'eliminazione di una o più risorse di questo tipo al termine del codice.</span><span class="sxs-lookup"><span data-stu-id="70c48-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="70c48-137">In modo da renderli disponibili per l'utilizzo da altro codice.</span><span class="sxs-lookup"><span data-stu-id="70c48-137">This makes them available for other code to use.</span></span>

 <span data-ttu-id="70c48-138">Le risorse gestite vengono eliminate dal .NET Framework Garbage Collector (GC) senza alcuna codifica aggiuntiva da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="70c48-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="70c48-139">Non è necessario un blocco `Using` per le risorse gestite.</span><span class="sxs-lookup"><span data-stu-id="70c48-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="70c48-140">Tuttavia, è comunque possibile usare un blocco `Using` per forzare l'eliminazione di una risorsa gestita anziché attendere il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="70c48-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="70c48-141">Un blocco `Using` è costituito da tre parti: acquisizione, utilizzo e eliminazione.</span><span class="sxs-lookup"><span data-stu-id="70c48-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="70c48-142">L' *acquisizione* significa creare una variabile e inizializzarla per fare riferimento alla risorsa di sistema.</span><span class="sxs-lookup"><span data-stu-id="70c48-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="70c48-143">L'istruzione `Using` può acquisire una o più risorse oppure è possibile acquisire esattamente una risorsa prima di immettere il blocco e fornirla all'istruzione `Using`.</span><span class="sxs-lookup"><span data-stu-id="70c48-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="70c48-144">Se si fornisce `resourceexpression`, è necessario acquisire la risorsa prima di passare il controllo all'istruzione `Using`.</span><span class="sxs-lookup"><span data-stu-id="70c48-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="70c48-145">L' *utilizzo* indica l'accesso alle risorse e l'esecuzione di azioni con loro.</span><span class="sxs-lookup"><span data-stu-id="70c48-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="70c48-146">Le istruzioni tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="70c48-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="70c48-147">Per *eliminazione* si intende la chiamata al metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto `resourcename`.</span><span class="sxs-lookup"><span data-stu-id="70c48-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="70c48-148">Questo consente all'oggetto di terminare in modo corretto le risorse.</span><span class="sxs-lookup"><span data-stu-id="70c48-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="70c48-149">L'istruzione `End Using` Elimina le risorse sotto il controllo del blocco di `Using`.</span><span class="sxs-lookup"><span data-stu-id="70c48-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="70c48-150">Comportamento</span><span class="sxs-lookup"><span data-stu-id="70c48-150">Behavior</span></span>

 <span data-ttu-id="70c48-151">Un blocco di `Using` si comporta come una costruzione di `Try`...`Finally` in cui il blocco `Try` usa le risorse e il `Finally` blocco ne comporta l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="70c48-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="70c48-152">Per questo motivo, il blocco `Using` garantisce l'eliminazione delle risorse, indipendentemente dal modo in cui si esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="70c48-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="70c48-153">Questo vale anche nel caso di un'eccezione non gestita, ad eccezione di un <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="70c48-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="70c48-154">L'ambito di ogni variabile di risorsa acquisita dall'istruzione `Using` è limitato al blocco di `Using`.</span><span class="sxs-lookup"><span data-stu-id="70c48-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="70c48-155">Se si specifica più di una risorsa di sistema nell'istruzione `Using`, l'effetto è identico a quello che si annida `Using` blocca un oggetto all'interno di un altro.</span><span class="sxs-lookup"><span data-stu-id="70c48-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="70c48-156">Se `resourcename` è `Nothing`, non viene effettuata alcuna chiamata a <xref:System.IDisposable.Dispose%2A> e non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="70c48-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="70c48-157">Gestione strutturata delle eccezioni in un blocco using</span><span class="sxs-lookup"><span data-stu-id="70c48-157">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="70c48-158">Se è necessario gestire un'eccezione che può verificarsi all'interno del blocco di `Using`, è possibile aggiungere una costruzione completa `Try`...`Finally`.</span><span class="sxs-lookup"><span data-stu-id="70c48-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="70c48-159">Se è necessario gestire il caso in cui l'istruzione `Using` non riesce ad acquisire una risorsa, è possibile verificare se `resourcename` è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="70c48-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="70c48-160">Gestione strutturata delle eccezioni anziché un blocco using</span><span class="sxs-lookup"><span data-stu-id="70c48-160">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="70c48-161">Se è necessario un controllo più accurato sull'acquisizione delle risorse o se è necessario codice aggiuntivo nel blocco `Finally`, è possibile riscrivere il blocco `Using` come una costruzione `Try`...`Finally`.</span><span class="sxs-lookup"><span data-stu-id="70c48-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="70c48-162">Nell'esempio seguente vengono illustrate `Try` di ossatura e costruzioni `Using` equivalenti nell'acquisizione e nell'eliminazione di `resource`.</span><span class="sxs-lookup"><span data-stu-id="70c48-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

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
> <span data-ttu-id="70c48-163">Il codice all'interno del blocco `Using` non deve assegnare l'oggetto `resourcename` a un'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="70c48-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="70c48-164">Quando si esce dal blocco `Using`, la risorsa viene eliminata e l'altra variabile non può accedere alla risorsa a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="70c48-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="70c48-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="70c48-165">Example</span></span>

 <span data-ttu-id="70c48-166">Nell'esempio seguente viene creato un file denominato log. txt che scrive due righe di testo nel file.</span><span class="sxs-lookup"><span data-stu-id="70c48-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="70c48-167">Nell'esempio viene inoltre letto lo stesso file e vengono visualizzate le righe di testo:</span><span class="sxs-lookup"><span data-stu-id="70c48-167">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="70c48-168">Poiché le classi <xref:System.IO.TextWriter> e <xref:System.IO.TextReader> implementano l'interfaccia <xref:System.IDisposable>, il codice può utilizzare `Using` istruzioni per garantire che il file venga chiuso correttamente dopo le operazioni di scrittura e lettura.</span><span class="sxs-lookup"><span data-stu-id="70c48-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="70c48-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70c48-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="70c48-170">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="70c48-170">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="70c48-171">Procedura: Eliminare una risorsa di sistema</span><span class="sxs-lookup"><span data-stu-id="70c48-171">How to: Dispose of a System Resource</span></span>](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
