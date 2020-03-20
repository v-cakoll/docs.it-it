---
title: HTTP
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
ms.openlocfilehash: c8c799a50e5d63bbf411c338eb9e93f85a942bb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048003"
---
# <a name="http"></a><span data-ttu-id="96b8d-102">HTTP</span><span class="sxs-lookup"><span data-stu-id="96b8d-102">HTTP</span></span>
<span data-ttu-id="96b8d-103">.NET Framework offre il supporto completo per il protocollo HTTP, che costituisce la maggior parte di tutto il traffico Internet, con le classi <xref:System.Net.HttpWebRequest> e <xref:System.Net.HttpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="96b8d-103">The .NET Framework provides comprehensive support for the HTTP protocol, which makes up the majority of all Internet traffic, with the <xref:System.Net.HttpWebRequest> and <xref:System.Net.HttpWebResponse> classes.</span></span> <span data-ttu-id="96b8d-104">Queste classi, derivate da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>, vengono restituite per impostazione predefinita ogni volta che il metodo statico <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> rileva un URI che inizia con "http" o "https".</span><span class="sxs-lookup"><span data-stu-id="96b8d-104">These classes, derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, are returned by default whenever the static method <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> encounters a URI beginning with "http" or "https".</span></span> <span data-ttu-id="96b8d-105">Nella maggior parte dei casi, le classi **WebRequest** e **WebResponse** rendono disponibile tutto ciò che serve per eseguire la richiesta. Se tuttavia è necessario accedere alle funzionalità specifiche di HTTP esposte come proprietà, è possibile eseguire il cast di tipo di queste classi su **HttpWebRequest** o **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="96b8d-105">In most cases, the **WebRequest** and **WebResponse** classes provide all that is necessary to make the request, but if you need access to the HTTP-specific features exposed as properties, you can typecast these classes to **HttpWebRequest** or **HttpWebResponse**.</span></span>  
  
 <span data-ttu-id="96b8d-106">**HttpWebRequest** e **HttpWebResponse** incapsulano una transazione standard di richiesta e risposta HTTP e forniscono l'accesso alle intestazioni HTTP comuni.</span><span class="sxs-lookup"><span data-stu-id="96b8d-106">**HttpWebRequest** and **HttpWebResponse** encapsulate a standard HTTP request-and-response transaction and provide access to common HTTP headers.</span></span> <span data-ttu-id="96b8d-107">Queste classi supportano anche la maggior parte delle funzionalità HTTP 1.1, tra cui pipelining, l'invio e ricezione di dati in blocchi, autenticazione, preautenticazione, crittografia, supporto di proxy, convalida del certificato del server e gestione della connessione.</span><span class="sxs-lookup"><span data-stu-id="96b8d-107">These classes also support most HTTP 1.1 features, including pipelining, sending and receiving data in chunks, authentication, preauthentication, encryption, proxy support, server certificate validation, and connection management.</span></span> <span data-ttu-id="96b8d-108">Le intestazioni personalizzate e le intestazioni non fornite tramite proprietà possono essere archiviate e sono accessibili tramite la proprietà **Headers**.</span><span class="sxs-lookup"><span data-stu-id="96b8d-108">Custom headers and headers not provided through properties can be stored in and accessed through the **Headers** property.</span></span>  
  
 <span data-ttu-id="96b8d-109">**HttpWebRequest** è la classe predefinita usata da **WebRequest** e non deve essere registrata prima di poter passare un URI al metodo **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="96b8d-109">**HttpWebRequest** is the default class used by **WebRequest** and does not need to be registered before you can pass a URI to the **WebRequest.Create** method.</span></span>  
  
 <span data-ttu-id="96b8d-110">È possibile configurare l'applicazione in modo che segua automaticamente i reindirizzamenti HTTP impostando la proprietà <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> su **true** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="96b8d-110">You can make your application follow HTTP redirects automatically by setting the <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> property to **true** (the default).</span></span> <span data-ttu-id="96b8d-111">L'applicazione reindirizzerà le richieste e la proprietà <xref:System.Net.HttpWebResponse.ResponseUri%2A> di **HttpWebResponse** conterrà la risorsa Web effettiva che ha risposto alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="96b8d-111">The application will redirect requests, and the <xref:System.Net.HttpWebResponse.ResponseUri%2A> property of **HttpWebResponse** will contain the actual Web resource that responded to the request.</span></span> <span data-ttu-id="96b8d-112">Se si imposta **AllowAutoRedirect** su **false**, l'applicazione deve essere in grado di gestire i reindirizzamenti come errori del protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="96b8d-112">If you set **AllowAutoRedirect** to **false**, your application must be able to handle redirects as HTTP protocol errors.</span></span>  
  
 <span data-ttu-id="96b8d-113">Le applicazioni ricevono gli errori del protocollo HTTP intercettando una <xref:System.Net.WebException> con la proprietà <xref:System.Net.WebException.Status%2A> impostata <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="96b8d-113">Applications receive HTTP protocol errors by catching a <xref:System.Net.WebException> with the <xref:System.Net.WebException.Status%2A> set to <xref:System.Net.WebExceptionStatus>.</span></span> <span data-ttu-id="96b8d-114">La proprietà <xref:System.Net.WebException.Response%2A> contiene l'oggetto **WebResponse** inviato dal server e indica l'errore HTTP effettivo rilevato.</span><span class="sxs-lookup"><span data-stu-id="96b8d-114">The <xref:System.Net.WebException.Response%2A> property contains the **WebResponse** sent by the server and indicates the actual HTTP error encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b8d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b8d-115">See also</span></span>

- [<span data-ttu-id="96b8d-116">Accesso a Internet tramite un proxy</span><span class="sxs-lookup"><span data-stu-id="96b8d-116">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="96b8d-117">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="96b8d-117">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="96b8d-118">Procedura: Accedere a proprietà specifiche di HTTP</span><span class="sxs-lookup"><span data-stu-id="96b8d-118">How to: Access HTTP-Specific Properties</span></span>](how-to-access-http-specific-properties.md)
