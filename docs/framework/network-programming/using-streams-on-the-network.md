---
title: Uso di flussi nella rete
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
ms.openlocfilehash: 7d5a2e3eec9b49731a09f6eb41a8d8500a59b45c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180615"
---
# <a name="using-streams-on-the-network"></a>Uso di flussi nella rete
Le risorse di rete sono rappresentate in .NET Framework come flussi. Grazie alla possibilità di gestire i flussi in modo generico, .NET Framework offre le opportunità seguenti:  
  
- Un modo comune per inviare e ricevere dati Web. Indipendentemente dal contenuto effettivo del file (HTML, XML o altro) l'applicazione userà <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> e <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> per inviare e ricevere dati.  
  
- Compatibilità con i flussi in .NET Framework. I flussi vengono usati in tutte le parti di .NET Framework, che offre un'infrastruttura avanzata per gestirli. Ad esempio, è possibile modificare un'applicazione che legge dati XML da un <xref:System.IO.FileStream> in modo che legga invece i dati da un <xref:System.Net.Sockets.NetworkStream> modificando solo le poche righe di codice che inizializzano il flusso. Le differenze principali tra la classe **NetworkStream** e gli altri flussi sono che **NetworkStream** non supporta la ricerca, la proprietà <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> restituisce sempre **false** e i metodi <xref:System.Net.Sockets.NetworkStream.Seek%2A> e <xref:System.Net.Sockets.NetworkStream.Position%2A> generano <xref:System.NotSupportedException>.  
  
- Elaborazione dei dati all'arrivo. I flussi consentono l'accesso ai dati non appena arrivano dalla rete, anziché imporre a un'applicazione di attendere il completamento del download dell'intero set di dati.  
  
 Lo spazio dei nomi <xref:System.Net.Sockets> contiene una classe **NetworkStream** che implementa la classe <xref:System.IO.Stream> appositamente per l'uso con le risorse di rete. Le classi nello spazio dei nomi <xref:System.Net.Sockets> usano la classe **NetworkStream** per rappresentare i flussi.  
  
 Per inviare dati alla rete usando il flusso restituito, chiamare <xref:System.Net.WebRequest.GetRequestStream%2A> su <xref:System.Net.WebRequest>. **WebRequest** invierà le intestazioni di richiesta al server; è quindi possibile inviare dati alla <xref:System.IO.Stream.BeginWrite%2A> <xref:System.IO.Stream.EndWrite%2A>risorsa <xref:System.IO.Stream.Write%2A> di rete chiamando il metodo , , o sul flusso restituito. Alcuni protocolli, ad esempio HTTP, potrebbero richiedere di impostare proprietà specifiche del protocollo prima di inviare dati. L'esempio di codice seguente illustra come impostare le proprietà specifiche di HTTP per l'invio dei dati. Presuppone che la variabile `sendData` contenga i dati da inviare e che la variabile `sendLength` corrisponda al numero di byte di dati da inviare.  
  
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
  
 Per ricevere dati dalla rete, chiamare <xref:System.Net.WebResponse.GetResponseStream%2A> su <xref:System.Net.WebResponse>. È quindi possibile leggere dati dalla risorsa di rete tramite la chiamata del metodo <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> o <xref:System.IO.Stream.Read%2A> sul flusso restituito.  
  
 Quando si usano flussi dalle risorse di rete, tenere presente quanto segue:  
  
- La proprietà **CanSeek** restituisce sempre **false** perché la classe **NetworkStream** non può cambiare posizione nel flusso. I metodi **Seek** e **Position** generano **NotSupportedException**.  
  
- Quando si usa **WebRequest** e **WebResponse**, le istanze del flusso create chiamando **GetResponseStream** sono di sola lettura e quelle create chiamando **GetRequestStream** sono di sola scrittura.  
  
- Usare la classe <xref:System.IO.StreamReader> per facilitare la codifica. L'esempio di codice seguente illustra come usare **StreamReader** per leggere un flusso con codifica ASCII da una **WebResponse** (l'esempio non include la creazione della richiesta).  
  
- La chiamata a **GetResponse** può bloccarsi se non sono disponibili risorse di rete. È consigliabile prendere in considerazione l'uso di una richiesta asincrona con i metodi <xref:System.Net.WebRequest.BeginGetResponse%2A> e <xref:System.Net.WebRequest.EndGetResponse%2A>.  
  
- La chiamata a **GetRequestStream** può bloccarsi mentre viene creata la connessione al server. È consigliabile prendere in considerazione l'uso di una richiesta asincrona per il flusso con i metodi <xref:System.Net.WebRequest.BeginGetRequestStream%2A> e <xref:System.Net.WebRequest.EndGetRequestStream%2A>.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Richiedere dati con la classe WebRequest](how-to-request-data-using-the-webrequest-class.md)
- [Richiesta di dati](requesting-data.md)
