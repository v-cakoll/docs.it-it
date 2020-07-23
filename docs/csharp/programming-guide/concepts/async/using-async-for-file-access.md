---
title: Uso della funzionalità Async per l'accesso ai file (C#)
description: Informazioni su come usare la funzionalità Async per accedere ai file in C#. È possibile chiamare i metodi asincroni senza usare i callback o suddividere il codice tra i metodi.
ms.date: 07/20/2015
ms.assetid: bb018fea-5313-4c80-ab3f-7c24b2145bd9
ms.openlocfilehash: eb67bd408fe37b99e6c5ffdc2550e8f95110d7eb
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925124"
---
# <a name="using-async-for-file-access-c"></a><span data-ttu-id="3ff43-104">Uso della funzionalità Async per l'accesso ai file (C#)</span><span class="sxs-lookup"><span data-stu-id="3ff43-104">Using Async for File Access (C#)</span></span>
<span data-ttu-id="3ff43-105">È possibile usare la funzionalità Async per accedere ai file.</span><span class="sxs-lookup"><span data-stu-id="3ff43-105">You can use the async feature to access files.</span></span> <span data-ttu-id="3ff43-106">Con la funzionalità Async è possibile chiamare i metodi asincroni senza usare callback o suddividere il codice in più metodi o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="3ff43-106">By using the async feature, you can call into asynchronous methods without using callbacks or splitting your code across multiple methods or lambda expressions.</span></span> <span data-ttu-id="3ff43-107">Per rendere asincrono il codice sincrono, è sufficiente chiamare un metodo asincrono anziché un metodo sincrono e aggiungere alcune parole chiave al codice.</span><span class="sxs-lookup"><span data-stu-id="3ff43-107">To make synchronous code asynchronous, you just call an asynchronous method instead of a synchronous method and add a few keywords to the code.</span></span>  
  
 <span data-ttu-id="3ff43-108">È opportuno considerare i seguenti motivi per l'aggiunta della modalità asincrona alle chiamate di accesso ai file:</span><span class="sxs-lookup"><span data-stu-id="3ff43-108">You might consider the following reasons for adding asynchrony to file access calls:</span></span>  
  
- <span data-ttu-id="3ff43-109">La modalità asincrona rende più reattive le applicazioni dell'interfaccia utente perché il thread dell'interfaccia utente che avvia l'operazione può eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="3ff43-109">Asynchrony makes UI applications more responsive because the UI thread that launches the operation can perform other work.</span></span> <span data-ttu-id="3ff43-110">Se il thread dell'interfaccia utente deve eseguire codice che richiede molto tempo (ad esempio, più di 50 millisecondi), l'interfaccia utente può bloccarsi fino al completamento dell'I/O e il thread dell'interfaccia utente può nuovamente elaborare l'input di tastiera e mouse e altri eventi.</span><span class="sxs-lookup"><span data-stu-id="3ff43-110">If the UI thread must execute code that takes a long time (for example, more than 50 milliseconds), the UI may freeze until the I/O is complete and the UI thread can again process keyboard and mouse input and other events.</span></span>  
  
- <span data-ttu-id="3ff43-111">La modalità asincrona migliora la scalabilità di ASP.NET e di altre applicazioni basate su server, riducendo la necessità di thread.</span><span class="sxs-lookup"><span data-stu-id="3ff43-111">Asynchrony improves the scalability of ASP.NET and other server-based applications by reducing the need for threads.</span></span> <span data-ttu-id="3ff43-112">Se l'applicazione usa un thread dedicato per ogni risposta e vengono gestite contemporaneamente mille richieste, sono necessari mille thread.</span><span class="sxs-lookup"><span data-stu-id="3ff43-112">If the application uses a dedicated thread per response and a thousand requests are being handled simultaneously, a thousand threads are needed.</span></span> <span data-ttu-id="3ff43-113">Le operazioni asincrone non richiedono spesso l'uso di un thread durante l'attesa.</span><span class="sxs-lookup"><span data-stu-id="3ff43-113">Asynchronous operations often don’t need to use a thread during the wait.</span></span> <span data-ttu-id="3ff43-114">Usano brevemente il thread di completamento di I/O esistente alla fine.</span><span class="sxs-lookup"><span data-stu-id="3ff43-114">They use the existing I/O completion thread briefly at the end.</span></span>  
  
