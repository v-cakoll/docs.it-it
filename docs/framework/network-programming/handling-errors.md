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
# <a name="handling-errors"></a><span data-ttu-id="efe74-104">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="efe74-104">Handling Errors</span></span>

<span data-ttu-id="efe74-105">Entrambe le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> generano eccezioni di sistema (ad esempio <xref:System.ArgumentException>) ed eccezioni specifiche del Web (ovvero <xref:System.Net.WebException> generate dal metodo <xref:System.Net.WebRequest.GetResponse%2A>).</span><span class="sxs-lookup"><span data-stu-id="efe74-105">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
<span data-ttu-id="efe74-106">Ogni **WebException** include una proprietà <xref:System.Net.WebException.Status%2A> che contiene un valore dall'enumerazione <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="efe74-106">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="efe74-107">È possibile esaminare la proprietà **Status** per determinare l'errore che si è verificato e intervenire in modo appropriato per risolvere l'errore.</span><span class="sxs-lookup"><span data-stu-id="efe74-107">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
<span data-ttu-id="efe74-108">La tabella seguente descrive i possibili valori per la proprietà **Status**.</span><span class="sxs-lookup"><span data-stu-id="efe74-108">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="efe74-109">Stato</span><span class="sxs-lookup"><span data-stu-id="efe74-109">Status</span></span>|<span data-ttu-id="efe74-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efe74-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="efe74-111">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-111">ConnectFailure</span></span>|<span data-ttu-id="efe74-112">Non è stato possibile contattare il servizio remoto al livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="efe74-112">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="efe74-113">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="efe74-113">ConnectionClosed</span></span>|<span data-ttu-id="efe74-114">Chiusura imprevista della connessione.</span><span class="sxs-lookup"><span data-stu-id="efe74-114">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="efe74-115">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-115">KeepAliveFailure</span></span>|<span data-ttu-id="efe74-116">Il server ha chiuso una connessione effettuata con l'intestazione Keep-alive impostata.</span><span class="sxs-lookup"><span data-stu-id="efe74-116">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="efe74-117">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-117">NameResolutionFailure</span></span>|<span data-ttu-id="efe74-118">Il servizio dei nomi non è riuscito a risolvere il nome host.</span><span class="sxs-lookup"><span data-stu-id="efe74-118">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="efe74-119">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="efe74-119">ProtocolError</span></span>|<span data-ttu-id="efe74-120">La risposta ricevuta dal server era completa ma indicava un errore a livello di protocollo.</span><span class="sxs-lookup"><span data-stu-id="efe74-120">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="efe74-121">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-121">ReceiveFailure</span></span>|<span data-ttu-id="efe74-122">Il server remoto non ha ricevuto una risposta completa.</span><span class="sxs-lookup"><span data-stu-id="efe74-122">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="efe74-123">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="efe74-123">RequestCanceled</span></span>|<span data-ttu-id="efe74-124">La richiesta è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="efe74-124">The request was canceled.</span></span>|  
|<span data-ttu-id="efe74-125">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-125">SecureChannelFailure</span></span>|<span data-ttu-id="efe74-126">Si è verificato un errore in un collegamento a un canale sicuro.</span><span class="sxs-lookup"><span data-stu-id="efe74-126">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="efe74-127">SendFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-127">SendFailure</span></span>|<span data-ttu-id="efe74-128">Non è stato possibile inviare una richiesta completa al server remoto.</span><span class="sxs-lookup"><span data-stu-id="efe74-128">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="efe74-129">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="efe74-129">ServerProtocolViolation</span></span>|<span data-ttu-id="efe74-130">La risposta dal server non era una risposta HTTP valida.</span><span class="sxs-lookup"><span data-stu-id="efe74-130">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="efe74-131">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="efe74-131">Success</span></span>|<span data-ttu-id="efe74-132">Nessun errore riscontrato.</span><span class="sxs-lookup"><span data-stu-id="efe74-132">No error was encountered.</span></span>|  
|<span data-ttu-id="efe74-133">Timeout</span><span class="sxs-lookup"><span data-stu-id="efe74-133">Timeout</span></span>|<span data-ttu-id="efe74-134">Non è stata ricevuta alcuna risposta entro il timeout impostato per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="efe74-134">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="efe74-135">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-135">TrustFailure</span></span>|<span data-ttu-id="efe74-136">Non è stato possibile convalidare un certificato del server.</span><span class="sxs-lookup"><span data-stu-id="efe74-136">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="efe74-137">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="efe74-137">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="efe74-138">È stato ricevuto un messaggio che supera il limite specificato durante l'invio di una richiesta o la ricezione di una risposta dal server.</span><span class="sxs-lookup"><span data-stu-id="efe74-138">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="efe74-139">Pending</span><span class="sxs-lookup"><span data-stu-id="efe74-139">Pending</span></span>|<span data-ttu-id="efe74-140">Una richiesta asincrona interna è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="efe74-140">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="efe74-141">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-141">PipelineFailure</span></span>|<span data-ttu-id="efe74-142">Questo valore supporta l'infrastruttura .NET Framework e non è possibile usarlo direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="efe74-142">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="efe74-143">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="efe74-143">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="efe74-144">Il servizio di risoluzione dei nomi non è riuscito a risolvere il nome host del proxy.</span><span class="sxs-lookup"><span data-stu-id="efe74-144">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="efe74-145">UnknownError</span><span class="sxs-lookup"><span data-stu-id="efe74-145">UnknownError</span></span>|<span data-ttu-id="efe74-146">Si è verificata un'eccezione di tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="efe74-146">An exception of unknown type has occurred.</span></span>|  
  
<span data-ttu-id="efe74-147">Quando la proprietà **Status** è **WebExceptionStatus.ProtocolError**, è disponibile un oggetto **WebResponse** che contiene la risposta dal server.</span><span class="sxs-lookup"><span data-stu-id="efe74-147">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="efe74-148">È possibile esaminare questa risposta per stabilire l'origine effettiva dell'errore del protocollo.</span><span class="sxs-lookup"><span data-stu-id="efe74-148">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
<span data-ttu-id="efe74-149">L'esempio seguente mostra come intercettare una **WebException**.</span><span class="sxs-lookup"><span data-stu-id="efe74-149">The following example shows how to catch a **WebException**.</span></span>  
  
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
  
<span data-ttu-id="efe74-150">Le applicazioni che usano la classe <xref:System.Net.Sockets.Socket> generano <xref:System.Net.Sockets.SocketException> quando si verificano errori sul socket di Windows.</span><span class="sxs-lookup"><span data-stu-id="efe74-150">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="efe74-151">Le classi <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> e <xref:System.Net.Sockets.UdpClient> sono basate sulla classe **Socket** e anch'esse generano **SocketException**.</span><span class="sxs-lookup"><span data-stu-id="efe74-151">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
<span data-ttu-id="efe74-152">Quando viene generata una **SocketException**, la classe **SocketException** imposta la proprietà <xref:System.Net.Sockets.SocketException.ErrorCode%2A> sull'ultimo errore relativo a un socket del sistema operativo che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="efe74-152">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="efe74-153">Per altre informazioni sui codici di errore di socket, vedere la documentazione dei codici di errore dell'API Winsock 2.0 in MSDN.</span><span class="sxs-lookup"><span data-stu-id="efe74-153">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe74-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efe74-154">See also</span></span>

- [<span data-ttu-id="efe74-155">Gestione e generazione di eccezioni in .NET</span><span class="sxs-lookup"><span data-stu-id="efe74-155">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="efe74-156">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="efe74-156">Requesting Data</span></span>](requesting-data.md)
