---
title: Uso di flussi nella rete
description: Il .NET Framework rappresenta le risorse di rete come flussi. La classe NetworkStream implementa la classe Stream da usare con le risorse di rete.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, streams
- Networking
- response to Internet request, streams
- network resources, stream capabilities
- receiving data, stream capabilities
- Network Resources
- sending data, stream capabilities
- downloading Internet resources, streams
- streams, capabilities
- Internet, streams
- streams
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
ms.openlocfilehash: f8d35b43c9b46a77bfd0c78f7d0118093b6fe824
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501976"
---
# <a name="using-streams-on-the-network"></a><span data-ttu-id="e611c-104">Uso di flussi nella rete</span><span class="sxs-lookup"><span data-stu-id="e611c-104">Using Streams on the Network</span></span>
<span data-ttu-id="e611c-105">Le risorse di rete sono rappresentate in .NET Framework come flussi.</span><span class="sxs-lookup"><span data-stu-id="e611c-105">Network resources are represented in the .NET Framework as streams.</span></span> <span data-ttu-id="e611c-106">Grazie alla possibilità di gestire i flussi in modo generico, .NET Framework offre le opportunità seguenti:</span><span class="sxs-lookup"><span data-stu-id="e611c-106">By treating streams generically, the .NET Framework offers the following capabilities:</span></span>  
  
- <span data-ttu-id="e611c-107">Un modo comune per inviare e ricevere dati Web.</span><span class="sxs-lookup"><span data-stu-id="e611c-107">A common way to send and receive Web data.</span></span> <span data-ttu-id="e611c-108">Indipendentemente dal contenuto effettivo del file (HTML, XML o altro) l'applicazione userà <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> e <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> per inviare e ricevere dati.</span><span class="sxs-lookup"><span data-stu-id="e611c-108">Whatever the actual contents of the file — HTML, XML, or anything else — your application will use <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> and <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> to send and receive data.</span></span>  
  
- <span data-ttu-id="e611c-109">Compatibilità con i flussi in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e611c-109">Compatibility with streams across the .NET Framework.</span></span> <span data-ttu-id="e611c-110">I flussi vengono usati in tutte le parti di .NET Framework, che offre un'infrastruttura avanzata per gestirli.</span><span class="sxs-lookup"><span data-stu-id="e611c-110">Streams are used throughout the .NET Framework, which has a rich infrastructure for handling them.</span></span> <span data-ttu-id="e611c-111">Ad esempio, è possibile modificare un'applicazione che legge dati XML da un <xref:System.IO.FileStream> in modo che legga invece i dati da un <xref:System.Net.Sockets.NetworkStream> modificando solo le poche righe di codice che inizializzano il flusso.</span><span class="sxs-lookup"><span data-stu-id="e611c-111">For example, you can modify an application that reads XML data from a <xref:System.IO.FileStream> to read data from a <xref:System.Net.Sockets.NetworkStream> instead by changing only the few lines of code that initialize the stream.</span></span> <span data-ttu-id="e611c-112">Le differenze principali tra la classe **NetworkStream** e gli altri flussi sono che **NetworkStream** non supporta la ricerca, la proprietà <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> restituisce sempre **false** e i metodi <xref:System.Net.Sockets.NetworkStream.Seek%2A> e <xref:System.Net.Sockets.NetworkStream.Position%2A> generano <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="e611c-112">The major differences between the **NetworkStream** class and other streams are that **NetworkStream** is not seekable, the <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> property always returns **false**, and the <xref:System.Net.Sockets.NetworkStream.Seek%2A> and <xref:System.Net.Sockets.NetworkStream.Position%2A> methods throw a <xref:System.NotSupportedException>.</span></span>  
  
- <span data-ttu-id="e611c-113">Elaborazione dei dati all'arrivo.</span><span class="sxs-lookup"><span data-stu-id="e611c-113">Processing of data as it arrives.</span></span> <span data-ttu-id="e611c-114">I flussi consentono l'accesso ai dati non appena arrivano dalla rete, anziché imporre a un'applicazione di attendere il completamento del download dell'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="e611c-114">Streams provide access to data as it arrives from the network, rather than forcing your application to wait for an entire data set to be downloaded.</span></span>  
  
 <span data-ttu-id="e611c-115">Lo spazio dei nomi <xref:System.Net.Sockets> contiene una classe **NetworkStream** che implementa la classe <xref:System.IO.Stream> appositamente per l'uso con le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="e611c-115">The <xref:System.Net.Sockets> namespace contains a **NetworkStream** class that implements the <xref:System.IO.Stream> class specifically for use with network resources.</span></span> <span data-ttu-id="e611c-116">Le classi nello spazio dei nomi <xref:System.Net.Sockets> usano la classe **NetworkStream** per rappresentare i flussi.</span><span class="sxs-lookup"><span data-stu-id="e611c-116">Classes in the <xref:System.Net.Sockets> namespace use the **NetworkStream** class to represent streams.</span></span>  
  
 <span data-ttu-id="e611c-117">Per inviare dati alla rete usando il flusso restituito, chiamare <xref:System.Net.WebRequest.GetRequestStream%2A> su <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="e611c-117">To send data to the network using the returned stream, call <xref:System.Net.WebRequest.GetRequestStream%2A> on your <xref:System.Net.WebRequest>.</span></span> <span data-ttu-id="e611c-118">**WebRequest** invierà le intestazioni della richiesta al server. è quindi possibile inviare i dati alla risorsa di rete chiamando il <xref:System.IO.Stream.BeginWrite%2A> <xref:System.IO.Stream.EndWrite%2A> metodo, o <xref:System.IO.Stream.Write%2A> sul flusso restituito.</span><span class="sxs-lookup"><span data-stu-id="e611c-118">The **WebRequest** will send request headers to the server; then you can send data to the network resource by calling the <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A>, or <xref:System.IO.Stream.Write%2A> method on the returned stream.</span></span> <span data-ttu-id="e611c-119">Alcuni protocolli, ad esempio HTTP, potrebbero richiedere di impostare proprietà specifiche del protocollo prima di inviare dati.</span><span class="sxs-lookup"><span data-stu-id="e611c-119">Some protocols, such as HTTP, may require you to set protocol-specific properties before sending data.</span></span> <span data-ttu-id="e611c-120">L'esempio di codice seguente illustra come impostare le proprietà specifiche di HTTP per l'invio dei dati.</span><span class="sxs-lookup"><span data-stu-id="e611c-120">The following code example shows how to set HTTP-specific properties for sending data.</span></span> <span data-ttu-id="e611c-121">Presuppone che la variabile `sendData` contenga i dati da inviare e che la variabile `sendLength` corrisponda al numero di byte di dati da inviare.</span><span class="sxs-lookup"><span data-stu-id="e611c-121">It assumes that the variable `sendData` contains the data to send and that the variable `sendLength` is the number of bytes of data to send.</span></span>  
  
