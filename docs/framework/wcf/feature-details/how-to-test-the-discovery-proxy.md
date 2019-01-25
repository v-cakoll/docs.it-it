---
title: 'Procedura: Testare il Proxy di individuazione'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 3c159481813266386706b34d172bbf9614a8253d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590513"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="36fda-102">Procedura: Testare il Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="36fda-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="36fda-103">Di seguito viene illustrato il quarto di quattro argomenti che indica come implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="36fda-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="36fda-104">Nell'argomento precedente, [come: Implementare un'applicazione Client che usa il Proxy di individuazione per cercare un servizio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), è stata implementata un'applicazione client WCF che usa il proxy di individuazione per trovare un servizio e quindi chiama il servizio.</span><span class="sxs-lookup"><span data-stu-id="36fda-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="36fda-105">In questo argomento viene descritto come verificare che il proxy di individuazione, il servizio e l'applicazione client funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="36fda-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="36fda-106">Eseguire il proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="36fda-106">Run the Discovery Proxy</span></span>  
  
1.  <span data-ttu-id="36fda-107">Aprire un prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="36fda-107">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="36fda-108">Potrebbe essere visualizzata una finestra di dialogo che afferma: Windows Firewall ha bloccato alcune funzionalità di questo programma.</span><span class="sxs-lookup"><span data-stu-id="36fda-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="36fda-109">Se viene visualizzato questo messaggio, scegliere il **Unblock** pulsante.</span><span class="sxs-lookup"><span data-stu-id="36fda-109">If you see this message, click the **Unblock** button.</span></span>  
  
3.  <span data-ttu-id="36fda-110">All'interno del prompt dei comandi eseguire il proxy di individuazione (DiscoveryProxy.exe).</span><span class="sxs-lookup"><span data-stu-id="36fda-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4.  <span data-ttu-id="36fda-111">Nell'applicazione viene visualizzato il testo seguente: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="36fda-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="36fda-112">Eseguire il servizio individuabile</span><span class="sxs-lookup"><span data-stu-id="36fda-112">Run the Discoverable Service</span></span>  
  
1.  <span data-ttu-id="36fda-113">Aprire un prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="36fda-113">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="36fda-114">Al prompt dei comandi eseguire il servizio individuabile Service.exe.</span><span class="sxs-lookup"><span data-stu-id="36fda-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3.  <span data-ttu-id="36fda-115">Il DiscoveryProxy.exe viene visualizzato il testo seguente: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="36fda-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="36fda-116">Eseguire l'applicazione client</span><span class="sxs-lookup"><span data-stu-id="36fda-116">Run the Client Application</span></span>  
  
1.  <span data-ttu-id="36fda-117">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="36fda-117">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="36fda-118">Al prompt dei comandi eseguire l'applicazione client.exe.</span><span class="sxs-lookup"><span data-stu-id="36fda-118">Within the command prompt, run the client.exe application.</span></span>  
  
3.  <span data-ttu-id="36fda-119">Dopo alcuni secondi l'applicazione client Visualizza il testo seguente: La connessione a [Endpoint-servizio].</span><span class="sxs-lookup"><span data-stu-id="36fda-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4.  <span data-ttu-id="36fda-120">Il service.exe viene quindi visualizzato il testo seguente: Il messaggio di saluto stata ricevuta una richiesta, risponderà.</span><span class="sxs-lookup"><span data-stu-id="36fda-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5.  <span data-ttu-id="36fda-121">Il client.exe viene quindi visualizzato il testo seguente: Hello Client!</span><span class="sxs-lookup"><span data-stu-id="36fda-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="36fda-122">Chiudere le applicazioni</span><span class="sxs-lookup"><span data-stu-id="36fda-122">Shut Down the Applications</span></span>  
  
1.  <span data-ttu-id="36fda-123">Chiudere l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="36fda-123">Shut down the client application.</span></span>  
  
2.  <span data-ttu-id="36fda-124">Chiudere il servizio.</span><span class="sxs-lookup"><span data-stu-id="36fda-124">Shut down the service.</span></span> <span data-ttu-id="36fda-125">Il proxy di individuazione visualizza il testo seguente: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="36fda-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3.  <span data-ttu-id="36fda-126">Chiudere il proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="36fda-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36fda-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36fda-127">See also</span></span>
- [<span data-ttu-id="36fda-128">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="36fda-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="36fda-129">Procedura: Implementare un Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="36fda-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="36fda-130">Procedura: Implementare un servizio individuabile che esegue la registrazione al Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="36fda-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="36fda-131">Procedura: Implementare un'applicazione Client che usa il Proxy di individuazione per cercare un servizio</span><span class="sxs-lookup"><span data-stu-id="36fda-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
