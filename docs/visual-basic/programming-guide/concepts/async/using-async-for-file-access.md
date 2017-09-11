---
title: "Utilizzo della funzionalità Async per l&quot;accesso ai File (Visual Basic) | Documenti di Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 85f5fe17a012402c406eed972debd1f5889dd393
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="using-async-for-file-access-visual-basic"></a><span data-ttu-id="1aede-102">Uso della funzionalità Async per l'accesso ai file (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1aede-102">Using Async for File Access (Visual Basic)</span></span>
<span data-ttu-id="1aede-103">È possibile utilizzare la funzionalità Async per accedere ai file.</span><span class="sxs-lookup"><span data-stu-id="1aede-103">You can use the Async feature to access files.</span></span> <span data-ttu-id="1aede-104">Tramite la funzionalità Async, è possibile chiamare i metodi asincroni senza utilizzare callback o suddividere il codice in più metodi o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="1aede-104">By using the Async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="1aede-105">Per rendere il codice sincrono asincrono, sufficiente chiamare un metodo asincrono anziché un metodo sincrono e aggiungere alcune parole chiave per il codice.</span><span class="sxs-lookup"><span data-stu-id="1aede-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="1aede-106">È opportuno considerare i seguenti motivi per l'aggiunta di asincronia per chiamate di accesso ai file:</span><span class="sxs-lookup"><span data-stu-id="1aede-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
-   <span data-ttu-id="1aede-107">Modalità asincrona rende più reattive applicazioni dell'interfaccia utente perché il thread dell'interfaccia utente che avvia l'operazione può eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="1aede-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="1aede-108">Se il thread dell'interfaccia utente deve essere eseguito codice che richiede molto tempo (ad esempio, più di 50 millisecondi), l'interfaccia utente potrebbe bloccare fino a quando il / o è stata completata e il thread dell'interfaccia utente può elaborare tastiera nuovamente e inpui e di altri eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="1aede-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
-   <span data-ttu-id="1aede-109">Modalità asincrona migliora la scalabilità di ASP.NET e altre applicazioni basate su server, riducendo la necessità di thread.</span><span class="sxs-lookup"><span data-stu-id="1aede-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="1aede-110">Se l'applicazione utilizza un thread dedicato per ogni risposta e mille richieste vengono gestite contemporaneamente, sono necessari i thread delle migliaia.</span><span class="sxs-lookup"><span data-stu-id="1aede-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="1aede-111">Operazioni asincrone non spesso necessitano usare un thread durante l'attesa.</span><span class="sxs-lookup"><span data-stu-id="1aede-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="1aede-112">Essi usare brevemente il thread di completamento i/o esistente alla fine.</span><span class="sxs-lookup"><span data-stu-id="1aede-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
-   <span data-ttu-id="1aede-113">La latenza di un'operazione di accesso ai file potrebbe essere molto bassa in condizioni correnti, ma la latenza può aumentare notevolmente in futuro.</span><span class="sxs-lookup"><span data-stu-id="1aede-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="1aede-114">Ad esempio, è possibile spostare un file a un server in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="1aede-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
-   <span data-ttu-id="1aede-115">L'ulteriore overhead di utilizzo della funzionalità Async è ridotto.</span><span class="sxs-lookup"><span data-stu-id="1aede-115">The added overhead of using the Async feature is small.</span></span>  
  
