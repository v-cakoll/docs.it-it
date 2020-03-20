---
title: 'Procedura: inviare dati utilizzando la classe WebRequest'
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 2467b289df7a0361b51ad91d4458d32742c42275
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70040825"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a><span data-ttu-id="7bb58-102">Procedura: inviare dati utilizzando la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="7bb58-102">How to: Send data by using the WebRequest class</span></span>

<span data-ttu-id="7bb58-103">La procedura seguente descrive i passaggi per inviare dati a un server.</span><span class="sxs-lookup"><span data-stu-id="7bb58-103">The following procedure describes the steps to send data to a server.</span></span> <span data-ttu-id="7bb58-104">Questa procedura viene comunemente usata per pubblicare dati in una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="7bb58-104">This procedure is commonly used to post data to a Web page.</span></span>

## <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="7bb58-105">Per inviare dati a un server host</span><span class="sxs-lookup"><span data-stu-id="7bb58-105">To send data to a host server</span></span>

1. <span data-ttu-id="7bb58-106">Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con l'URI di una risorsa che accetta dati, come ad esempio uno script o una pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7bb58-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource, such as a script or ASP.NET page, that accepts data.</span></span> <span data-ttu-id="7bb58-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")
    ```

    > [!NOTE]
    > <span data-ttu-id="7bb58-108">.NET Framework offre le classi specifiche del protocollo derivate dalle classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> per gli URI che iniziano con *http:*, *https:*, *ftp:* e *file:*.</span><span class="sxs-lookup"><span data-stu-id="7bb58-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="7bb58-109">Se è necessario impostare o eseguire la lettura di proprietà specifiche del protocollo, è necessario eseguire il cast dell'oggetto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> su un tipo di oggetto specifico del protocollo.</span><span class="sxs-lookup"><span data-stu-id="7bb58-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="7bb58-110">Per altre informazioni, vedere [Programmazione di protocolli di collegamento](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="7bb58-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="7bb58-111">Impostare i valori di proprietà necessari nell'oggetto `WebRequest`.</span><span class="sxs-lookup"><span data-stu-id="7bb58-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="7bb58-112">Per abilitare l'autenticazione, ad esempio, impostare la proprietà <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> su un'istanza della classe <xref:System.Net.NetworkCredential>:</span><span class="sxs-lookup"><span data-stu-id="7bb58-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="7bb58-113">Specificare un metodo di protocollo che consente l'invio dei dati con una richiesta, ad esempio il metodo `POST` HTTP:</span><span class="sxs-lookup"><span data-stu-id="7bb58-113">Specify a protocol method that permits data to be sent with a request, such as the HTTP `POST` method:</span></span>

    ```csharp
    request.Method = "POST";
    ```

    ```vb
    request.Method = "POST"
    ```

4. <span data-ttu-id="7bb58-114">Impostare la proprietà <xref:System.Web.HttpRequest.ContentLength> sul numero di byte inclusi nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="7bb58-114">Set the <xref:System.Web.HttpRequest.ContentLength> property to the number of bytes you're including with your request.</span></span> <span data-ttu-id="7bb58-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-115">For example:</span></span>

    ```csharp
    request.ContentLength = byteArray.Length;
    ```

    ```vb
    request.ContentLength = byteArray.Length
    ```

5. <span data-ttu-id="7bb58-116">Impostare la proprietà <xref:System.Web.HttpRequest.ContentType> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="7bb58-116">Set the <xref:System.Web.HttpRequest.ContentType> property to an appropriate value.</span></span> <span data-ttu-id="7bb58-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-117">For example:</span></span>

    ```csharp
    request.ContentType = "application/x-www-form-urlencoded";
    ```

    ```vb
    request.ContentType = "application/x-www-form-urlencoded"
    ```

6. <span data-ttu-id="7bb58-118">Ottenere il flusso che contiene i dati della richiesta chiamando il metodo <xref:System.Net.WebRequest.GetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="7bb58-118">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span> <span data-ttu-id="7bb58-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-119">For example:</span></span>

    ```csharp
    Stream dataStream = request.GetRequestStream();
    ```

    ```vb
    Dim dataStream As Stream = request.GetRequestStream()
    ```

7. <span data-ttu-id="7bb58-120">Scrivere i dati nell'oggetto <xref:System.IO.Stream> restituito dal metodo `GetRequestStream`.</span><span class="sxs-lookup"><span data-stu-id="7bb58-120">Write the data to the <xref:System.IO.Stream> object returned by the `GetRequestStream` method.</span></span> <span data-ttu-id="7bb58-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-121">For example:</span></span>

    ```csharp
    dataStream.Write(byteArray, 0, byteArray.Length);
    ```

    ```vb
    dataStream.Write(byteArray, 0, byteArray.Length)
    ```

8. <span data-ttu-id="7bb58-122">Chiudere il flusso della richiesta chiamando il metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bb58-122">Close the request stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7bb58-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-123">For example:</span></span>

    ```csharp
    dataStream.Close();
    ```

    ```vb
    dataStream.Close()
    ```

9. <span data-ttu-id="7bb58-124">Inviare la richiesta al server chiamando <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bb58-124">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7bb58-125">Questo metodo restituisce un oggetto contenente la risposta del server.</span><span class="sxs-lookup"><span data-stu-id="7bb58-125">This method returns an object containing the server's response.</span></span> <span data-ttu-id="7bb58-126">Il tipo dell'oggetto `WebResponse` restituito viene determinato dallo schema dell'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="7bb58-126">The returned `WebResponse` object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="7bb58-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-127">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

10. <span data-ttu-id="7bb58-128">È possibile accedere alle proprietà dell'oggetto `WebResponse`oppure eseguirne il cast su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo.</span><span class="sxs-lookup"><span data-stu-id="7bb58-128">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="7bb58-129">Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast dell'oggetto `WebResponse` su un riferimento <xref:System.Net.HttpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="7bb58-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an <xref:System.Net.HttpWebResponse> reference.</span></span> <span data-ttu-id="7bb58-130">L'esempio di codice seguente illustra come visualizzare la proprietà <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> specifica di HTTP inviata con una risposta:</span><span class="sxs-lookup"><span data-stu-id="7bb58-130">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)
    ```

