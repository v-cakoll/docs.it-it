---
title: Gestione degli errori
description: Informazioni sulle eccezioni specifiche del sistema e del Web generate da WebRequest e WebResponse. Utilizzare la proprietà Status per comprendere e risolvere il problema.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, WebRequest and WebResponse classes exceptions
- Status property
- WebExceptions class, about WebExceptions class
- Timeout enumeration member
- ConnectFailure enumeration member
- TrustFailure enumeration member
- WebRequest class, exceptions
- requesting data from Internet, error handling
- Success enumeration member
- receiving data, errors
- ProtocolError enumeration member
- downloading Internet resources, error handling
- WebResponse class, exceptions
- SendFailure enumeration member
- errors [.NET Framework], WebRequest and WebResponse classes exceptions
- sending data, errors
- response to Internet request, error handling
- NameResolutionFailure enumeration member
- KeepAliveFailure enumeration member
- network resources, WebRequest and WebResponse classes exceptions
- RequestCanceled enumeration member
- ReceiveFailure enumeration member
- ServerProtocolViolation enumeration member
- ConnectionClosed enumeration member
- SecureChannelFailure enumeration member
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
ms.openlocfilehash: 786b2bd8bc4d1b394bcfe920053b2f4f55d1cdea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502574"
---
# <a name="handling-errors"></a>Gestione degli errori

Entrambe le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> generano eccezioni di sistema (ad esempio <xref:System.ArgumentException>) ed eccezioni specifiche del Web (ovvero <xref:System.Net.WebException> generate dal metodo <xref:System.Net.WebRequest.GetResponse%2A>).  
  
Ogni **WebException** include una proprietà <xref:System.Net.WebException.Status%2A> che contiene un valore dall'enumerazione <xref:System.Net.WebExceptionStatus>. È possibile esaminare la proprietà **Status** per determinare l'errore che si è verificato e intervenire in modo appropriato per risolvere l'errore.  
  
La tabella seguente descrive i possibili valori per la proprietà **Status**.  
  
|Stato|Descrizione|  
|------------|-----------------|  
|ConnectFailure|Non è stato possibile contattare il servizio remoto al livello di trasporto.|  
|ConnectionClosed|Chiusura imprevista della connessione.|  
|KeepAliveFailure|Il server ha chiuso una connessione effettuata con l'intestazione Keep-alive impostata.|  
|NameResolutionFailure|Il servizio dei nomi non è riuscito a risolvere il nome host.|  
|ProtocolError|La risposta ricevuta dal server era completa ma indicava un errore a livello di protocollo.|  
|ReceiveFailure|Il server remoto non ha ricevuto una risposta completa.|  
|RequestCanceled|La richiesta è stata annullata.|  
|SecureChannelFailure|Si è verificato un errore in un collegamento a un canale sicuro.|  
|SendFailure|Non è stato possibile inviare una richiesta completa al server remoto.|  
|ServerProtocolViolation|La risposta dal server non era una risposta HTTP valida.|  
|Operazione completata|Nessun errore riscontrato.|  
|Timeout|Non è stata ricevuta alcuna risposta entro il timeout impostato per la richiesta.|  
|TrustFailure|Non è stato possibile convalidare un certificato del server.|  
|MessageLengthLimitExceeded|È stato ricevuto un messaggio che supera il limite specificato durante l'invio di una richiesta o la ricezione di una risposta dal server.|  
|Pending|Una richiesta asincrona interna è in sospeso.|  
|PipelineFailure|Questo valore supporta l'infrastruttura .NET Framework e non è possibile usarlo direttamente nel codice.|  
|ProxyNameResolutionFailure|Il servizio di risoluzione dei nomi non è riuscito a risolvere il nome host del proxy.|  
|UnknownError|Si è verificata un'eccezione di tipo sconosciuto.|  
  
Quando la proprietà **Status** è **WebExceptionStatus.ProtocolError**, è disponibile un oggetto **WebResponse** che contiene la risposta dal server. È possibile esaminare questa risposta per stabilire l'origine effettiva dell'errore del protocollo.  
  
L'esempio seguente mostra come intercettare una **WebException**.  
  
