---
title: Gestione di connessioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 29077a1c0f2b803270adb730e0d810143095e709
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526542"
---
# <a name="managing-connections"></a><span data-ttu-id="4ba4d-102">Gestione di connessioni</span><span class="sxs-lookup"><span data-stu-id="4ba4d-102">Managing Connections</span></span>
<span data-ttu-id="4ba4d-103">Le applicazioni che usano HTTP per connettersi alle risorse di dati possono usare le classi <xref:System.Net.ServicePoint> e <xref:System.Net.ServicePointManager> di .NET Framework per gestire le connessioni a Internet e ottenere prestazioni e scalabilità ottimali.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-103">Applications that use HTTP to connect to data resources can use the .NET Framework's <xref:System.Net.ServicePoint> and <xref:System.Net.ServicePointManager> classes to manage connections to the Internet and to help them achieve optimum scale and performance.</span></span>  
  
 <span data-ttu-id="4ba4d-104">La classe **ServicePoint** offre un endpoint a cui un'applicazione può connettersi per accedere alle risorse Internet.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-104">The **ServicePoint** class provides an application with an endpoint to which the application can connect to access Internet resources.</span></span> <span data-ttu-id="4ba4d-105">Ogni **ServicePoint** contiene informazioni che consentono di ottimizzare le connessioni con un server Internet tramite la condivisione di informazioni sull'ottimizzazione tra le connessioni per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-105">Each **ServicePoint** contains information that helps optimize connections with an Internet server by sharing optimization information between connections to improve performance.</span></span>  
  
 <span data-ttu-id="4ba4d-106">Ogni **ServicePoint** è identificato da un URI (Uniform Resource Identifier) e viene categorizzato in base ai frammenti dell'URI che indicano host e identificatore di schema.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-106">Each **ServicePoint** is identified by a Uniform Resource Identifier (URI) and is categorized according to the scheme identifier and host fragments of the URI.</span></span> <span data-ttu-id="4ba4d-107">Ad esempio, la stessa istanza di **ServicePoint** fornirà le richieste agli URI `http://www.contoso.com/index.htm` e `http://www.contoso.com/news.htm?date=today` perché hanno gli stessi frammenti per l'identificatore di schema (http) e l'host (`www.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="4ba4d-107">For example, the same **ServicePoint** instance would provide requests to the URIs `http://www.contoso.com/index.htm` and `http://www.contoso.com/news.htm?date=today` since they have the same scheme identifier (http) and host fragments (`www.contoso.com`).</span></span> <span data-ttu-id="4ba4d-108">Se l'applicazione dispone già di una connessione permanente al server `www.contoso.com`, userà tale connessione per recuperare entrambe le richieste, evitando la necessità di creare due connessioni.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-108">If the application already has a persistent connection to the server `www.contoso.com`, it uses that connection to retrieve both requests, avoiding the need to create two connections.</span></span>  
  
 <span data-ttu-id="4ba4d-109">**ServicePointManager** è una classe statica che gestisce la creazione e distruzione delle istanze di **ServicePoint**.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-109">**ServicePointManager** is a static class that manages the creation and destruction of **ServicePoint** instances.</span></span> <span data-ttu-id="4ba4d-110">**ServicePointManager** crea un **ServicePoint** quando l'applicazione richiede una risorsa Internet che non è presente nella raccolta di istanze di **ServicePoint** esistenti.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-110">The **ServicePointManager** creates a **ServicePoint** when the application requests an Internet resource that is not in the collection of existing **ServicePoint** instances.</span></span> <span data-ttu-id="4ba4d-111">Le istanze di **ServicePoint** vengono eliminate definitivamente quando superano il tempo di inattività massimo o quando il numero di istanze di **ServicePoint** esistenti supera il numero massimo di istanze di **ServicePoint** per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-111">**ServicePoint** instances are destroyed when they have exceeded their maximum idle time or when the number of existing **ServicePoint** instances exceeds the maximum number of **ServicePoint** instances for the application.</span></span> <span data-ttu-id="4ba4d-112">È possibile controllare sia il tempo di inattività massimo predefinito che il numero massimo di istanze di **ServicePoint** impostando le proprietà <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> e <xref:System.Net.ServicePointManager.MaxServicePoints%2A> in **ServicePointManager**.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-112">You can control both the default maximum idle time and the maximum number of **ServicePoint** instances by setting the <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> and <xref:System.Net.ServicePointManager.MaxServicePoints%2A> properties on the **ServicePointManager**.</span></span>  
  
 <span data-ttu-id="4ba4d-113">Il numero di connessioni tra un client e un server può avere un impatto significativo sulla velocità effettiva dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-113">The number of connections between a client and server can have a dramatic impact on application throughput.</span></span> <span data-ttu-id="4ba4d-114">Per impostazione predefinita, un'applicazione che usa la classe <xref:System.Net.HttpWebRequest> usa al massimo due connessioni permanenti a un determinato server, ma è possibile impostare il numero massimo di connessioni per ogni singola applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-114">By default, an application using the <xref:System.Net.HttpWebRequest> class uses a maximum of two persistent connections to a given server, but you can set the maximum number of connections on a per-application basis.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ba4d-115">La specifica HTTP/1.1 limita il numero di connessioni da un'applicazione a due connessioni per server.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-115">The HTTP/1.1 specification limits the number of connections from an application to two connections per server.</span></span>  
  
 <span data-ttu-id="4ba4d-116">Il numero ottimale di connessioni dipende dalle condizioni effettive di esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-116">The optimum number of connections depends on the actual conditions in which the application runs.</span></span> <span data-ttu-id="4ba4d-117">L'aumento del numero di connessioni disponibili per l'applicazione potrebbe non influire sulle prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-117">Increasing the number of connections available to the application may not affect application performance.</span></span> <span data-ttu-id="4ba4d-118">Per determinare l'impatto dell'aggiunta di altre connessioni, eseguire più test delle prestazioni variando il numero di connessioni.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-118">To determine the impact of more connections, run performance tests while varying the number of connections.</span></span> <span data-ttu-id="4ba4d-119">È possibile modificare il numero di connessioni usate da un'applicazione modificando la proprietà <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> statica nella classe **ServicePointManager** durante l'inizializzazione dell'applicazione, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-119">You can change the number of connections that an application uses by changing the static <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> property on the **ServicePointManager** class at application initialization, as shown in the following code sample.</span></span>  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 <span data-ttu-id="4ba4d-120">La modifica della proprietà **ServicePointManager.DefaultConnectionLimit** non influisce sulle istanze di **ServicePoint** inizializzate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-120">Changing the **ServicePointManager.DefaultConnectionLimit** property does not affect previously initialized **ServicePoint** instances.</span></span> <span data-ttu-id="4ba4d-121">Il codice seguente illustra la modifica del limite di connessione per un'istanza esistente di **ServicePoint** per il server `http://www.contoso.com` sul valore archiviato in `newLimit`.</span><span class="sxs-lookup"><span data-stu-id="4ba4d-121">The following code demonstrates changing the connection limit on an existing **ServicePoint** for the server `http://www.contoso.com` to the value stored in `newLimit`.</span></span>  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ba4d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ba4d-122">See Also</span></span>  
 [<span data-ttu-id="4ba4d-123">Raggruppamento delle connessioni</span><span class="sxs-lookup"><span data-stu-id="4ba4d-123">Connection Grouping</span></span>](../../../docs/framework/network-programming/connection-grouping.md)  
 [<span data-ttu-id="4ba4d-124">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="4ba4d-124">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