- <span data-ttu-id="3ff43-115">La latenza di un'operazione di accesso ai file può essere molto bassa nelle condizioni attuali, ma aumentare notevolmente in futuro.</span><span class="sxs-lookup"><span data-stu-id="3ff43-115">The latency of a file access operation might be very low under current conditions, but the latency may greatly increase in the future.</span></span> <span data-ttu-id="3ff43-116">Ad esempio, un file può essere spostato in tutt'altra parte del mondo.</span><span class="sxs-lookup"><span data-stu-id="3ff43-116">For example, a file may be moved to a server that's across the world.</span></span>  
  
- <span data-ttu-id="3ff43-117">Il sovraccarico aggiuntivo dovuto all'uso della funzionalità Async è ridotto.</span><span class="sxs-lookup"><span data-stu-id="3ff43-117">The added overhead of using the Async feature is small.</span></span>  
  
- <span data-ttu-id="3ff43-118">Le attività asincrone possono essere facilmente eseguite in parallelo.</span><span class="sxs-lookup"><span data-stu-id="3ff43-118">Asynchronous tasks can easily be run in parallel.</span></span>  
  
## <a name="running-the-examples"></a><span data-ttu-id="3ff43-119">Esecuzione degli esempi</span><span class="sxs-lookup"><span data-stu-id="3ff43-119">Running the Examples</span></span>  
 <span data-ttu-id="3ff43-120">Per eseguire gli esempi in questo argomento, è possibile creare un'**applicazione WPF** o un'**applicazione Windows Form** e quindi aggiungere un **pulsante**.</span><span class="sxs-lookup"><span data-stu-id="3ff43-120">To run the examples in this topic, you can create a **WPF Application** or a **Windows Forms Application** and then add a **Button**.</span></span> <span data-ttu-id="3ff43-121">Nell'evento `Click` del pulsante aggiungere una chiamata al primo metodo in ogni esempio.</span><span class="sxs-lookup"><span data-stu-id="3ff43-121">In the button's `Click` event, add a call to the first method in each example.</span></span>  
  
 <span data-ttu-id="3ff43-122">Negli esempi seguenti, includere le `using` direttive seguenti.</span><span class="sxs-lookup"><span data-stu-id="3ff43-122">In the following examples, include the following `using` directives.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Diagnostics;  