```csharp  
try
{  
    // Create a request instance.  
    WebRequest myRequest =
    WebRequest.Create("http://www.contoso.com");  
    // Get the response.  
    WebResponse myResponse = myRequest.GetResponse();  
    //Get a readable stream from the server.
    Stream sr = myResponse.GetResponseStream();  
  
    //Read from the stream and write any data to the console.  
    bytesread = sr.Read( myBuffer, 0, length);  
    while( bytesread > 0 )
    {  
        for (int i=0; i<bytesread; i++) {  
            Console.Write( "{0}", myBuffer[i]);  
        }  
        Console.WriteLine();  
        bytesread = sr.Read( myBuffer, 0, length);  
    }  
    sr.Close();  
    myResponse.Close();  
}  
catch (WebException webExcp)
{  
    // If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.");  
    // Write out the WebException message.  
    Console.WriteLine(webExcp.ToString());  
    // Get the WebException status code.  
    WebExceptionStatus status =  webExcp.Status;  
    // If status is WebExceptionStatus.ProtocolError,
    //   there has been a protocol error and a WebResponse
    //   should exist. Display the protocol error.  
    if (status == WebExceptionStatus.ProtocolError) {  
        Console.Write("The server returned protocol error ");  
        // Get HttpWebResponse so that you can check the HTTP status code.  
        HttpWebResponse httpResponse = (HttpWebResponse)webExcp.Response;  
        Console.WriteLine((int)httpResponse.StatusCode + " - "  
           + httpResponse.StatusCode);  
    }  
}  
catch (Exception e)
{  
    // Code to catch other exceptions goes here.  
}  
```  
  
```vb  
Try  
    ' Create a request instance.  
    Dim myRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ' Get the response.  
    Dim myResponse As WebResponse = myRequest.GetResponse()  
    'Get a readable stream from the server.
    Dim sr As Stream = myResponse.GetResponseStream()  
  
    Dim i As Integer
    'Read from the stream and write any data to the console.  
    bytesread = sr.Read(myBuffer, 0, length)  
    While bytesread > 0  
        For i = 0 To bytesread - 1  
            Console.Write("{0}", myBuffer(i))  
        Next i  
        Console.WriteLine()  
        bytesread = sr.Read(myBuffer, 0, length)  
    End While  
    sr.Close()  
    myResponse.Close()  
Catch webExcp As WebException  
    ' If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.")  
    ' Write out the WebException message.  
    Console.WriteLine(webExcp.ToString())  
    ' Get the WebException status code.  
    Dim status As WebExceptionStatus = webExcp.Status  
    ' If status is WebExceptionStatus.ProtocolError,
    '   there has been a protocol error and a WebResponse
    '   should exist. Display the protocol error.  
    If status = WebExceptionStatus.ProtocolError Then  
        Console.Write("The server returned protocol error ")  
        ' Get HttpWebResponse so that you can check the HTTP status code.  
        Dim httpResponse As HttpWebResponse = _  
           CType(webExcp.Response, HttpWebResponse)  
        Console.WriteLine(CInt(httpResponse.StatusCode).ToString() & _  
           " - " & httpResponse.StatusCode.ToString())  
    End If  
Catch e As Exception  
    ' Code to catch other exceptions goes here.  
End Try  
```  
  
Le applicazioni che usano la classe <xref:System.Net.Sockets.Socket> generano <xref:System.Net.Sockets.SocketException> quando si verificano errori sul socket di Windows. Le classi <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> e <xref:System.Net.Sockets.UdpClient> sono basate sulla classe **Socket** e anch'esse generano **SocketException**.  
  
Quando viene generata una **SocketException**, la classe **SocketException** imposta la proprietà <xref:System.Net.Sockets.SocketException.ErrorCode%2A> sull'ultimo errore relativo a un socket del sistema operativo che si è verificato. Per altre informazioni sui codici di errore di socket, vedere la documentazione dei codici di errore dell'API Winsock 2.0 in MSDN.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione e generazione di eccezioni in .NET](../../standard/exceptions/index.md)
- [Richiesta di dati](requesting-data.md)