-   <span data-ttu-id="1aede-116">Attività asincrone può facilmente essere eseguita in parallelo.</span><span class="sxs-lookup"><span data-stu-id="1aede-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="1aede-117">Esecuzione degli esempi</span><span class="sxs-lookup"><span data-stu-id="1aede-117">Running the Examples</span></span>  
 <span data-ttu-id="1aede-118">Per eseguire gli esempi in questo argomento, è possibile creare un **applicazione WPF** o **applicazione Windows Form** e quindi aggiungere un **pulsante**.</span><span class="sxs-lookup"><span data-stu-id="1aede-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="1aede-119">Il pulsante `Click` evento, aggiungere una chiamata al primo metodo in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="1aede-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="1aede-120">Negli esempi seguenti, incluse le seguenti `Imports` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="1aede-120">In the following examples, include the following `Imports` statements.</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="1aede-121">Utilizzare la classe FileStream</span><span class="sxs-lookup"><span data-stu-id="1aede-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="1aede-122">Negli esempi inclusi in questo argomento viene utilizzato il <xref:System.IO.FileStream>classe, che dispone di un'opzione che causa i/o asincrone a livello di sistema operativo.</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="1aede-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="1aede-123">Utilizzando questa opzione, è possibile evitare di bloccare un thread ThreadPool in molti casi.</span><span class="sxs-lookup"><span data-stu-id="1aede-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="1aede-124">Per abilitare questa opzione, specificare il `useAsync=true` o `options=FileOptions.Asynchronous` argomento nella chiamata al costruttore.</span><span class="sxs-lookup"><span data-stu-id="1aede-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="1aede-125">È possibile utilizzare questa opzione con <xref:System.IO.StreamReader>e <xref:System.IO.StreamWriter>Se vengono aperti direttamente specificando un percorso del file.</xref:System.IO.StreamWriter> </xref:System.IO.StreamReader></span><span class="sxs-lookup"><span data-stu-id="1aede-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="1aede-126">Tuttavia, è possibile utilizzare questa opzione se si fornisce loro un <xref:System.IO.Stream>che la <xref:System.IO.FileStream>classe aperto.</xref:System.IO.FileStream> </xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="1aede-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="1aede-127">Si noti che le chiamate asincrone sono più veloci in App dell'interfaccia utente anche se un thread di pool di thread è bloccato, poiché il thread dell'interfaccia utente non è bloccato durante l'attesa.</span><span class="sxs-lookup"><span data-stu-id="1aede-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="1aede-128">Scrittura di testo</span><span class="sxs-lookup"><span data-stu-id="1aede-128">Writing Text</span></span>  
 <span data-ttu-id="1aede-129">Nell'esempio seguente scrive il testo in un file.</span><span class="sxs-lookup"><span data-stu-id="1aede-129">The following example writes text to a file.</span></span> <span data-ttu-id="1aede-130">In ogni istruzione await, il metodo termina immediatamente.</span><span class="sxs-lookup"><span data-stu-id="1aede-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="1aede-131">Una volta completato il / o di file, il metodo riprende in corrispondenza dell'istruzione che segue l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="1aede-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="1aede-132">Si noti che il modificatore async nella definizione di metodi che utilizzano l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="1aede-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
```vb  
Public Async Sub ProcessWrite()  
    Dim filePath = "temp2.txt"  
    Dim text = "Hello World" & ControlChars.CrLf  
  
    Await WriteTextAsync(filePath, text)  
End Sub  
  
Private Async Function WriteTextAsync(filePath As String, text As String) As Task  
    Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize:=4096, useAsync:=True)  
  
        Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
    End Using  
End Function  
```  
  
 <span data-ttu-id="1aede-133">L'esempio originale include l'istruzione `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, che è una contrazione delle due istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1aede-133">The original example has the statement `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, which is a contraction of the following two statements:</span></span>  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 <span data-ttu-id="1aede-134">La prima istruzione restituisce un'attività e determina l'elaborazione di file avviare.</span><span class="sxs-lookup"><span data-stu-id="1aede-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="1aede-135">La seconda istruzione con await induce il metodo chiudere immediatamente e restituire un'attività diversa.</span><span class="sxs-lookup"><span data-stu-id="1aede-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="1aede-136">Al termine dell'elaborazione in un secondo momento il file, esecuzione torna all'istruzione successiva ad await.</span><span class="sxs-lookup"><span data-stu-id="1aede-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="1aede-137">Per ulteriori informazioni, vedere [flusso di controllo in programmi asincroni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="1aede-137">For more information, see  [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="1aede-138">Lettura di testo</span><span class="sxs-lookup"><span data-stu-id="1aede-138">Reading Text</span></span>  
 <span data-ttu-id="1aede-139">Nell'esempio seguente legge il testo da un file.</span><span class="sxs-lookup"><span data-stu-id="1aede-139">The following example reads text from a file.</span></span> <span data-ttu-id="1aede-140">Il testo viene memorizzato nel buffer e, in questo caso, inserito in un <xref:System.Text.StringBuilder>.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="1aede-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="1aede-141">A differenza nell'esempio precedente, la valutazione dell'attesa produce un valore.</span><span class="sxs-lookup"><span data-stu-id="1aede-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="1aede-142">Il <xref:System.IO.Stream.ReadAsync%2A>metodo restituisce un <xref:System.Threading.Tasks.Task> \< <xref:System.Int32>>, pertanto la valutazione dell'attesa produce un `Int32` valore (`numRead`) dopo il completamento dell'operazione.</xref:System.Int32> </xref:System.Threading.Tasks.Task> </xref:System.IO.Stream.ReadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="1aede-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="1aede-143">Per ulteriori informazioni, vedere [Async restituire tipi (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="1aede-143">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
