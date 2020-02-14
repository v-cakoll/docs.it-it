---
title: streamWriterBufferedDataLost (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
ms.openlocfilehash: 82940b40b302f4a928547f2e6a0c285727e13934
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216108"
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="bfe75-102">streamWriterBufferedDataLost (MDA)</span><span class="sxs-lookup"><span data-stu-id="bfe75-102">streamWriterBufferedDataLost MDA</span></span>
<span data-ttu-id="bfe75-103">L'assistente al debug gestito `streamWriterBufferedDataLost` viene attivato quando viene scritto un <xref:System.IO.StreamWriter>, ma il metodo <xref:System.IO.StreamWriter.Flush%2A> o <xref:System.IO.StreamWriter.Close%2A> non viene chiamato in seguito prima dell'eliminazione definitiva dell'istanza di <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="bfe75-103">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="bfe75-104">Quando questo assistente al debug gestito è abilitato, il runtime determina se tutti i dati memorizzati nel buffer esistono ancora in <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="bfe75-104">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="bfe75-105">In caso affermativo, l'assistente al debug gestito viene attivato.</span><span class="sxs-lookup"><span data-stu-id="bfe75-105">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="bfe75-106">La chiamata dei metodi <xref:System.GC.Collect%2A> e <xref:System.GC.WaitForPendingFinalizers%2A> può forzare l'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="bfe75-106">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="bfe75-107">In caso contrario, i finalizzatori vengono eseguiti in momenti apparentemente arbitrari e probabilmente non vengono eseguiti affatto all'uscita dal processo.</span><span class="sxs-lookup"><span data-stu-id="bfe75-107">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="bfe75-108">L'esecuzione dei finalizzatori in modo esplicito con questo assistente al debug gestito sarà utile per riprodurre in modo più affidabile questo tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="bfe75-108">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bfe75-109">Sintomi</span><span class="sxs-lookup"><span data-stu-id="bfe75-109">Symptoms</span></span>  
 <span data-ttu-id="bfe75-110">Un <xref:System.IO.StreamWriter> non scrive gli ultimi 1-4 KB di dati in un file.</span><span class="sxs-lookup"><span data-stu-id="bfe75-110">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bfe75-111">Causa</span><span class="sxs-lookup"><span data-stu-id="bfe75-111">Cause</span></span>  
 <span data-ttu-id="bfe75-112"><xref:System.IO.StreamWriter> memorizza nel buffer i dati internamente e ciò richiede che il metodo <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> venga chiamato per scrivere i dati memorizzati nel buffer nell'archivio dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="bfe75-112">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="bfe75-113">Se il metodo <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> non viene chiamato in modo appropriato, i dati memorizzati nel buffer nell'istanza di <xref:System.IO.StreamWriter> potrebbero non essere scritti come previsto.</span><span class="sxs-lookup"><span data-stu-id="bfe75-113">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="bfe75-114">Di seguito è riportato un esempio di codice non corretto che dovrebbe essere intercettato da questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="bfe75-114">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="bfe75-115">Il codice precedente attiverà questo assistente al debug gestito in modo più affidabile se viene attivata e poi sospesa un'operazione di Garbage Collection fino al completamento dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="bfe75-115">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="bfe75-116">Per analizzare questo tipo di problema, è possibile aggiungere il codice seguente alla fine del metodo precedente in una build di debug.</span><span class="sxs-lookup"><span data-stu-id="bfe75-116">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="bfe75-117">Ciò sarà utile per attivare in modo affidabile l'assistente al debug gestito, ma ovviamente non risolve la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="bfe75-117">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="bfe75-118">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="bfe75-118">Resolution</span></span>  
 <span data-ttu-id="bfe75-119">Assicurarsi di chiamare <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> sul <xref:System.IO.StreamWriter> prima di chiudere un'applicazione o qualsiasi blocco di codice che ha un'istanza di un <xref:System.IO.StreamWriter>.</span><span class="sxs-lookup"><span data-stu-id="bfe75-119">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="bfe75-120">Uno dei meccanismi migliori per ottenere questo risultato consiste nel creare l'istanza con un blocco `using` C# (`Using` in Visual Basic), che garantisce la chiamata del metodo <xref:System.IO.StreamWriter.Dispose%2A> per il writer, con conseguente chiusura corretta dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="bfe75-120">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="bfe75-121">Il codice seguente mostra la stessa soluzione, con `try/finally` invece di `using`.</span><span class="sxs-lookup"><span data-stu-id="bfe75-121">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
```csharp
StreamWriter sw;  
try   
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally   
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 <span data-ttu-id="bfe75-122">Se nessuna di queste soluzioni può essere usata (ad esempio, se un <xref:System.IO.StreamWriter> viene archiviato in una variabile statica e non è possibile eseguire facilmente il codice alla fine della durata), la chiamata di <xref:System.IO.StreamWriter.Flush%2A> su <xref:System.IO.StreamWriter> dopo l'ultimo uso oppure l'impostazione della proprietà <xref:System.IO.StreamWriter.AutoFlush%2A> su `true` prima del primo uso dovrebbe consentire di evitare questo problema.</span><span class="sxs-lookup"><span data-stu-id="bfe75-122">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
```csharp
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()   
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bfe75-123">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="bfe75-123">Effect on the Runtime</span></span>  
 <span data-ttu-id="bfe75-124">L'assistente al debug gestito non ha alcun effetto sull'ambiente di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bfe75-124">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bfe75-125">Output</span><span class="sxs-lookup"><span data-stu-id="bfe75-125">Output</span></span>  
 <span data-ttu-id="bfe75-126">Un messaggio che indica che si è verificata questa violazione.</span><span class="sxs-lookup"><span data-stu-id="bfe75-126">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bfe75-127">Configurazione</span><span class="sxs-lookup"><span data-stu-id="bfe75-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfe75-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe75-128">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="bfe75-129">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="bfe75-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
