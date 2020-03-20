---
title: Richiesta di dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
ms.openlocfilehash: 1f367caf7656a83597b6262a5746686df15d33b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047323"
---
# <a name="requesting-data"></a><span data-ttu-id="2522d-102">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="2522d-102">Requesting Data</span></span>
<span data-ttu-id="2522d-103">Lo sviluppo di applicazioni in esecuzione nell'ambiente operativo distribuito dell'attuale rete Internet richiede un metodo efficace e semplice da usare per il recupero dei dati da risorse di tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="2522d-103">Developing applications that run in the distributed operating environment of today's Internet requires an efficient, easy-to-use method for retrieving data from resources of all types.</span></span> <span data-ttu-id="2522d-104">I protocolli di collegamento consentono di sviluppare applicazioni che usano una singola interfaccia per recuperare i dati da più protocolli Internet.</span><span class="sxs-lookup"><span data-stu-id="2522d-104">Pluggable protocols let you develop applications that use a single interface to retrieve data from multiple Internet protocols.</span></span>  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a><span data-ttu-id="2522d-105">Caricamento e download dei dati da un server Internet</span><span class="sxs-lookup"><span data-stu-id="2522d-105">Uploading and Downloading Data from an Internet Server</span></span>  
 <span data-ttu-id="2522d-106">Per semplici transazioni di richiesta e risposta, la classe <xref:System.Net.WebClient> offre il metodo più semplice per caricare e scaricare i dati da un server Internet.</span><span class="sxs-lookup"><span data-stu-id="2522d-106">For simple request and response transactions, the <xref:System.Net.WebClient> class provides the easiest method for uploading data to or downloading data from an Internet server.</span></span> <span data-ttu-id="2522d-107">**WebClient** fornisce metodi per caricare e scaricare file, inviare e ricevere flussi, inviare un buffer di dati al server e ricevere una risposta.</span><span class="sxs-lookup"><span data-stu-id="2522d-107">**WebClient** provides methods for uploading and downloading files, sending and receiving streams, and sending a data buffer to the server and receiving a response.</span></span> <span data-ttu-id="2522d-108">**WebClient** usa le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> per stabilire le connessioni alla risorsa Internet, così che qualunque protocollo di collegamento registrato sia disponibile per l'uso.</span><span class="sxs-lookup"><span data-stu-id="2522d-108">**WebClient** uses the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes to make the actual connections to the Internet resource, so any registered pluggable protocol is available for use.</span></span>  
  
 <span data-ttu-id="2522d-109">Le applicazioni client che devono eseguire transazioni più complesse richiedono i dati dai server usando la classe **WebRequest** e i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="2522d-109">Client applications that need to make more complex transactions request data from servers using the **WebRequest** class and its descendants.</span></span> <span data-ttu-id="2522d-110">**WebRequest** incapsula i dettagli della connessione al server, inviando la richiesta e ricevendo la risposta.</span><span class="sxs-lookup"><span data-stu-id="2522d-110">**WebRequest** encapsulates the details of connecting to the server, sending the request, and receiving the response.</span></span> <span data-ttu-id="2522d-111">**WebRequest** è una classe astratta che definisce un set di proprietà e metodi disponibili per tutte le applicazioni che usano protocolli di collegamento.</span><span class="sxs-lookup"><span data-stu-id="2522d-111">**WebRequest** is an abstract class that defines a set of properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="2522d-112">I discendenti di **WebRequest**, come <xref:System.Net.HttpWebRequest>, implementano le proprietà e i metodi definiti da **WebRequest** in modo coerente con il protocollo sottostante.</span><span class="sxs-lookup"><span data-stu-id="2522d-112">Descendants of **WebRequest**, such as <xref:System.Net.HttpWebRequest>, implement the properties and methods defined by **WebRequest** in a way that is consistent with the underlying protocol.</span></span>  
  
 <span data-ttu-id="2522d-113">La classe **WebRequest** crea istanze specifiche del protocollo dei discendenti di **WebRequest** usando il valore dell'URI passato al metodo <xref:System.Net.WebRequest.Create%2A> per determinare l'istanza di classe derivata specifica da creare.</span><span class="sxs-lookup"><span data-stu-id="2522d-113">The **WebRequest** class creates protocol-specific instances of **WebRequest** descendants, using the value of the URI passed to its <xref:System.Net.WebRequest.Create%2A> method to determine the specific derived-class instance to create.</span></span> <span data-ttu-id="2522d-114">Le applicazioni indicano i discendenti di **WebRequest** da usare per gestire una richiesta registrando il costruttore del discendente con il metodo <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2522d-114">Applications indicate which **WebRequest** descendant should be used to handle a request by registering the descendant's constructor with the <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="2522d-115">Viene effettuata una richiesta alla risorsa Internet chiamando il metodo <xref:System.Net.WebRequest.GetResponse%2A> in **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="2522d-115">A request is made to the Internet resource by calling the <xref:System.Net.WebRequest.GetResponse%2A> method on the **WebRequest**.</span></span> <span data-ttu-id="2522d-116">Il metodo **GetResponse** costruisce la richiesta specifica del protocollo usando le proprietà di **WebRequest**, crea la connessione socket TCP o UDP al server e invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="2522d-116">The **GetResponse** method constructs the protocol-specific request from the properties of the **WebRequest**, makes the TCP or UDP socket connection to the server, and sends the request.</span></span> <span data-ttu-id="2522d-117">Per le richieste che inviano dati al server, ad esempio le richieste HTTP **Post** o FTP **Put**, il metodo <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> fornisce un flusso di rete in cui inviare dati.</span><span class="sxs-lookup"><span data-stu-id="2522d-117">For requests that send data to the server, such as HTTP **Post** or FTP **Put** requests, the <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> method provides a network stream in which to send the data.</span></span>  
  
 <span data-ttu-id="2522d-118">Il metodo **GetResponse** restituisce un oggetto **WebResponse** specifico del protocollo che corrisponde all'oggetto **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="2522d-118">The **GetResponse** method returns a protocol-specific **WebResponse** that matches the **WebRequest.**</span></span>  
  
 <span data-ttu-id="2522d-119">La classe **WebResponse** è anche una classe astratta che definisce le proprietà e i metodi disponibili per tutte le applicazioni che usano protocolli di collegamento.</span><span class="sxs-lookup"><span data-stu-id="2522d-119">The **WebResponse** class is also an abstract class that defines properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="2522d-120">I discendenti di **WebResponse** implementano questi metodi e proprietà per il protocollo sottostante.</span><span class="sxs-lookup"><span data-stu-id="2522d-120">**WebResponse** descendants implement these properties and methods for the underlying protocol.</span></span> <span data-ttu-id="2522d-121">La classe <xref:System.Net.HttpWebResponse>, ad esempio, implementa la classe **WebResponse** per HTTP.</span><span class="sxs-lookup"><span data-stu-id="2522d-121">The <xref:System.Net.HttpWebResponse> class, for example, implements the **WebResponse** class for HTTP.</span></span>  
  
 <span data-ttu-id="2522d-122">I dati restituiti dal server vengono presentati all'applicazione nel flusso restituito dal metodo <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2522d-122">The data returned by the server is presented to the application in the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2522d-123">È possibile usare questo flusso come qualsiasi altro, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2522d-123">You can use this stream like any other, as shown in the following example.</span></span>  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2522d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2522d-124">See also</span></span>

- [<span data-ttu-id="2522d-125">Programmazione di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2522d-125">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="2522d-126">Procedura: Richiedere una pagina Web e recuperare i risultati sotto forma di flusso</span><span class="sxs-lookup"><span data-stu-id="2522d-126">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [<span data-ttu-id="2522d-127">Procedura: Recuperare un oggetto WebResponse specifico del protocollo corrispondente a un oggetto WebRequest</span><span class="sxs-lookup"><span data-stu-id="2522d-127">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