using System.IO;  
using System.Text;  
using System.Threading.Tasks;  
```  
  
## <a name="use-of-the-filestream-class"></a><span data-ttu-id="3ff43-123">Uso della classe FileStream</span><span class="sxs-lookup"><span data-stu-id="3ff43-123">Use of the FileStream Class</span></span>  
 <span data-ttu-id="3ff43-124">Negli esempi di questo argomento viene usata la classe <xref:System.IO.FileStream>, che ha un'opzione che determina la generazione di I/O asincrono a livello di sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3ff43-124">The examples in this topic use the <xref:System.IO.FileStream> class, which has an option that causes asynchronous I/O to occur at the operating system level.</span></span> <span data-ttu-id="3ff43-125">L'opzione consente di evitare il blocco di un thread del pool di thread in molti casi.</span><span class="sxs-lookup"><span data-stu-id="3ff43-125">By using this option, you can avoid blocking a ThreadPool thread in many cases.</span></span> <span data-ttu-id="3ff43-126">Per abilitare questa opzione, specificare l'argomento `useAsync=true` o `options=FileOptions.Asynchronous` nella chiamata al costruttore.</span><span class="sxs-lookup"><span data-stu-id="3ff43-126">To enable this option, you specify the `useAsync=true` or `options=FileOptions.Asynchronous` argument in the constructor call.</span></span>  
  
 <span data-ttu-id="3ff43-127">Non è possibile usare questa opzione con oggetti <xref:System.IO.StreamReader> e <xref:System.IO.StreamWriter> se questi vengono aperti direttamente tramite l'indicazione di un percorso.</span><span class="sxs-lookup"><span data-stu-id="3ff43-127">You can’t use this option with <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> if you open them directly by specifying a file path.</span></span> <span data-ttu-id="3ff43-128">È tuttavia possibile usare questa opzione se si fornisce loro un oggetto <xref:System.IO.Stream> aperto dalla classe <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="3ff43-128">However, you can use this option if you provide them a <xref:System.IO.Stream> that the <xref:System.IO.FileStream> class opened.</span></span> <span data-ttu-id="3ff43-129">Si noti che le chiamate asincrone sono più veloci nelle applicazioni dell'interfaccia utente anche se un thread del pool di thread è bloccato, poiché il thread dell'interfaccia utente non è bloccato durante l'attesa.</span><span class="sxs-lookup"><span data-stu-id="3ff43-129">Note that asynchronous calls are faster in UI apps even if a ThreadPool thread is blocked, because the UI thread isn’t blocked during the wait.</span></span>  
  
## <a name="writing-text"></a><span data-ttu-id="3ff43-130">Scrittura di testo</span><span class="sxs-lookup"><span data-stu-id="3ff43-130">Writing Text</span></span>  
 <span data-ttu-id="3ff43-131">Nell'esempio seguente viene scritto un testo in un file.</span><span class="sxs-lookup"><span data-stu-id="3ff43-131">The following example writes text to a file.</span></span> <span data-ttu-id="3ff43-132">Ad ogni istruzione await il metodo termina immediatamente.</span><span class="sxs-lookup"><span data-stu-id="3ff43-132">At each await statement, the method immediately exits.</span></span> <span data-ttu-id="3ff43-133">Completato l'I/O del file, il metodo riprende in corrispondenza dell'istruzione che segue l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="3ff43-133">When the file I/O is complete, the method resumes at the statement that follows the await statement.</span></span> <span data-ttu-id="3ff43-134">Si noti che il modificatore async si trova nella definizione dei metodi che usano l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="3ff43-134">Note that the async modifier is in the definition of methods that use the await statement.</span></span>  
  
```csharp  
public async Task ProcessWriteAsync()  
{  
    string filePath = @"temp2.txt";  
    string text = "Hello World\r\n";  
  
    await WriteTextAsync(filePath, text);  
}  
  
private async Task WriteTextAsync(string filePath, string text)  
{  
    byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Append, FileAccess.Write, FileShare.None,  
        bufferSize: 4096, useAsync: true))  
    {  
        await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
    };  
}  
```  
  
 <span data-ttu-id="3ff43-135">L'esempio originale usa l'istruzione `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, che è una contrazione delle due istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ff43-135">The original example has the statement `await sourceStream.WriteAsync(encodedText, 0, encodedText.Length);`, which is a contraction of the following two statements:</span></span>  
  
```csharp  
Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
await theTask;  
```  
  
 <span data-ttu-id="3ff43-136">La prima istruzione restituisce un'attività e determina l'avvio dell'elaborazione dei file.</span><span class="sxs-lookup"><span data-stu-id="3ff43-136">The first statement returns a task and causes file processing to start.</span></span> <span data-ttu-id="3ff43-137">La seconda istruzione con await induce il metodo a terminare immediatamente e restituire un'attività diversa.</span><span class="sxs-lookup"><span data-stu-id="3ff43-137">The second statement with the await causes the method to immediately exit and return a different task.</span></span> <span data-ttu-id="3ff43-138">Al termine dell'elaborazione dei file l'esecuzione torna quindi all'istruzione che segue await.</span><span class="sxs-lookup"><span data-stu-id="3ff43-138">When the file processing later completes, execution returns to the statement that follows the await.</span></span> <span data-ttu-id="3ff43-139">Per altre informazioni, vedere [Flusso di controllo in programmi asincroni (C#)](./control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="3ff43-139">For more information, see  [Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md).</span></span>  
  
