---
title: 'Procedura: test del proxy di individuazione'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 78921d0a26f1116c87c2931b1472a161d6fed145
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592814"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="f01ff-102">Procedura: test del proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="f01ff-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="f01ff-103">Di seguito viene illustrato il quarto di quattro argomenti che indica come implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="f01ff-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="f01ff-104">Nell'argomento precedente, [procedura: implementare un'applicazione client che utilizza il proxy di individuazione per trovare un servizio](client-app-discovery-proxy-to-find-a-service.md), è stata implementata un'applicazione client WCF che utilizza il proxy di individuazione per trovare un servizio e quindi chiama il servizio.</span><span class="sxs-lookup"><span data-stu-id="f01ff-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="f01ff-105">In questo argomento viene descritto come verificare che il proxy di individuazione, il servizio e l'applicazione client funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="f01ff-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="f01ff-106">Eseguire il proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="f01ff-106">Run the Discovery Proxy</span></span>  
  
1. <span data-ttu-id="f01ff-107">Aprire un prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="f01ff-107">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="f01ff-108">È possibile che venga visualizzata una finestra di dialogo con il testo seguente: Windows Firewall ha bloccato alcune funzionalità del programma.</span><span class="sxs-lookup"><span data-stu-id="f01ff-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="f01ff-109">Se viene visualizzato questo messaggio, fare clic sul pulsante **Sblocca** .</span><span class="sxs-lookup"><span data-stu-id="f01ff-109">If you see this message, click the **Unblock** button.</span></span>  
  
3. <span data-ttu-id="f01ff-110">All'interno del prompt dei comandi eseguire il proxy di individuazione (DiscoveryProxy.exe).</span><span class="sxs-lookup"><span data-stu-id="f01ff-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4. <span data-ttu-id="f01ff-111">Nell'applicazione viene visualizzato il testo seguente: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="f01ff-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="f01ff-112">Eseguire il servizio individuabile</span><span class="sxs-lookup"><span data-stu-id="f01ff-112">Run the Discoverable Service</span></span>  
  
1. <span data-ttu-id="f01ff-113">Aprire un prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="f01ff-113">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="f01ff-114">Al prompt dei comandi eseguire il servizio individuabile Service.exe.</span><span class="sxs-lookup"><span data-stu-id="f01ff-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3. <span data-ttu-id="f01ff-115">DiscoveryProxy. exe deve visualizzare il testo seguente: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="f01ff-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="f01ff-116">Eseguire l'applicazione client</span><span class="sxs-lookup"><span data-stu-id="f01ff-116">Run the Client Application</span></span>  
  
1. <span data-ttu-id="f01ff-117">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f01ff-117">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="f01ff-118">Al prompt dei comandi eseguire l'applicazione client.exe.</span><span class="sxs-lookup"><span data-stu-id="f01ff-118">Within the command prompt, run the client.exe application.</span></span>  
  
3. <span data-ttu-id="f01ff-119">Dopo alcuni secondi nell'applicazione client viene visualizzato il testo seguente: Connessione a [Endpoint-servizio] in corso.</span><span class="sxs-lookup"><span data-stu-id="f01ff-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4. <span data-ttu-id="f01ff-120">In Service.exe viene quindi visualizzato il testo seguente: Greeting request received, I will respond.</span><span class="sxs-lookup"><span data-stu-id="f01ff-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5. <span data-ttu-id="f01ff-121">In Client.exe viene quindi visualizzato il testo seguente: Hello Client!</span><span class="sxs-lookup"><span data-stu-id="f01ff-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="f01ff-122">Chiudere le applicazioni</span><span class="sxs-lookup"><span data-stu-id="f01ff-122">Shut Down the Applications</span></span>  
  
1. <span data-ttu-id="f01ff-123">Chiudere l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="f01ff-123">Shut down the client application.</span></span>  
  
2. <span data-ttu-id="f01ff-124">Chiudere il servizio.</span><span class="sxs-lookup"><span data-stu-id="f01ff-124">Shut down the service.</span></span> <span data-ttu-id="f01ff-125">Il proxy di individuazione visualizza il testo seguente: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="f01ff-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3. <span data-ttu-id="f01ff-126">Chiudere il proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="f01ff-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01ff-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f01ff-127">See also</span></span>

- [<span data-ttu-id="f01ff-128">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="f01ff-128">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="f01ff-129">Procedura: implementare un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="f01ff-129">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="f01ff-130">Procedura: implementare un servizio individuabile che esegue la registrazione al proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="f01ff-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="f01ff-131">Procedura: implementare un'applicazione client che usa il proxy di individuazione per cercare un servizio</span><span class="sxs-lookup"><span data-stu-id="f01ff-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
