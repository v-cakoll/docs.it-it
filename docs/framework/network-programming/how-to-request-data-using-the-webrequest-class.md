---
title: 'Procedura: Richiedere dati con la classe WebRequest'
ms.date: 03/30/2017
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e02ad4772d3ba84a2735a2e146a9979862d75989
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397715"
---
# <a name="how-to-request-data-using-the-webrequest-class"></a>Procedura: Richiedere dati con la classe WebRequest
La procedura seguente descrive i passaggi necessari per richiedere una risorsa da un server, ad esempio, una pagina Web o un file. La risorsa deve essere identificata da un URI.  
  
### <a name="to-request-data-from-a-host-server"></a>Per richiedere dati da un server host  
  
1.  Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A> con l'URI della risorsa.  
  
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
  
     Nella maggior parte dei casi, la classe **WebRequest** è sufficiente per la ricezione di dati. Tuttavia, se è necessario impostare le proprietà specifiche del protocollo, è necessario eseguire il cast di **WebRequest** sul tipo specifico del protocollo. Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebRequest>, eseguire il cast di **WebRequest** su un riferimento **HttpWebRequest**. L'esempio di codice seguente mostra come impostare la proprietà <xref:System.Net.HttpWebRequest.UserAgent%2A> specifica di HTTP.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Per inviare la richiesta al server, chiamare <xref:System.Net.HttpWebRequest.GetResponse%2A>. Il tipo effettivo dell'oggetto **WebResponse** restituito è determinato dallo schema dell'URI richiesto.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  Dopo aver finito di usare un oggetto <xref:System.Net.WebResponse>, è necessario chiuderlo chiamando il metodo <xref:System.Net.WebResponse.Close%2A>. In alternativa, se è stato usato il flusso di risposta dall'oggetto risposta, è possibile chiudere il flusso tramite la chiamata del metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Se non si chiude la risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare ulteriori richieste.  
  
4.  È possibile accedere alle proprietà di **WebResponse** oppure eseguire il cast di **WebResponse** su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo. Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast di **WebResponse** su un riferimento **HttpWebResponse**. L'esempio di codice seguente mostra come visualizzare le informazioni sullo stato inviate con una risposta.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Per ottenere il flusso contenente i dati di risposta inviati dal server, usare il metodo <xref:System.Net.HttpWebResponse.GetResponseStream%2A> di **WebResponse**.  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  Dopo la lettura dei dati dalla risposta, è necessario chiudere il flusso di risposta tramite il metodo **Stream.Close** oppure chiudere la risposta tramite il metodo **WebResponse.Close**. Non è necessario chiamare il metodo **Close** sia sul flusso di risposta che su **WebResponse**, ma non si tratta di un'operazione che può causare danni. **WebResponse.Close** chiama **Stream.Close** alla chiusura della risposta.  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di richieste Internet](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [Uso di flussi nella rete](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [Accesso a Internet con un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Richiesta di dati](../../../docs/framework/network-programming/requesting-data.md)  
 [Procedura: Inviare dati con la classe WebRequest](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
