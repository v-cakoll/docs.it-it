---
title: Autorizzazioni Web e socket
description: Informazioni su come le classi WebPermission e SocketPermission forniscono la sicurezza Internet per l'uso dello spazio dei nomi System.Net nel .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
ms.openlocfilehash: 08ae360e8097f7281631da2a3f9846994dfbf5b6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501898"
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="5a10a-103">Autorizzazioni Web e socket</span><span class="sxs-lookup"><span data-stu-id="5a10a-103">Web and Socket Permissions</span></span>
<span data-ttu-id="5a10a-104">La sicurezza Internet per le applicazioni che usano lo spazio dei nomi <xref:System.Net> viene fornita dalle classi <xref:System.Net.WebPermission> e <xref:System.Net.SocketPermission>.</span><span class="sxs-lookup"><span data-stu-id="5a10a-104">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="5a10a-105">La classe **WebPermission** controlla il diritto di un'applicazione di richiedere i dati da un URI o di servire un URI in Internet.</span><span class="sxs-lookup"><span data-stu-id="5a10a-105">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="5a10a-106">La classe **SocketPermission** controlla il diritto di un'applicazione di usare un oggetto <xref:System.Net.Sockets.Socket> per accettare i dati su una porta locale o di contattare i dispositivi remoti usando un protocollo di trasporto in un altro indirizzo, in base all'host, al numero di porta e al protocollo di trasporto del socket.</span><span class="sxs-lookup"><span data-stu-id="5a10a-106">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="5a10a-107">La classe di autorizzazioni da usare dipende dal tipo di applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a10a-107">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="5a10a-108">Le applicazioni che usano <xref:System.Net.WebRequest> e i relativi discendenti devono usare la classe **WebPermission** per gestire le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5a10a-108">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="5a10a-109">Le applicazioni che usano l'accesso a livello di socket devono usare la classe **SocketPermission** per gestire le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5a10a-109">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="5a10a-110">**WebPermission** e **SocketPermission** definiscono due autorizzazioni: accettazione e connessione.</span><span class="sxs-lookup"><span data-stu-id="5a10a-110">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="5a10a-111">L'autorizzazione di accettazione concede all'applicazione il diritto di rispondere a una connessione in ingresso da un'altra entità.</span><span class="sxs-lookup"><span data-stu-id="5a10a-111">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="5a10a-112">L'autorizzazione di connessione concede all'applicazione il diritto di avviare una connessione a un'altra entità.</span><span class="sxs-lookup"><span data-stu-id="5a10a-112">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="5a10a-113">Per le istanze di **SocketPermission**, autorizzazione di accettazione significa che un'applicazione può accettare le connessioni in ingresso su un indirizzo di trasporto locale, mentre autorizzazione di connessione significa che un'applicazione può connettersi a un indirizzo di trasporto remoto (o locale).</span><span class="sxs-lookup"><span data-stu-id="5a10a-113">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="5a10a-114">Per le istanze di **WebPermission**, autorizzazione di accettazione significa che un'applicazione può esportare l'URI controllato da **WebPermission**, mentre autorizzazione di connessione significa che un'applicazione può accedere a tale URI (che sia locale o remoto).</span><span class="sxs-lookup"><span data-stu-id="5a10a-114">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a10a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a10a-115">See also</span></span>

- [<span data-ttu-id="5a10a-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5a10a-116">Security</span></span>](../../standard/security/index.md)
- [<span data-ttu-id="5a10a-117">Sicurezza nella programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="5a10a-117">Security in Network Programming</span></span>](security-in-network-programming.md)
