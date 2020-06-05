---
title: Utilizzo della funzionalità Async per l'accesso ai file
ms.date: 07/20/2015
ms.assetid: c989305f-08e3-4687-95c3-948465cda202
ms.openlocfilehash: 2ee1efa69f4b13224be65fe802ebf5f834c941aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400771"
---
# <a name="using-async-for-file-access-visual-basic"></a><span data-ttu-id="8513c-102">Uso della funzionalità Async per l'accesso ai file (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8513c-102">Using Async for File Access (Visual Basic)</span></span>
<span data-ttu-id="8513c-103">È possibile usare la funzionalità Async per accedere ai file.</span><span class="sxs-lookup"><span data-stu-id="8513c-103">You can use the Async feature to access files.</span></span> <span data-ttu-id="8513c-104">Tramite la funzionalità Async, è possibile chiamare i metodi asincroni senza utilizzare callback o suddividere il codice in più metodi o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="8513c-104">By using the Async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="8513c-105">Per rendere asincrono il codice sincrono, è sufficiente chiamare un metodo asincrono anziché un metodo sincrono e aggiungere alcune parole chiave al codice.</span><span class="sxs-lookup"><span data-stu-id="8513c-105">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="8513c-106">È opportuno considerare i seguenti motivi per l'aggiunta della modalità asincrona alle chiamate di accesso ai file:</span><span class="sxs-lookup"><span data-stu-id="8513c-106">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
- <span data-ttu-id="8513c-107">La modalità asincrona rende più reattive le applicazioni dell'interfaccia utente perché il thread dell'interfaccia utente che avvia l'operazione può eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="8513c-107">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="8513c-108">Se il thread dell'interfaccia utente deve eseguire codice che richiede molto tempo (ad esempio, più di 50 millisecondi), l'interfaccia utente può bloccarsi fino al completamento dell'I/O e il thread dell'interfaccia utente può nuovamente elaborare l'input di tastiera e mouse e altri eventi.</span><span class="sxs-lookup"><span data-stu-id="8513c-108">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
- <span data-ttu-id="8513c-109">La modalità asincrona migliora la scalabilità di ASP.NET e di altre applicazioni basate su server, riducendo la necessità di thread.</span><span class="sxs-lookup"><span data-stu-id="8513c-109">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="8513c-110">Se l'applicazione usa un thread dedicato per ogni risposta e vengono gestite contemporaneamente mille richieste, sono necessari mille thread.</span><span class="sxs-lookup"><span data-stu-id="8513c-110">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="8513c-111">Le operazioni asincrone non richiedono spesso l'uso di un thread durante l'attesa.</span><span class="sxs-lookup"><span data-stu-id="8513c-111">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="8513c-112">Usano brevemente il thread di completamento di I/O esistente alla fine.</span><span class="sxs-lookup"><span data-stu-id="8513c-112">They use the existing I/O completion thread briefly at the end.</span></span>  
  
- <span data-ttu-id="8513c-113">La latenza di un'operazione di accesso ai file può essere molto bassa nelle condizioni attuali, ma aumentare notevolmente in futuro.</span><span class="sxs-lookup"><span data-stu-id="8513c-113">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="8513c-114">Ad esempio, un file può essere spostato in tutt'altra parte del mondo.</span><span class="sxs-lookup"><span data-stu-id="8513c-114">For example, a file may be moved to a server that's across the world.</span></span>  
  
- <span data-ttu-id="8513c-115">Il sovraccarico aggiuntivo dovuto all'uso della funzionalità Async è ridotto.</span><span class="sxs-lookup"><span data-stu-id="8513c-115">The added overhead of using the Async feature is small.</span></span>  
  
