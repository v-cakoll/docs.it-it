---
title: 'Procedura: Inviare dati con la classe WebRequest'
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
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2102fce150f512a49093eb2b214258ac35e276e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-send-data-using-the-webrequest-class"></a>Procedura: Inviare dati con la classe WebRequest
La procedura seguente descrive i passaggi usati per inviare dati a un server. Questa procedura viene comunemente usata per pubblicare dati in una pagina Web.  
  
### <a name="to-send-data-to-a-host-server"></a>Per inviare dati a un server host  
  
1.  Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A> con l'URI della risorsa che accetta i dati, ad esempio, uno script o una pagina ASP.NET.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  .NET Framework fornisce le classi specifiche del protocollo derivate da **WebRequest** e **WebResponse** per gli URI che iniziano con "http:", "https:", "ftp:" e "file:". Per accedere alle risorse con altri protocolli, è necessario implementare classi specifiche del protocollo che derivano da **WebRequest** e **WebResponse**. Per altre informazioni, vedere [Programmazione di protocolli di collegamento](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
2.  Impostare i valori di proprietà necessari in **WebRequest**. Per abilitare l'autenticazione, ad esempio, impostare la proprietà **Credentials** su un'istanza della classe <xref:System.Net.NetworkCredential>.  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     Nella maggior parte dei casi, l'istanza stessa di **WebRequest** è sufficiente per inviare i dati. Tuttavia, se è necessario impostare le proprietà specifiche del protocollo, è necessario eseguire il cast di **WebRequest** sul tipo specifico del protocollo. Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebRequest>, eseguire il cast di **WebRequest** su un riferimento **HttpWebRequest**. L'esempio di codice seguente mostra come impostare la proprietà <xref:System.Net.HttpWebRequest.UserAgent%2A> specifica di HTTP.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Specificare un metodo di protocollo che consente l'invio dei dati con una richiesta, ad esempio il metodo **POST** HTTP.  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  Impostare la proprietà **ContentLength**.  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  Impostare la proprietà **ContentType** su un valore appropriato.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Ottenere il flusso che contiene i dati della richiesta chiamando il metodo <xref:System.Net.WebRequest.GetRequestStream%2A>.  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  Scrivere i dati nell'oggetto <xref:System.IO.Stream> restituito da questo metodo.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  Chiudere il flusso della richiesta chiamando il metodo **Stream.Close**.  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. Inviare la richiesta al server chiamando <xref:System.Net.WebRequest.GetResponse%2A>. Questo metodo restituisce un oggetto contenente la risposta del server. Il tipo dell'oggetto <xref:System.Net.WebResponse> restituito viene determinato dallo schema dell'URI della richiesta.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  Dopo aver finito di usare un oggetto <xref:System.Net.WebResponse>, è necessario chiuderlo chiamando il metodo <xref:System.Net.WebResponse.Close%2A>. In alternativa, se è stato usato il flusso di risposta dall'oggetto risposta, è possibile chiudere il flusso tramite la chiamata del metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Se non si chiude la risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare ulteriori richieste.  
  
10. È possibile accedere alle proprietà di **WebResponse** oppure eseguire il cast di **WebResponse** su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo. Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast di **WebResponse** su un riferimento **HttpWebResponse**.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Per ottenere il flusso contenente i dati di risposta inviati dal server, chiamare il metodo <xref:System.Net.WebResponse.GetResponseStream%2A> di **WebResponse**.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. Dopo la lettura dei dati dalla risposta, è necessario chiudere il flusso di risposta tramite il metodo **Stream.Close** oppure chiudere la risposta tramite il metodo **WebResponse.Close**. Non è necessario chiamare il metodo **Close** sia sul flusso di risposta che su **WebResponse**, ma non si tratta di un'operazione che può causare danni.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Esempio  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
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
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
            response.Close()  
        End Sub  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di richieste Internet](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [L'uso di flussi di rete](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [Accesso a Internet con un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Richiesta di dati](../../../docs/framework/network-programming/requesting-data.md)  
 [Procedura: Richiedere dati con la classe WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