11. <span data-ttu-id="7bb58-131">Per ottenere il flusso contenente i dati di risposta inviati dal server, chiamare il metodo <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> dell'oggetto `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="7bb58-131">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method of your `WebResponse` object.</span></span> <span data-ttu-id="7bb58-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-132">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

12. <span data-ttu-id="7bb58-133">Dopo aver letto i dati dall'oggetto risposta, chiuderlo con il metodo <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> oppure chiudere il flusso della risposta con il metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bb58-133">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7bb58-134">Se non si chiude la risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare nuove richieste.</span><span class="sxs-lookup"><span data-stu-id="7bb58-134">If you don't close either the response or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="7bb58-135">Poiché il metodo `WebResponse.Close` chiama `Stream.Close` quando chiude la risposta, non è necessario chiamare `Close` sia sull'oggetto risposta che sul flusso, anche se tale operazione non crea problemi.</span><span class="sxs-lookup"><span data-stu-id="7bb58-135">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="7bb58-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bb58-136">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="7bb58-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bb58-137">Example</span></span>

<span data-ttu-id="7bb58-138">L'esempio seguente illustra come inviare dati a un server Web ed eseguire la lettura dei dati nella risposta:</span><span class="sxs-lookup"><span data-stu-id="7bb58-138">The following example shows how to send data to a web server and read the data in its response:</span></span>

[!code-csharp[SendDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/SendDataUsingWebRequest/cs/WebRequestPostExample.cs)]
[!code-vb[SendDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/SendDataUsingWebRequest/vb/WebRequestPostExample.vb)]

## <a name="see-also"></a><span data-ttu-id="7bb58-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bb58-139">See also</span></span>

- [<span data-ttu-id="7bb58-140">Creazione di richieste Internet</span><span class="sxs-lookup"><span data-stu-id="7bb58-140">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="7bb58-141">Utilizzo dei flussi in rete</span><span class="sxs-lookup"><span data-stu-id="7bb58-141">Using streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="7bb58-142">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="7bb58-142">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="7bb58-143">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="7bb58-143">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="7bb58-144">Procedura: richiedere dati utilizzando la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="7bb58-144">How to: Request data by using the WebRequest class</span></span>](how-to-request-data-using-the-webrequest-class.md)
