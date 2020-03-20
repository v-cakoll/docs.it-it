---
title: Procedure consigliate per le classi System.Net
ms.date: 03/30/2017
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
ms.openlocfilehash: c7324dcbc27c95c7d799592700d46c195e7d952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048885"
---
# <a name="best-practices-for-systemnet-classes"></a><span data-ttu-id="3afff-102">Procedure consigliate per le classi System.Net</span><span class="sxs-lookup"><span data-stu-id="3afff-102">Best Practices for System.Net Classes</span></span>
<span data-ttu-id="3afff-103">I suggerimenti seguenti consentono di usare al meglio le classi contenute in <xref:System.Net>:</span><span class="sxs-lookup"><span data-stu-id="3afff-103">The following recommendations will help you use the classes contained in <xref:System.Net> to their best advantage:</span></span>  
  
- <span data-ttu-id="3afff-104">Per le procedure consigliate per Transport Layer Security (TLS), vedere [Procedure consigliate per Transport Layer Security (TLS) con .NET Framework](tls.md).</span><span class="sxs-lookup"><span data-stu-id="3afff-104">For Transport Layer Security (TLS) best practices, see [Transport Layer Security (TLS) best practices with .NET Framework](tls.md).</span></span>

- <span data-ttu-id="3afff-105">Se possibile, usare le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> anziché eseguire cast di tipo nelle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="3afff-105">Use <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> whenever possible instead of type casting to descendant classes.</span></span> <span data-ttu-id="3afff-106">Le applicazioni che usano **WebRequest** e **WebResponse** possono usufruire dei nuovi protocolli Internet senza dover apportare modifiche significative al codice.</span><span class="sxs-lookup"><span data-stu-id="3afff-106">Applications that use **WebRequest** and **WebResponse** can take advantage of new Internet protocols without needing extensive code changes.</span></span>  
  
- <span data-ttu-id="3afff-107">Quando si scrivono applicazioni ASP.NET da eseguire su un server mediante le classi **System.Net**, è spesso preferibile, in termini di prestazioni, usare i metodi asincroni per <xref:System.Net.WebRequest.GetResponse%2A> e <xref:System.Net.WebResponse.GetResponseStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="3afff-107">When writing ASP.NET applications that run on a server using the **System.Net** classes, it is often better, from a performance standpoint, to use the asynchronous methods for <xref:System.Net.WebRequest.GetResponse%2A> and <xref:System.Net.WebResponse.GetResponseStream%2A>.</span></span>  
  
- <span data-ttu-id="3afff-108">Il numero di connessioni aperte a una risorsa Internet può influire in modo significativo sulle prestazioni di rete e sulla velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="3afff-108">The number of connections opened to an Internet resource can have a significant impact on network performance and throughput.</span></span> <span data-ttu-id="3afff-109">Per impostazione predefinita, **System.Net** usa due connessioni per ogni applicazione e per ogni host.</span><span class="sxs-lookup"><span data-stu-id="3afff-109">**System.Net** uses two connections per application per host by default.</span></span> <span data-ttu-id="3afff-110">Impostando la proprietà <xref:System.Net.ServicePoint.ConnectionLimit%2A> nella classe <xref:System.Net.ServicePoint> relativa all'applicazione, è possibile aumentare questo numero per un determinato host.</span><span class="sxs-lookup"><span data-stu-id="3afff-110">Setting the <xref:System.Net.ServicePoint.ConnectionLimit%2A> property in the <xref:System.Net.ServicePoint> for your application can increase this number for a particular host.</span></span> <span data-ttu-id="3afff-111">L'impostazione della proprietà <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> consente invece di aumentare il numero predefinito per tutti gli host.</span><span class="sxs-lookup"><span data-stu-id="3afff-111">Setting the <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> property can increase this default for all hosts.</span></span>  
  
- <span data-ttu-id="3afff-112">Quando si scrivono protocolli di livello socket, è preferibile usare <xref:System.Net.Sockets.TcpClient> o <xref:System.Net.Sockets.UdpClient> anziché scrivere direttamente su un <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="3afff-112">When writing socket-level protocols, try to use <xref:System.Net.Sockets.TcpClient> or <xref:System.Net.Sockets.UdpClient> whenever possible instead of writing directly to a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="3afff-113">Queste due classi client, infatti, incapsulano la creazione di socket TCP e UDP, evitando di dover gestire i dettagli della connessione.</span><span class="sxs-lookup"><span data-stu-id="3afff-113">These two client classes encapsulate the creation of TCP and UDP sockets without requiring you to handle the details of the connection.</span></span>  
  
- <span data-ttu-id="3afff-114">Quando si accede a siti che richiedono credenziali, usare la classe <xref:System.Net.CredentialCache> per creare una cache di credenziali anziché fornirle con ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="3afff-114">When accessing sites that require credentials, use the <xref:System.Net.CredentialCache> class to create a cache of credentials rather than supplying them with every request.</span></span> <span data-ttu-id="3afff-115">La classe **CredentialCache** cerca nella cache la credenziale appropriata da presentare con una richiesta, sollevando l'utente dalla responsabilità di creare e presentare credenziali in base all'URL.</span><span class="sxs-lookup"><span data-stu-id="3afff-115">The **CredentialCache** class searches the cache to find the appropriate credential to present with a request, relieving you of the responsibility of creating and presenting credentials based on the URL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3afff-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3afff-116">See also</span></span>

- [<span data-ttu-id="3afff-117">Programmazione di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3afff-117">Network Programming in the .NET Framework</span></span>](index.md)