- <span data-ttu-id="8513c-116">Le attività asincrone possono essere facilmente eseguite in parallelo.</span><span class="sxs-lookup"><span data-stu-id="8513c-116">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="8513c-117">Esecuzione degli esempi</span><span class="sxs-lookup"><span data-stu-id="8513c-117">Running the Examples</span></span>  
 <span data-ttu-id="8513c-118">Per eseguire gli esempi in questo argomento, è possibile creare un'**applicazione WPF** o un'**applicazione Windows Form** e quindi aggiungere un **pulsante**.</span><span class="sxs-lookup"><span data-stu-id="8513c-118">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="8513c-119">Nell'evento `Click` del pulsante aggiungere una chiamata al primo metodo in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="8513c-119">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="8513c-120">Negli esempi seguenti includere le istruzioni `Imports` indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8513c-120">In the following examples, include the following `Imports` statements.</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="8513c-121">Uso della classe FileStream</span><span class="sxs-lookup"><span data-stu-id="8513c-121">Use of the FileStream Class</span></span>  
 <span data-ttu-id="8513c-122">Negli esempi di questo argomento viene usata la classe <xref:System.IO.FileStream>, che ha un'opzione che determina la generazione di I/O asincrono a livello di sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8513c-122">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="8513c-123">L'opzione consente di evitare il blocco di un thread del pool di thread in molti casi.</span><span class="sxs-lookup"><span data-stu-id="8513c-123">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="8513c-124">Per abilitare questa opzione, specificare l'argomento `useAsync=true` o `options=FileOptions.Asynchronous` nella chiamata al costruttore.</span><span class="sxs-lookup"><span data-stu-id="8513c-124">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="8513c-125">Non è possibile usare questa opzione con oggetti <xref:System.IO.StreamReader> e <xref:System.IO.StreamWriter> se questi vengono aperti direttamente tramite l'indicazione di un percorso.</span><span class="sxs-lookup"><span data-stu-id="8513c-125">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="8513c-126">È tuttavia possibile usare questa opzione se si fornisce loro un oggetto <xref:System.IO.Stream> aperto dalla classe <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="8513c-126">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="8513c-127">Si noti che le chiamate asincrone sono più veloci nelle applicazioni dell'interfaccia utente anche se un thread del pool di thread è bloccato, poiché il thread dell'interfaccia utente non è bloccato durante l'attesa.</span><span class="sxs-lookup"><span data-stu-id="8513c-127">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="8513c-128">Scrittura di testo</span><span class="sxs-lookup"><span data-stu-id="8513c-128">Writing Text</span></span>  
 <span data-ttu-id="8513c-129">Nell'esempio seguente viene scritto un testo in un file.</span><span class="sxs-lookup"><span data-stu-id="8513c-129">The following example writes text to a file.</span></span> <span data-ttu-id="8513c-130">Ad ogni istruzione await il metodo termina immediatamente.</span><span class="sxs-lookup"><span data-stu-id="8513c-130">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="8513c-131">Completato l'I/O del file, il metodo riprende in corrispondenza dell'istruzione che segue l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="8513c-131">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="8513c-132">Si noti che il modificatore async si trova nella definizione dei metodi che usano l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="8513c-132">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
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
  
 <span data-ttu-id="8513c-133">L'esempio originale usa l'istruzione `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, che è una contrazione delle due istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8513c-133">The original example has the statement `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, which is a contraction of the following two statements:</span></span>  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 <span data-ttu-id="8513c-134">La prima istruzione restituisce un'attività e determina l'avvio dell'elaborazione dei file.</span><span class="sxs-lookup"><span data-stu-id="8513c-134">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="8513c-135">La seconda istruzione con await induce il metodo a terminare immediatamente e restituire un'attività diversa.</span><span class="sxs-lookup"><span data-stu-id="8513c-135">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="8513c-136">Al termine dell'elaborazione dei file l'esecuzione torna quindi all'istruzione che segue await.</span><span class="sxs-lookup"><span data-stu-id="8513c-136">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="8513c-137">Per ulteriori informazioni, vedere [flusso di controllo in programmi asincroni (Visual Basic)](control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="8513c-137">For more information, see  [Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="8513c-138">Lettura di testo</span><span class="sxs-lookup"><span data-stu-id="8513c-138">Reading Text</span></span>  
 <span data-ttu-id="8513c-139">Nell'esempio seguente viene letto del testo da un file.</span><span class="sxs-lookup"><span data-stu-id="8513c-139">The following example reads text from a file.</span></span> <span data-ttu-id="8513c-140">Il testo viene memorizzato nel buffer e, in questo caso, inserito in un oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="8513c-140">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="8513c-141">A differenza dell'esempio precedente, la valutazione di await produce un valore.</span><span class="sxs-lookup"><span data-stu-id="8513c-141">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="8513c-142">Il metodo <xref:System.IO.Stream.ReadAsync%2A> restituisce un <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>. Pertanto la valutazione dell'attesa produce un valore `Int32` (`numRead`) dopo il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="8513c-142">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="8513c-143">Per ulteriori informazioni, vedere [tipi restituiti asincroni (Visual Basic)](async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="8513c-143">For more information, see [Async Return Types (Visual Basic)](async-return-types.md).</span></span>  
  
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
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="8513c-144">I/O asincrono parallelo</span><span class="sxs-lookup"><span data-stu-id="8513c-144">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="8513c-145">Nell'esempio seguente viene illustrata l'elaborazione parallela per la scrittura di 10 file di testo.</span><span class="sxs-lookup"><span data-stu-id="8513c-145">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="8513c-146">Per ogni file, il metodo <xref:System.IO.Stream.WriteAsync%2A> restituisce un'attività che successivamente viene aggiunta a un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="8513c-146">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="8513c-147">L'istruzione `Await Task.WhenAll(tasks)` termina il metodo e riprende all'interno del metodo quando l'elaborazione dei file è completata per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="8513c-147">The `Await Task.WhenAll(tasks)` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="8513c-148">L'esempio chiude tutte le istanze di <xref:System.IO.FileStream> in un blocco `Finally` dopo il completamento delle attività.</span><span class="sxs-lookup"><span data-stu-id="8513c-148">The example closes all <xref:System.IO.FileStream> instances in a `Finally` block after the tasks are complete.</span></span> <span data-ttu-id="8513c-149">Se invece ogni oggetto `FileStream` è stato creato in un'istruzione `Imports`, è possibile che l'oggetto `FileStream` venga eliminato prima del completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8513c-149">If each `FileStream` was instead created in a `Imports` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="8513c-150">Si noti che qualsiasi miglioramento delle prestazioni è dovuto quasi interamente all'elaborazione parallela e non all'elaborazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="8513c-150">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="8513c-151">I vantaggi dell'asincronia sono che l'elaborazione non blocca più thread e non blocca il thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8513c-151">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
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
  
 <span data-ttu-id="8513c-152">Quando si usano i metodi <xref:System.IO.Stream.WriteAsync%2A> e <xref:System.IO.Stream.ReadAsync%2A>, è possibile specificare uno struct <xref:System.Threading.CancellationToken>, che consente di annullare l'operazione nel corso del flusso.</span><span class="sxs-lookup"><span data-stu-id="8513c-152">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="8513c-153">Per altre informazioni, vedere [ottimizzazione dell'applicazione asincrona (Visual Basic)](fine-tuning-your-async-application.md) e [annullamento nei thread gestiti](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="8513c-153">For more information, see [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8513c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8513c-154">See also</span></span>

- [<span data-ttu-id="8513c-155">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8513c-155">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="8513c-156">Tipi restituiti asincroni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8513c-156">Async Return Types (Visual Basic)</span></span>](async-return-types.md)
- [<span data-ttu-id="8513c-157">Flusso di controllo in programmi asincroni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8513c-157">Control Flow in Async Programs (Visual Basic)</span></span>](control-flow-in-async-programs.md)
