---
title: streamWriterBufferedDataLost (MDA)
description: Esaminare l'assistente al debug gestito (MDA) streamWriterBufferedDataLost, che può essere attivato se un StreamWriter non scrive gli ultimi 1-4 KB di dati in un file.
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
ms.openlocfilehash: 0c10ea6bb9dc0aaafa2ac1798696579af7592895
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803482"
---
# <a name="streamwriterbuffereddatalost-mda"></a>streamWriterBufferedDataLost (MDA)
L'assistente al debug gestito `streamWriterBufferedDataLost` viene attivato quando viene scritto un <xref:System.IO.StreamWriter>, ma il metodo <xref:System.IO.StreamWriter.Flush%2A> o <xref:System.IO.StreamWriter.Close%2A> non viene chiamato in seguito prima dell'eliminazione definitiva dell'istanza di <xref:System.IO.StreamWriter>. Quando questo assistente al debug gestito è abilitato, il runtime determina se tutti i dati memorizzati nel buffer esistono ancora in <xref:System.IO.StreamWriter>. In caso affermativo, l'assistente al debug gestito viene attivato. La chiamata dei metodi <xref:System.GC.Collect%2A> e <xref:System.GC.WaitForPendingFinalizers%2A> può forzare l'esecuzione dei finalizzatori. In caso contrario, i finalizzatori vengono eseguiti in momenti apparentemente arbitrari e probabilmente non vengono eseguiti affatto all'uscita dal processo. L'esecuzione dei finalizzatori in modo esplicito con questo assistente al debug gestito sarà utile per riprodurre in modo più affidabile questo tipo di problema.  
  
## <a name="symptoms"></a>Sintomi  
 Un <xref:System.IO.StreamWriter> non scrive gli ultimi 1-4 KB di dati in un file.  
  
## <a name="cause"></a>Causa  
 <xref:System.IO.StreamWriter> memorizza nel buffer i dati internamente e ciò richiede che il metodo <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> venga chiamato per scrivere i dati memorizzati nel buffer nell'archivio dati sottostante. Se il metodo <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> non viene chiamato in modo appropriato, i dati memorizzati nel buffer nell'istanza di <xref:System.IO.StreamWriter> potrebbero non essere scritti come previsto.  
  
 Di seguito è riportato un esempio di codice non corretto che dovrebbe essere intercettato da questo assistente al debug gestito.  
  
```csharp  
// Poorly written code.  
void Write()
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 Il codice precedente attiverà questo assistente al debug gestito in modo più affidabile se viene attivata e poi sospesa un'operazione di Garbage Collection fino al completamento dei finalizzatori. Per analizzare questo tipo di problema, è possibile aggiungere il codice seguente alla fine del metodo precedente in una build di debug. Ciò sarà utile per attivare in modo affidabile l'assistente al debug gestito, ma ovviamente non risolve la causa del problema.  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a>Soluzione  
 Assicurarsi di chiamare <xref:System.IO.StreamWriter.Close%2A> o <xref:System.IO.StreamWriter.Flush%2A> sul <xref:System.IO.StreamWriter> prima di chiudere un'applicazione o qualsiasi blocco di codice che ha un'istanza di un <xref:System.IO.StreamWriter>. Uno dei meccanismi migliori per ottenere questo risultato consiste nel creare l'istanza con un blocco `using` C# (`Using` in Visual Basic), che garantisce la chiamata del metodo <xref:System.IO.StreamWriter.Dispose%2A> per il writer, con conseguente chiusura corretta dell'istanza.  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))
{  
    sw.WriteLine("Data");  
}  
```  
  
 Il codice seguente mostra la stessa soluzione, con `try/finally` invece di `using`.  
  
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
  
 Se nessuna di queste soluzioni può essere usata (ad esempio, se un <xref:System.IO.StreamWriter> viene archiviato in una variabile statica e non è possibile eseguire facilmente il codice alla fine della durata), la chiamata di <xref:System.IO.StreamWriter.Flush%2A> su <xref:System.IO.StreamWriter> dopo l'ultimo uso oppure l'impostazione della proprietà <xref:System.IO.StreamWriter.AutoFlush%2A> su `true` prima del primo uso dovrebbe consentire di evitare questo problema.  
  
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
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto sull'ambiente di esecuzione.  
  
## <a name="output"></a>Output  
 Un messaggio che indica che si è verificata questa violazione.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamWriter>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