```csharp  
HttpWebRequest request =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 <span data-ttu-id="e611c-122">Per ricevere dati dalla rete, chiamare <xref:System.Net.WebResponse.GetResponseStream%2A> su <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="e611c-122">To receive data from the network, call <xref:System.Net.WebResponse.GetResponseStream%2A> on your <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="e611c-123">È quindi possibile leggere dati dalla risorsa di rete tramite la chiamata del metodo <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> o <xref:System.IO.Stream.Read%2A> sul flusso restituito.</span><span class="sxs-lookup"><span data-stu-id="e611c-123">You can then read data from the network resource by calling the <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A>, or <xref:System.IO.Stream.Read%2A> method on the returned stream.</span></span>  
  
 <span data-ttu-id="e611c-124">Quando si usano flussi dalle risorse di rete, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e611c-124">When using streams from network resources, keep in mind the following points:</span></span>  
  
- <span data-ttu-id="e611c-125">La proprietà **CanSeek** restituisce sempre **false** perché la classe **NetworkStream** non può cambiare posizione nel flusso.</span><span class="sxs-lookup"><span data-stu-id="e611c-125">The **CanSeek** property always returns **false** since the **NetworkStream** class cannot change position in the stream.</span></span> <span data-ttu-id="e611c-126">I metodi **Seek** e **Position** generano **NotSupportedException**.</span><span class="sxs-lookup"><span data-stu-id="e611c-126">The **Seek** and **Position** methods throw a **NotSupportedException**.</span></span>  
  
- <span data-ttu-id="e611c-127">Quando si usa **WebRequest** e **WebResponse**, le istanze del flusso create chiamando **GetResponseStream** sono di sola lettura e quelle create chiamando **GetRequestStream** sono di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="e611c-127">When you use **WebRequest** and **WebResponse**, stream instances created by calling **GetResponseStream** are read-only and stream instances created by calling **GetRequestStream** are write-only.</span></span>  
  
- <span data-ttu-id="e611c-128">Usare la classe <xref:System.IO.StreamReader> per facilitare la codifica.</span><span class="sxs-lookup"><span data-stu-id="e611c-128">Use the <xref:System.IO.StreamReader> class to make encoding easier.</span></span> <span data-ttu-id="e611c-129">L'esempio di codice seguente illustra come usare **StreamReader** per leggere un flusso con codifica ASCII da una **WebResponse** (l'esempio non include la creazione della richiesta).</span><span class="sxs-lookup"><span data-stu-id="e611c-129">The following code example uses a **StreamReader** to read an ASCII-encoded stream from a **WebResponse** (the example does not show creating the request).</span></span>  
  
- <span data-ttu-id="e611c-130">La chiamata a **GetResponse** può bloccarsi se non sono disponibili risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="e611c-130">The call to **GetResponse** can block if network resources are not available.</span></span> <span data-ttu-id="e611c-131">È consigliabile prendere in considerazione l'uso di una richiesta asincrona con i metodi <xref:System.Net.WebRequest.BeginGetResponse%2A> e <xref:System.Net.WebRequest.EndGetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="e611c-131">You should consider using an asynchronous request with the <xref:System.Net.WebRequest.BeginGetResponse%2A> and <xref:System.Net.WebRequest.EndGetResponse%2A> methods.</span></span>  
  
- <span data-ttu-id="e611c-132">La chiamata a **GetRequestStream** può bloccarsi mentre viene creata la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="e611c-132">The call to **GetRequestStream** can block while the connection to the server is created.</span></span> <span data-ttu-id="e611c-133">È consigliabile prendere in considerazione l'uso di una richiesta asincrona per il flusso con i metodi <xref:System.Net.WebRequest.BeginGetRequestStream%2A> e <xref:System.Net.WebRequest.EndGetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="e611c-133">You should consider using an asynchronous request for the stream with the <xref:System.Net.WebRequest.BeginGetRequestStream%2A> and <xref:System.Net.WebRequest.EndGetRequestStream%2A> methods.</span></span>  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e611c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e611c-134">See also</span></span>

- [<span data-ttu-id="e611c-135">Procedura: Richiedere dati con la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="e611c-135">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="e611c-136">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="e611c-136">Requesting Data</span></span>](requesting-data.md)