```vb  
Public Async Sub ProcessRead()  
    Dim filePath = "temp2.txt"  
  
    If File.Exists(filePath) = False Then  
        Debug.WriteLine("file not found: " & filePath)  
    Else  
        Try  
            Dim text As String = Await ReadTextAsync(filePath)  
            Debug.WriteLine(text)  
        Catch ex As Exception  
            Debug.WriteLine(ex.Message)  
        End Try  
    End If  
End Sub  
  
Private Async Function ReadTextAsync(filePath As String) As Task(Of String)  
  
    Using sourceStream As New FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize:=4096, useAsync:=True)  
  
        Dim sb As New StringBuilder  
  
        Dim buffer As Byte() = New Byte(&H1000) {}  
        Dim numRead As Integer  
        numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        While numRead <> 0  
            Dim text As String = Encoding.Unicode.GetString(buffer, 0, numRead)  
            sb.Append(text)  
  
            numRead = Await sourceStream.ReadAsync(buffer, 0, buffer.Length)  
        End While  
  
        Return sb.ToString  
    End Using  
End Function  
```  
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="1aede-144">/ O asincrone parallela</span><span class="sxs-lookup"><span data-stu-id="1aede-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="1aede-145">Nell'esempio seguente viene illustrato l'elaborazione parallela scrivendo 10 file di testo.</span><span class="sxs-lookup"><span data-stu-id="1aede-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="1aede-146">Per ogni file, il <xref:System.IO.Stream.WriteAsync%2A>metodo restituisce un'attività che viene quindi aggiunto a un elenco di attività.</xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="1aede-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="1aede-147">Il `Await Task.WhenAll(tasks)` istruzione termina il metodo e riprende all'interno del metodo dell'elaborazione di file completate per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="1aede-147">The `Await Task.WhenAll(tasks)` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="1aede-148">Nell'esempio vengono chiuse tutte <xref:System.IO.FileStream>le istanze in un `Finally` blocchi dopo le attività vengono completate.</xref:System.IO.FileStream></span><span class="sxs-lookup"><span data-stu-id="1aede-148">The example closes all <xref:System.IO.FileStream> instances in a `Finally` block after the tasks are complete.</span></span> <span data-ttu-id="1aede-149">Se ogni `FileStream` invece è stato creato in un `Imports` istruzione, il `FileStream` potrebbero essere eliminati prima del completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1aede-149">If each `FileStream` was instead created in a `Imports` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="1aede-150">Si noti che qualsiasi miglioramento delle prestazioni è quasi interamente dall'elaborazione in parallelo e non l'elaborazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="1aede-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="1aede-151">I vantaggi dell'asincronia sono che non impegnare più thread e che non bloccare il thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1aede-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
```vb  
Public Async Sub ProcessWriteMult()  
    Dim folder = "tempfolder\"  
    Dim tasks As New List(Of Task)  
    Dim sourceStreams As New List(Of FileStream)  
  
    Try  
        For index = 1 To 10  
            Dim text = "In file " & index.ToString & ControlChars.CrLf  
  
            Dim fileName = "thefile" & index.ToString("00") & ".txt"  
            Dim filePath = folder & fileName  
  
            Dim encodedText As Byte() = Encoding.Unicode.GetBytes(text)  
  
            Dim sourceStream As New FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize:=4096, useAsync:=True)  
  
            Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
            sourceStreams.Add(sourceStream)  
  
            tasks.Add(theTask)  
        Next  
  
        Await Task.WhenAll(tasks)  
    Finally  
        For Each sourceStream As FileStream In sourceStreams  
            sourceStream.Close()  
        Next  
    End Try  
End Sub  
```  
  
 <span data-ttu-id="1aede-152">Quando si utilizza il <xref:System.IO.Stream.WriteAsync%2A>e <xref:System.IO.Stream.ReadAsync%2A>metodi, è possibile specificare un <xref:System.Threading.CancellationToken>, che consente di annullare il flusso intermedio di operazione.</xref:System.Threading.CancellationToken> </xref:System.IO.Stream.ReadAsync%2A> </xref:System.IO.Stream.WriteAsync%2A></span><span class="sxs-lookup"><span data-stu-id="1aede-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="1aede-153">Per ulteriori informazioni, vedere [ottimizzazione Async applicazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) e [annullamento in thread gestiti](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).</span><span class="sxs-lookup"><span data-stu-id="1aede-153">For more information, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](http://msdn.microsoft.com/library/eea11fe5-d8b0-4314-bb5d-8a58166fb1c3).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aede-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aede-154">See Also</span></span>  
 <span data-ttu-id="1aede-155">[Programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="1aede-155">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="1aede-156"> [Tipi restituiti asincroni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="1aede-156"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="1aede-157"> [Flusso di controllo in programmi asincroni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span><span class="sxs-lookup"><span data-stu-id="1aede-157"> [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)</span></span>
