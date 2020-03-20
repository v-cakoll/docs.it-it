---
title: 'Procedura: richiedere dati utilizzando la classe WebRequest'
ms.date: 03/21/2019
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
ms.openlocfilehash: e670a2a503ce704eff847e9e0b3ee340ab52fe62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048159"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="40834-102">Procedura: richiedere dati utilizzando la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="40834-102">How to: Request data by using the WebRequest class</span></span>

<span data-ttu-id="40834-103">La procedura seguente descrive i passaggi per richiedere una risorsa da un server, ad esempio una pagina Web o un file.</span><span class="sxs-lookup"><span data-stu-id="40834-103">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="40834-104">La risorsa deve essere identificata da un URI.</span><span class="sxs-lookup"><span data-stu-id="40834-104">The resource must be identified by a URI.</span></span>

## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="40834-105">Per richiedere dati da un server host</span><span class="sxs-lookup"><span data-stu-id="40834-105">To request data from a host server</span></span>

1. <span data-ttu-id="40834-106">Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con l'URI di una risorsa.</span><span class="sxs-lookup"><span data-stu-id="40834-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="40834-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40834-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("https://docs.microsoft.com");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("https://docs.microsoft.com")
    ```

    > [!NOTE]
    > <span data-ttu-id="40834-108">.NET Framework offre le classi specifiche del protocollo derivate dalle classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> per gli URI che iniziano con *http:*, *https:*, *ftp:* e *file:*.</span><span class="sxs-lookup"><span data-stu-id="40834-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="40834-109">Se è necessario impostare o eseguire la lettura di proprietà specifiche del protocollo, è necessario eseguire il cast dell'oggetto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> su un tipo di oggetto specifico del protocollo.</span><span class="sxs-lookup"><span data-stu-id="40834-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="40834-110">Per altre informazioni, vedere [Programmazione di protocolli di collegamento](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="40834-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="40834-111">Impostare i valori di proprietà necessari nell'oggetto `WebRequest`.</span><span class="sxs-lookup"><span data-stu-id="40834-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="40834-112">Per abilitare l'autenticazione, ad esempio, impostare la proprietà <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> su un'istanza della classe <xref:System.Net.NetworkCredential>:</span><span class="sxs-lookup"><span data-stu-id="40834-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="40834-113">Inviare la richiesta al server chiamando <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40834-113">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="40834-114">Questo metodo restituisce un oggetto contenente la risposta del server.</span><span class="sxs-lookup"><span data-stu-id="40834-114">This method returns an object containing the server's response.</span></span> <span data-ttu-id="40834-115">Il tipo dell'oggetto <xref:System.Net.WebResponse> restituito viene determinato dallo schema dell'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="40834-115">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="40834-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40834-116">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

4. <span data-ttu-id="40834-117">È possibile accedere alle proprietà dell'oggetto `WebResponse`oppure eseguirne il cast su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo.</span><span class="sxs-lookup"><span data-stu-id="40834-117">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="40834-118">Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast dell'oggetto `WebResponse` su un riferimento `HttpWebResponse`.</span><span class="sxs-lookup"><span data-stu-id="40834-118">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="40834-119">L'esempio di codice seguente illustra come visualizzare la proprietà <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> specifica di HTTP inviata con una risposta:</span><span class="sxs-lookup"><span data-stu-id="40834-119">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)
    ```

5. <span data-ttu-id="40834-120">Per ottenere il flusso contenente i dati di risposta inviati dal server, chiamare il metodo <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40834-120">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="40834-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40834-121">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

6. <span data-ttu-id="40834-122">Dopo aver letto i dati dall'oggetto risposta, chiuderlo con il metodo <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> oppure chiudere il flusso della risposta con il metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40834-122">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="40834-123">Se non si chiude l'oggetto risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare nuove richieste.</span><span class="sxs-lookup"><span data-stu-id="40834-123">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="40834-124">Poiché il metodo `WebResponse.Close` chiama `Stream.Close` quando chiude la risposta, non è necessario chiamare `Close` sia sull'oggetto risposta che sul flusso, anche se tale operazione non crea problemi.</span><span class="sxs-lookup"><span data-stu-id="40834-124">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="40834-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="40834-125">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="40834-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="40834-126">Example</span></span>

<span data-ttu-id="40834-127">L'esempio di codice seguente illustra come creare una richiesta a un server Web ed eseguire la lettura dei dati nella risposta:</span><span class="sxs-lookup"><span data-stu-id="40834-127">The following code example shows how to create a request to a web server and read the data in its response:</span></span>

[!code-csharp[RequestDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/RequestDataUsingWebRequest/cs/WebRequestGetExample.cs)]
[!code-vb[RequestDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/RequestDataUsingWebRequest/vb/WebRequestGetExample.vb)]

## <a name="see-also"></a><span data-ttu-id="40834-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40834-128">See also</span></span>

- [<span data-ttu-id="40834-129">Creazione di richieste Internet</span><span class="sxs-lookup"><span data-stu-id="40834-129">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="40834-130">Utilizzo dei flussi in rete</span><span class="sxs-lookup"><span data-stu-id="40834-130">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="40834-131">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="40834-131">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="40834-132">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="40834-132">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="40834-133">Procedura: inviare dati utilizzando la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="40834-133">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