## <a name="reading-text"></a><span data-ttu-id="3ff43-140">Lettura di testo</span><span class="sxs-lookup"><span data-stu-id="3ff43-140">Reading Text</span></span>  
 <span data-ttu-id="3ff43-141">Nell'esempio seguente viene letto del testo da un file.</span><span class="sxs-lookup"><span data-stu-id="3ff43-141">The following example reads text from a file.</span></span> <span data-ttu-id="3ff43-142">Il testo viene memorizzato nel buffer e, in questo caso, inserito in un oggetto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="3ff43-142">The text is buffered and, in this case, placed into a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="3ff43-143">A differenza dell'esempio precedente, la valutazione di await produce un valore.</span><span class="sxs-lookup"><span data-stu-id="3ff43-143">Unlike in the previous example, the evaluation of the await produces a value.</span></span> <span data-ttu-id="3ff43-144">Il metodo <xref:System.IO.Stream.ReadAsync%2A> restituisce un <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>. Pertanto la valutazione dell'attesa produce un valore `Int32` (`numRead`) dopo il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="3ff43-144">The <xref:System.IO.Stream.ReadAsync%2A> method returns a <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>, so the evaluation of the await produces an `Int32` value (`numRead`) after the operation completes.</span></span> <span data-ttu-id="3ff43-145">Per altre informazioni, vedere [Tipi restituiti asincroni (C#)](./async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="3ff43-145">For more information, see [Async Return Types (C#)](./async-return-types.md).</span></span>  
  
