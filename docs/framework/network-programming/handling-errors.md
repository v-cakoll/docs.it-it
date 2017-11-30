---
title: Gestione degli errori
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: aad78fb509f98a01b5ca072ad476d901fdd1d4d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="handling-errors"></a><span data-ttu-id="a1ffc-102">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="a1ffc-102">Handling Errors</span></span>
<span data-ttu-id="a1ffc-103">Entrambe le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> generano eccezioni di sistema (ad esempio <xref:System.ArgumentException>) ed eccezioni specifiche del Web (ovvero <xref:System.Net.WebException> generate dal metodo <xref:System.Net.WebRequest.GetResponse%2A>).</span><span class="sxs-lookup"><span data-stu-id="a1ffc-103">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
 <span data-ttu-id="a1ffc-104">Ogni **WebException** include una proprietà <xref:System.Net.WebException.Status%2A> che contiene un valore dall'enumerazione <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-104">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="a1ffc-105">È possibile esaminare la proprietà **Status** per determinare l'errore che si è verificato e intervenire in modo appropriato per risolvere l'errore.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-105">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
 <span data-ttu-id="a1ffc-106">La tabella seguente descrive i possibili valori per la proprietà **Status**.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-106">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="a1ffc-107">Status</span><span class="sxs-lookup"><span data-stu-id="a1ffc-107">Status</span></span>|<span data-ttu-id="a1ffc-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1ffc-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a1ffc-109">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-109">ConnectFailure</span></span>|<span data-ttu-id="a1ffc-110">Non è stato possibile contattare il servizio remoto al livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-110">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="a1ffc-111">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="a1ffc-111">ConnectionClosed</span></span>|<span data-ttu-id="a1ffc-112">Chiusura imprevista della connessione.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-112">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="a1ffc-113">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-113">KeepAliveFailure</span></span>|<span data-ttu-id="a1ffc-114">Il server ha chiuso una connessione effettuata con l'intestazione Keep-alive impostata.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-114">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="a1ffc-115">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-115">NameResolutionFailure</span></span>|<span data-ttu-id="a1ffc-116">Il servizio dei nomi non è riuscito a risolvere il nome host.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-116">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="a1ffc-117">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="a1ffc-117">ProtocolError</span></span>|<span data-ttu-id="a1ffc-118">La risposta ricevuta dal server era completa ma indicava un errore a livello di protocollo.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-118">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="a1ffc-119">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-119">ReceiveFailure</span></span>|<span data-ttu-id="a1ffc-120">Il server remoto non ha ricevuto una risposta completa.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-120">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="a1ffc-121">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="a1ffc-121">RequestCanceled</span></span>|<span data-ttu-id="a1ffc-122">La richiesta è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-122">The request was canceled.</span></span>|  
|<span data-ttu-id="a1ffc-123">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-123">SecureChannelFailure</span></span>|<span data-ttu-id="a1ffc-124">Si è verificato un errore in un collegamento a un canale sicuro.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-124">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="a1ffc-125">SendFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-125">SendFailure</span></span>|<span data-ttu-id="a1ffc-126">Non è stato possibile inviare una richiesta completa al server remoto.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-126">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="a1ffc-127">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="a1ffc-127">ServerProtocolViolation</span></span>|<span data-ttu-id="a1ffc-128">La risposta dal server non era una risposta HTTP valida.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-128">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="a1ffc-129">Riuscito</span><span class="sxs-lookup"><span data-stu-id="a1ffc-129">Success</span></span>|<span data-ttu-id="a1ffc-130">Nessun errore riscontrato.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-130">No error was encountered.</span></span>|  
|<span data-ttu-id="a1ffc-131">Timeout</span><span class="sxs-lookup"><span data-stu-id="a1ffc-131">Timeout</span></span>|<span data-ttu-id="a1ffc-132">Non è stata ricevuta alcuna risposta entro il timeout impostato per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-132">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="a1ffc-133">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-133">TrustFailure</span></span>|<span data-ttu-id="a1ffc-134">Non è stato possibile convalidare un certificato del server.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-134">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="a1ffc-135">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="a1ffc-135">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="a1ffc-136">È stato ricevuto un messaggio che supera il limite specificato durante l'invio di una richiesta o la ricezione di una risposta dal server.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-136">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="a1ffc-137">In sospeso</span><span class="sxs-lookup"><span data-stu-id="a1ffc-137">Pending</span></span>|<span data-ttu-id="a1ffc-138">Una richiesta asincrona interna è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-138">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="a1ffc-139">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-139">PipelineFailure</span></span>|<span data-ttu-id="a1ffc-140">Questo valore supporta l'infrastruttura .NET Framework e non è possibile usarlo direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-140">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="a1ffc-141">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="a1ffc-141">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="a1ffc-142">Il servizio di risoluzione dei nomi non è riuscito a risolvere il nome host del proxy.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-142">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="a1ffc-143">UnknownError</span><span class="sxs-lookup"><span data-stu-id="a1ffc-143">UnknownError</span></span>|<span data-ttu-id="a1ffc-144">Si è verificata un'eccezione di tipo sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-144">An exception of unknown type has occurred.</span></span>|  
  
 <span data-ttu-id="a1ffc-145">Quando la proprietà **Status** è **WebExceptionStatus.ProtocolError**, è disponibile un oggetto **WebResponse** che contiene la risposta dal server.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-145">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="a1ffc-146">È possibile esaminare questa risposta per stabilire l'origine effettiva dell'errore del protocollo.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-146">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
 <span data-ttu-id="a1ffc-147">L'esempio seguente mostra come intercettare una **WebException**.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-147">The following example shows how to catch a **WebException**.</span></span>  
  
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
  
 <span data-ttu-id="a1ffc-148">Le applicazioni che usano la classe <xref:System.Net.Sockets.Socket> generano <xref:System.Net.Sockets.SocketException> quando si verificano errori sul socket di Windows.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-148">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="a1ffc-149">Le classi <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> e <xref:System.Net.Sockets.UdpClient> sono basate sulla classe **Socket** e anch'esse generano **SocketException**.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-149">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
 <span data-ttu-id="a1ffc-150">Quando viene generata una **SocketException**, la classe **SocketException** imposta la proprietà <xref:System.Net.Sockets.SocketException.ErrorCode%2A> sull'ultimo errore relativo a un socket del sistema operativo che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-150">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="a1ffc-151">Per altre informazioni sui codici di errore di socket, vedere la documentazione dei codici di errore dell'API Winsock 2.0 in MSDN.</span><span class="sxs-lookup"><span data-stu-id="a1ffc-151">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ffc-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1ffc-152">See Also</span></span>  
 [<span data-ttu-id="a1ffc-153">Nozioni fondamentali sulla gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="a1ffc-153">Exception Handling Fundamentals</span></span>](../../../docs/standard/exceptions/exception-handling-fundamentals.md)  
 [<span data-ttu-id="a1ffc-154">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="a1ffc-154">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
