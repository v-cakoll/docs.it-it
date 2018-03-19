---
title: 'Procedura: Richiedere dati con la classe WebRequest'
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
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 463a59444d3f93e5560e149033fd845ac8cbe62d
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-request-data-using-the-webrequest-class"></a><span data-ttu-id="721d3-102">Procedura: Richiedere dati con la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="721d3-102">How to: Request Data Using the WebRequest Class</span></span>
<span data-ttu-id="721d3-103">La procedura seguente descrive i passaggi necessari per richiedere una risorsa da un server, ad esempio, una pagina Web o un file.</span><span class="sxs-lookup"><span data-stu-id="721d3-103">The following procedure describes the steps used to request a resource from a server, for example, a Web page or file.</span></span> <span data-ttu-id="721d3-104">La risorsa deve essere identificata da un URI.</span><span class="sxs-lookup"><span data-stu-id="721d3-104">The resource must be identified by a URI.</span></span>  
  
### <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="721d3-105">Per richiedere dati da un server host</span><span class="sxs-lookup"><span data-stu-id="721d3-105">To request data from a host server</span></span>  
  
1.  <span data-ttu-id="721d3-106">Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A> con l'URI della risorsa.</span><span class="sxs-lookup"><span data-stu-id="721d3-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="721d3-107">.NET Framework fornisce le classi specifiche del protocollo derivate da **WebRequest** e **WebResponse** per gli URI che iniziano con "http:", "https:", "ftp:" e "file:".</span><span class="sxs-lookup"><span data-stu-id="721d3-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="721d3-108">Per accedere alle risorse con altri protocolli, è necessario implementare classi specifiche del protocollo che derivano da **WebRequest** e **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="721d3-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="721d3-109">Per altre informazioni, vedere [Programmazione di protocolli di collegamento](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="721d3-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="721d3-110">Impostare i valori di proprietà necessari in **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="721d3-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="721d3-111">Per abilitare l'autenticazione, ad esempio, impostare la proprietà **Credentials** su un'istanza della classe <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="721d3-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="721d3-112">Nella maggior parte dei casi, la classe **WebRequest** è sufficiente per la ricezione di dati.</span><span class="sxs-lookup"><span data-stu-id="721d3-112">In most cases, the **WebRequest** class is sufficient to receive data.</span></span> <span data-ttu-id="721d3-113">Tuttavia, se è necessario impostare le proprietà specifiche del protocollo, è necessario eseguire il cast di **WebRequest** sul tipo specifico del protocollo.</span><span class="sxs-lookup"><span data-stu-id="721d3-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="721d3-114">Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebRequest>, eseguire il cast di **WebRequest** su un riferimento **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="721d3-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="721d3-115">L'esempio di codice seguente mostra come impostare la proprietà <xref:System.Net.HttpWebRequest.UserAgent%2A> specifica di HTTP.</span><span class="sxs-lookup"><span data-stu-id="721d3-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="721d3-116">Per inviare la richiesta al server, chiamare <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="721d3-116">To send the request to the server, call <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="721d3-117">Il tipo effettivo dell'oggetto **WebResponse** restituito è determinato dallo schema dell'URI richiesto.</span><span class="sxs-lookup"><span data-stu-id="721d3-117">The actual type of the returned **WebResponse** object is determined by the scheme of the requested URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="721d3-118">Dopo aver finito di usare un oggetto <xref:System.Net.WebResponse>, è necessario chiuderlo chiamando il metodo <xref:System.Net.WebResponse.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="721d3-118">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="721d3-119">In alternativa, se è stato usato il flusso di risposta dall'oggetto risposta, è possibile chiudere il flusso tramite la chiamata del metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="721d3-119">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="721d3-120">Se non si chiude la risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare ulteriori richieste.</span><span class="sxs-lookup"><span data-stu-id="721d3-120">If you do not close either the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
4.  <span data-ttu-id="721d3-121">È possibile accedere alle proprietà di **WebResponse** oppure eseguire il cast di **WebResponse** su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo.</span><span class="sxs-lookup"><span data-stu-id="721d3-121">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="721d3-122">Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast di **WebResponse** su un riferimento **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="721d3-122">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to a **HttpWebResponse** reference.</span></span> <span data-ttu-id="721d3-123">L'esempio di codice seguente mostra come visualizzare le informazioni sullo stato inviate con una risposta.</span><span class="sxs-lookup"><span data-stu-id="721d3-123">The following code example shows how to display the status information sent with a response.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  <span data-ttu-id="721d3-124">Per ottenere il flusso contenente i dati di risposta inviati dal server, usare il metodo <xref:System.Net.HttpWebResponse.GetResponseStream%2A> di **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="721d3-124">To get the stream containing response data sent by the server, use the <xref:System.Net.HttpWebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  <span data-ttu-id="721d3-125">Dopo la lettura dei dati dalla risposta, è necessario chiudere il flusso di risposta tramite il metodo **Stream.Close** oppure chiudere la risposta tramite il metodo **WebResponse.Close**.</span><span class="sxs-lookup"><span data-stu-id="721d3-125">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="721d3-126">Non è necessario chiamare il metodo **Close** sia sul flusso di risposta che su **WebResponse**, ma non si tratta di un'operazione che può causare danni.</span><span class="sxs-lookup"><span data-stu-id="721d3-126">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span> <span data-ttu-id="721d3-127">**WebResponse.Close** chiama **Stream.Close** alla chiusura della risposta.</span><span class="sxs-lookup"><span data-stu-id="721d3-127">**WebResponse.Close** calls **Stream.Close** when closing the response.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="721d3-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="721d3-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create(  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestGetExample  
  
        Public Shared Sub Main()  
            ' Create a request for the URL.   
            Dim request As WebRequest = _  
              WebRequest.Create("http://www.contoso.com/default.html")  
            ' If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            Dim dataStream As Stream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams and the response.  
            reader.Close()  
            response.Close()  
        End Sub   
    End Class   
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="721d3-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="721d3-129">See Also</span></span>  
 [<span data-ttu-id="721d3-130">Creazione di richieste Internet</span><span class="sxs-lookup"><span data-stu-id="721d3-130">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="721d3-131">Uso di flussi nella rete</span><span class="sxs-lookup"><span data-stu-id="721d3-131">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="721d3-132">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="721d3-132">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="721d3-133">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="721d3-133">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="721d3-134">Procedura: Inviare dati con la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="721d3-134">How to: Send Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
