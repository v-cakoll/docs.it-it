---
title: 'Procedura: inviare dati tramite la classe WebRequest'
description: Informazioni su come inviare dati a un server usando la classe WebRequest nell'.NET Framework. Questa procedura viene comunemente usata per inserire i dati in una pagina Web.
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 4b353250fec778ee8b352f13de6d7faaf15c13ee
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502444"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a>Procedura: inviare dati tramite la classe WebRequest

La procedura seguente descrive i passaggi per inviare dati a un server. Questa procedura viene comunemente usata per pubblicare dati in una pagina Web.

## <a name="to-send-data-to-a-host-server"></a>Per inviare dati a un server host

1. Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con l'URI di una risorsa che accetta dati, come ad esempio uno script o una pagina ASP.NET. Ad esempio:

    ```csharp
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")
    ```

    > [!NOTE]
    > .NET Framework offre le classi specifiche del protocollo derivate dalle classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> per gli URI che iniziano con *http:*, *https:*, *ftp:* e *file:*.

    Se è necessario impostare o eseguire la lettura di proprietà specifiche del protocollo, è necessario eseguire il cast dell'oggetto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> su un tipo di oggetto specifico del protocollo. Per altre informazioni, vedere [Programmazione di protocolli di collegamento](programming-pluggable-protocols.md).

2. Impostare i valori di proprietà necessari nell'oggetto `WebRequest`. Per abilitare l'autenticazione, ad esempio, impostare la proprietà <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> su un'istanza della classe <xref:System.Net.NetworkCredential>:

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. Specificare un metodo di protocollo che consente l'invio dei dati con una richiesta, ad esempio il metodo `POST` HTTP:

    ```csharp
    request.Method = "POST";
    ```

    ```vb
    request.Method = "POST"
    ```

4. Impostare la proprietà <xref:System.Web.HttpRequest.ContentLength> sul numero di byte inclusi nella richiesta. Ad esempio:

    ```csharp
    request.ContentLength = byteArray.Length;
    ```

    ```vb
    request.ContentLength = byteArray.Length
    ```

5. Impostare la proprietà <xref:System.Web.HttpRequest.ContentType> su un valore appropriato. Ad esempio:

    ```csharp
    request.ContentType = "application/x-www-form-urlencoded";
    ```

    ```vb
    request.ContentType = "application/x-www-form-urlencoded"
    ```

6. Ottenere il flusso che contiene i dati della richiesta chiamando il metodo <xref:System.Net.WebRequest.GetRequestStream%2A>. Ad esempio:

    ```csharp
    Stream dataStream = request.GetRequestStream();
    ```

    ```vb
    Dim dataStream As Stream = request.GetRequestStream()
    ```

7. Scrivere i dati nell'oggetto <xref:System.IO.Stream> restituito dal metodo `GetRequestStream`. Ad esempio:

    ```csharp
    dataStream.Write(byteArray, 0, byteArray.Length);
    ```

    ```vb
    dataStream.Write(byteArray, 0, byteArray.Length)
    ```

8. Chiudere il flusso della richiesta chiamando il metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Ad esempio:

    ```csharp
    dataStream.Close();
    ```

    ```vb
    dataStream.Close()
    ```

9. Inviare la richiesta al server chiamando <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>. Questo metodo restituisce un oggetto contenente la risposta del server. Il tipo dell'oggetto `WebResponse` restituito viene determinato dallo schema dell'URI della richiesta. Ad esempio:

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

10. È possibile accedere alle proprietà dell'oggetto `WebResponse`oppure eseguirne il cast su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo.

    Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast dell'oggetto `WebResponse` su un riferimento <xref:System.Net.HttpWebResponse>. L'esempio di codice seguente illustra come visualizzare la proprietà <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> specifica di HTTP inviata con una risposta:

    ```csharp
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)
    ```

11. Per ottenere il flusso contenente i dati di risposta inviati dal server, chiamare il metodo <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> dell'oggetto `WebResponse`. Ad esempio:

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

12. Dopo aver letto i dati dall'oggetto risposta, chiuderlo con il metodo <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> oppure chiudere il flusso della risposta con il metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Se non si chiude la risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare nuove richieste. Poiché il metodo `WebResponse.Close` chiama `Stream.Close` quando chiude la risposta, non è necessario chiamare `Close` sia sull'oggetto risposta che sul flusso, anche se tale operazione non crea problemi. Ad esempio:

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a>Esempio

L'esempio seguente illustra come inviare dati a un server Web ed eseguire la lettura dei dati nella risposta:

[!code-csharp[SendDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/SendDataUsingWebRequest/cs/WebRequestPostExample.cs)]
[!code-vb[SendDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/SendDataUsingWebRequest/vb/WebRequestPostExample.vb)]

## <a name="see-also"></a>Vedere anche

- [Creazione di richieste Internet](creating-internet-requests.md)
- [Uso di flussi nella rete](using-streams-on-the-network.md)
- [Accesso a Internet con un proxy](accessing-the-internet-through-a-proxy.md)
- [Richiesta di dati](requesting-data.md)
- [Procedura: richiedere dati tramite la classe WebRequest](how-to-request-data-using-the-webrequest-class.md)
