---
title: 'Procedura: Richiedere dati con la classe WebRequest'
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
ms.openlocfilehash: 1b71327d007e66cc217f6d69e11122c481e5118f
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634037"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a>Procedura: Richiedere dati con la classe WebRequest
La procedura seguente descrive i passaggi per richiedere una risorsa da un server, ad esempio una pagina Web o un file. La risorsa deve essere identificata da un URI.  
  
## <a name="to-request-data-from-a-host-server"></a>Per richiedere dati da un server host  
  
1.  Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con l'URI di una risorsa. Ad esempio: 
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/default.html");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/default.html")  
    ```  
  
    > [!NOTE]
    > .NET Framework offre le classi specifiche del protocollo derivate dalle classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> per gli URI che iniziano con *http:*, *https:*, *ftp:* e *file:*.
    Se è necessario impostare o eseguire la lettura di proprietà specifiche del protocollo, è necessario eseguire il cast dell'oggetto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> su un tipo di oggetto specifico del protocollo. Per altre informazioni, vedere [Programmazione di protocolli di collegamento](programming-pluggable-protocols.md). 
  
2.  Impostare i valori di proprietà necessari nell'oggetto `WebRequest`. Per abilitare l'autenticazione, ad esempio, impostare la proprietà <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> su un'istanza della classe <xref:System.Net.NetworkCredential>:  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
3.  Inviare la richiesta al server chiamando <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>. Questo metodo restituisce un oggetto contenente la risposta del server. Il tipo dell'oggetto <xref:System.Net.WebResponse> restituito viene determinato dallo schema dell'URI della richiesta. Ad esempio:
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
4.  È possibile accedere alle proprietà dell'oggetto `WebResponse`oppure eseguirne il cast su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo. 

    Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast dell'oggetto `WebResponse` su un riferimento `HttpWebResponse`. L'esempio di codice seguente illustra come visualizzare la proprietà <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> specifica di HTTP inviata con una risposta:
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Per ottenere il flusso contenente i dati di risposta inviati dal server, chiamare il metodo <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>. Ad esempio:  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  Dopo aver letto i dati dall'oggetto risposta, chiuderlo con il metodo <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> oppure chiudere il flusso della risposta con il metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Se non si chiude l'oggetto risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare nuove richieste. Poiché il metodo `WebResponse.Close` chiama `Stream.Close` quando chiude la risposta, non è necessario chiamare `Close` sia sull'oggetto risposta che sul flusso, anche se tale operazione non crea problemi. Ad esempio:
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Esempio  

L'esempio di codice seguente illustra come creare una richiesta a un server Web ed eseguire la lettura dei dati nella risposta:  
  
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
            // Open the stream by using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  

            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  

            // Clean up the response.  
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
            ' Open the stream by using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  

            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  

            ' Clean up the response.  
            reader.Close()  
            response.Close() 

        End Sub   

    End Class  
 
End Namespace  
```  
  
## <a name="see-also"></a>Vedere anche
- [Creazione di richieste Internet](creating-internet-requests.md)
- [Uso di flussi nella rete](using-streams-on-the-network.md)
- [Accesso a Internet con un proxy](accessing-the-internet-through-a-proxy.md)
- [Richiesta di dati](requesting-data.md)
- [Procedura: Inviare dati con la classe WebRequest](how-to-send-data-using-the-webrequest-class.md)