```csharp  
public async Task ProcessReadAsync()  
{  
    string filePath = @"temp2.txt";  
  
    if (File.Exists(filePath) == false)  
    {  
        Debug.WriteLine("file not found: " + filePath);  
    }  
    else  
    {  
        try  
        {  
            string text = await ReadTextAsync(filePath);  
            Debug.WriteLine(text);  
        }  
        catch (Exception ex)  
        {  
            Debug.WriteLine(ex.Message);  
        }  
    }  
}  
  
private async Task<string> ReadTextAsync(string filePath)  
{  
    using (FileStream sourceStream = new FileStream(filePath,  
        FileMode.Open, FileAccess.Read, FileShare.Read,  
        bufferSize: 4096, useAsync: true))  
    {  
        StringBuilder sb = new StringBuilder();  
  
        byte[] buffer = new byte[0x1000];  
        int numRead;  
        while ((numRead = await sourceStream.ReadAsync(buffer, 0, buffer.Length)) != 0)  
        {  
            string text = Encoding.Unicode.GetString(buffer, 0, numRead);  
            sb.Append(text);  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
## <a name="parallel-asynchronous-io"></a><span data-ttu-id="3ff43-146">I/O asincrono parallelo</span><span class="sxs-lookup"><span data-stu-id="3ff43-146">Parallel Asynchronous I/O</span></span>  
 <span data-ttu-id="3ff43-147">Nell'esempio seguente viene illustrata l'elaborazione parallela per la scrittura di 10 file di testo.</span><span class="sxs-lookup"><span data-stu-id="3ff43-147">The following example demonstrates parallel processing by writing 10 text files.</span></span> <span data-ttu-id="3ff43-148">Per ogni file, il metodo <xref:System.IO.Stream.WriteAsync%2A> restituisce un'attività che successivamente viene aggiunta a un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="3ff43-148">For each file, the <xref:System.IO.Stream.WriteAsync%2A> method returns a task that is then added to a list of tasks.</span></span> <span data-ttu-id="3ff43-149">L'istruzione `await Task.WhenAll(tasks);` termina il metodo e riprende all'interno del metodo quando l'elaborazione dei file è completata per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="3ff43-149">The `await Task.WhenAll(tasks);` statement exits the method and resumes within the method when file processing is complete for all of the tasks.</span></span>  
  
 <span data-ttu-id="3ff43-150">L'esempio chiude tutte le istanze di <xref:System.IO.FileStream> in un blocco `finally` dopo il completamento delle attività.</span><span class="sxs-lookup"><span data-stu-id="3ff43-150">The example closes all <xref:System.IO.FileStream> instances in a `finally` block after the tasks are complete.</span></span> <span data-ttu-id="3ff43-151">Se invece ogni oggetto `FileStream` è stato creato in un'istruzione `using`, è possibile che l'oggetto `FileStream` venga eliminato prima del completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3ff43-151">If each `FileStream` was instead created in a `using` statement, the `FileStream` might be disposed of before the task was complete.</span></span>  
  
 <span data-ttu-id="3ff43-152">Si noti che qualsiasi miglioramento delle prestazioni è dovuto quasi interamente all'elaborazione parallela e non all'elaborazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="3ff43-152">Note that any performance boost is almost entirely from the parallel processing and not the asynchronous processing.</span></span> <span data-ttu-id="3ff43-153">I vantaggi dell'asincronia sono che l'elaborazione non blocca più thread e non blocca il thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3ff43-153">The advantages of asynchrony are that it doesn’t tie up multiple threads, and that it doesn’t tie up the user interface thread.</span></span>  
  
```csharp  
public async Task ProcessWriteMultAsync()  
{  
    string folder = @"tempfolder\";  
    List<Task> tasks = new List<Task>();  
    List<FileStream> sourceStreams = new List<FileStream>();  
  
    try  
    {  
        for (int index = 1; index <= 10; index++)  
        {  
            string text = "In file " + index.ToString() + "\r\n";  
  
            string fileName = "thefile" + index.ToString("00") + ".txt";  
            string filePath = folder + fileName;  
  
            byte[] encodedText = Encoding.Unicode.GetBytes(text);  
  
            FileStream sourceStream = new FileStream(filePath,  
                FileMode.Append, FileAccess.Write, FileShare.None,  
                bufferSize: 4096, useAsync: true);  
  
            Task theTask = sourceStream.WriteAsync(encodedText, 0, encodedText.Length);  
            sourceStreams.Add(sourceStream);  
  
            tasks.Add(theTask);  
        }  
  
        await Task.WhenAll(tasks);  
    }  
  
    finally  
    {  
        foreach (FileStream sourceStream in sourceStreams)  
        {  
            sourceStream.Close();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="3ff43-154">Quando si usano i metodi <xref:System.IO.Stream.WriteAsync%2A> e <xref:System.IO.Stream.ReadAsync%2A>, è possibile specificare uno struct <xref:System.Threading.CancellationToken>, che consente di annullare l'operazione nel corso del flusso.</span><span class="sxs-lookup"><span data-stu-id="3ff43-154">When using the <xref:System.IO.Stream.WriteAsync%2A> and <xref:System.IO.Stream.ReadAsync%2A> methods, you can specify a <xref:System.Threading.CancellationToken>, which you can use to cancel the operation mid-stream.</span></span> <span data-ttu-id="3ff43-155">Per altre informazioni, vedere [Ottimizzazione dell'app asincrona (C#)](./fine-tuning-your-async-application.md) e [Annullamento in thread gestiti](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="3ff43-155">For more information, see [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) and [Cancellation in Managed Threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff43-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ff43-156">See also</span></span>

- [<span data-ttu-id="3ff43-157">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="3ff43-157">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="3ff43-158">Tipi restituiti async (C#)</span><span class="sxs-lookup"><span data-stu-id="3ff43-158">Async Return Types (C#)</span></span>](./async-return-types.md)
- [<span data-ttu-id="3ff43-159">Flusso di controllo nei programmi asincroni (C#)</span><span class="sxs-lookup"><span data-stu-id="3ff43-159">Control Flow in Async Programs (C#)</span></span>](./control-flow-in-async-programs.md)
