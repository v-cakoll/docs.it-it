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
# <a name="using-async-for-file-access-visual-basic"></a>Uso della funzionalità Async per l'accesso ai file (Visual Basic)
È possibile usare la funzionalità Async per accedere ai file. Tramite la funzionalità Async, è possibile chiamare i metodi asincroni senza utilizzare callback o suddividere il codice in più metodi o espressioni lambda. Per rendere asincrono il codice sincrono, è sufficiente chiamare un metodo asincrono anziché un metodo sincrono e aggiungere alcune parole chiave al codice.  
  
 È opportuno considerare i seguenti motivi per l'aggiunta della modalità asincrona alle chiamate di accesso ai file:  
  
- La modalità asincrona rende più reattive le applicazioni dell'interfaccia utente perché il thread dell'interfaccia utente che avvia l'operazione può eseguire altre operazioni. Se il thread dell'interfaccia utente deve eseguire codice che richiede molto tempo (ad esempio, più di 50 millisecondi), l'interfaccia utente può bloccarsi fino al completamento dell'I/O e il thread dell'interfaccia utente può nuovamente elaborare l'input di tastiera e mouse e altri eventi.  
  
- La modalità asincrona migliora la scalabilità di ASP.NET e di altre applicazioni basate su server, riducendo la necessità di thread. Se l'applicazione usa un thread dedicato per ogni risposta e vengono gestite contemporaneamente mille richieste, sono necessari mille thread. Le operazioni asincrone non richiedono spesso l'uso di un thread durante l'attesa. Usano brevemente il thread di completamento di I/O esistente alla fine.  
  
- La latenza di un'operazione di accesso ai file può essere molto bassa nelle condizioni attuali, ma aumentare notevolmente in futuro. Ad esempio, un file può essere spostato in tutt'altra parte del mondo.  
  
- Il sovraccarico aggiuntivo dovuto all'uso della funzionalità Async è ridotto.  
  
- Le attività asincrone possono essere facilmente eseguite in parallelo.  
  
## <a name="running-the-examples"></a>Esecuzione degli esempi  
 Per eseguire gli esempi in questo argomento, è possibile creare un'**applicazione WPF** o un'**applicazione Windows Form** e quindi aggiungere un **pulsante**. Nell'evento `Click` del pulsante aggiungere una chiamata al primo metodo in ogni esempio.  
  
 Negli esempi seguenti includere le istruzioni `Imports` indicate di seguito.  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Diagnostics  
Imports System.IO  
Imports System.Text  
Imports System.Threading.Tasks  
```  
  
## <a name="use-of-the-filestream-class"></a>Uso della classe FileStream  
 Negli esempi di questo argomento viene usata la classe <xref:System.IO.FileStream>, che ha un'opzione che determina la generazione di I/O asincrono a livello di sistema operativo. L'opzione consente di evitare il blocco di un thread del pool di thread in molti casi. Per abilitare questa opzione, specificare l'argomento `useAsync=true` o `options=FileOptions.Asynchronous` nella chiamata al costruttore.  
  
 Non è possibile usare questa opzione con oggetti <xref:System.IO.StreamReader> e <xref:System.IO.StreamWriter> se questi vengono aperti direttamente tramite l'indicazione di un percorso. È tuttavia possibile usare questa opzione se si fornisce loro un oggetto <xref:System.IO.Stream> aperto dalla classe <xref:System.IO.FileStream>. Si noti che le chiamate asincrone sono più veloci nelle applicazioni dell'interfaccia utente anche se un thread del pool di thread è bloccato, poiché il thread dell'interfaccia utente non è bloccato durante l'attesa.  
  
## <a name="writing-text"></a>Scrittura di testo  
 Nell'esempio seguente viene scritto un testo in un file. Ad ogni istruzione await il metodo termina immediatamente. Completato l'I/O del file, il metodo riprende in corrispondenza dell'istruzione che segue l'istruzione await. Si noti che il modificatore async si trova nella definizione dei metodi che usano l'istruzione await.  
  
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
  
 L'esempio originale usa l'istruzione `Await sourceStream.WriteAsync(encodedText, 0, encodedText.Length)`, che è una contrazione delle due istruzioni seguenti:  
  
```vb  
Dim theTask As Task = sourceStream.WriteAsync(encodedText, 0, encodedText.Length)  
Await theTask  
```  
  
 La prima istruzione restituisce un'attività e determina l'avvio dell'elaborazione dei file. La seconda istruzione con await induce il metodo a terminare immediatamente e restituire un'attività diversa. Al termine dell'elaborazione dei file l'esecuzione torna quindi all'istruzione che segue await. Per ulteriori informazioni, vedere [flusso di controllo in programmi asincroni (Visual Basic)](control-flow-in-async-programs.md).  
  
## <a name="reading-text"></a>Lettura di testo  
 Nell'esempio seguente viene letto del testo da un file. Il testo viene memorizzato nel buffer e, in questo caso, inserito in un oggetto <xref:System.Text.StringBuilder>. A differenza dell'esempio precedente, la valutazione di await produce un valore. Il metodo <xref:System.IO.Stream.ReadAsync%2A> restituisce un <xref:System.Threading.Tasks.Task>\<<xref:System.Int32>>. Pertanto la valutazione dell'attesa produce un valore `Int32` (`numRead`) dopo il completamento dell'operazione. Per ulteriori informazioni, vedere [tipi restituiti asincroni (Visual Basic)](async-return-types.md).  
  
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
  
## <a name="parallel-asynchronous-io"></a>I/O asincrono parallelo  
 Nell'esempio seguente viene illustrata l'elaborazione parallela per la scrittura di 10 file di testo. Per ogni file, il metodo <xref:System.IO.Stream.WriteAsync%2A> restituisce un'attività che successivamente viene aggiunta a un elenco di attività. L'istruzione `Await Task.WhenAll(tasks)` termina il metodo e riprende all'interno del metodo quando l'elaborazione dei file è completata per tutte le attività.  
  
 L'esempio chiude tutte le istanze di <xref:System.IO.FileStream> in un blocco `Finally` dopo il completamento delle attività. Se invece ogni oggetto `FileStream` è stato creato in un'istruzione `Imports`, è possibile che l'oggetto `FileStream` venga eliminato prima del completamento dell'attività.  
  
 Si noti che qualsiasi miglioramento delle prestazioni è dovuto quasi interamente all'elaborazione parallela e non all'elaborazione asincrona. I vantaggi dell'asincronia sono che l'elaborazione non blocca più thread e non blocca il thread dell'interfaccia utente.  
  
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
  
 Quando si usano i metodi <xref:System.IO.Stream.WriteAsync%2A> e <xref:System.IO.Stream.ReadAsync%2A>, è possibile specificare uno struct <xref:System.Threading.CancellationToken>, che consente di annullare l'operazione nel corso del flusso. Per altre informazioni, vedere [ottimizzazione dell'applicazione asincrona (Visual Basic)](fine-tuning-your-async-application.md) e [annullamento nei thread gestiti](../../../../standard/threading/cancellation-in-managed-threads.md).  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona con Async e Await (Visual Basic)](index.md)
- [Tipi restituiti asincroni (Visual Basic)](async-return-types.md)
- [Flusso di controllo in programmi asincroni (Visual Basic)](control-flow-in-async-programs.md)
