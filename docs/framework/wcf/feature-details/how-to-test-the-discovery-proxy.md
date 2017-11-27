---
title: 'Procedura: test del proxy di individuazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f9c721a0ef357feeb4df540cb5b7b74d067dc807
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="21ce5-102">Procedura: test del proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="21ce5-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="21ce5-103">Di seguito viene illustrato il quarto di quattro argomenti che indica come implementare un proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="21ce5-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="21ce5-104">Nell'argomento precedente, [procedura: implementare un'applicazione Client che utilizza il Proxy di individuazione per trovare un servizio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), è implementato un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applicazione client che utilizza il proxy di individuazione per trovare un servizio e quindi chiama il servizio.</span><span class="sxs-lookup"><span data-stu-id="21ce5-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="21ce5-105">In questo argomento viene descritto come verificare che il proxy di individuazione, il servizio e l'applicazione client funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="21ce5-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="21ce5-106">Eseguire il proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="21ce5-106">Run the Discovery Proxy</span></span>  
  
1.  <span data-ttu-id="21ce5-107">Aprire un prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="21ce5-107">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="21ce5-108">È possibile che venga visualizzata una finestra di dialogo con il testo seguente: Windows Firewall ha bloccato alcune funzionalità del programma.</span><span class="sxs-lookup"><span data-stu-id="21ce5-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="21ce5-109">Se viene visualizzato questo messaggio, fare clic su di **Unblock** pulsante.</span><span class="sxs-lookup"><span data-stu-id="21ce5-109">If you see this message, click the **Unblock** button.</span></span>  
  
3.  <span data-ttu-id="21ce5-110">All'interno del prompt dei comandi eseguire il proxy di individuazione (DiscoveryProxy.exe).</span><span class="sxs-lookup"><span data-stu-id="21ce5-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4.  <span data-ttu-id="21ce5-111">Nell'applicazione viene visualizzato il testo seguente: `Proxy started. Hit Enter to exit`.</span><span class="sxs-lookup"><span data-stu-id="21ce5-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="21ce5-112">Eseguire il servizio individuabile</span><span class="sxs-lookup"><span data-stu-id="21ce5-112">Run the Discoverable Service</span></span>  
  
1.  <span data-ttu-id="21ce5-113">Aprire un prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="21ce5-113">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="21ce5-114">Al prompt dei comandi eseguire il servizio individuabile Service.exe.</span><span class="sxs-lookup"><span data-stu-id="21ce5-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3.  <span data-ttu-id="21ce5-115">Il DiscoveryProxy.exe viene visualizzato il testo seguente: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span><span class="sxs-lookup"><span data-stu-id="21ce5-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="21ce5-116">Eseguire l'applicazione client</span><span class="sxs-lookup"><span data-stu-id="21ce5-116">Run the Client Application</span></span>  
  
1.  <span data-ttu-id="21ce5-117">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="21ce5-117">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="21ce5-118">Al prompt dei comandi eseguire l'applicazione client.exe.</span><span class="sxs-lookup"><span data-stu-id="21ce5-118">Within the command prompt, run the client.exe application.</span></span>  
  
3.  <span data-ttu-id="21ce5-119">Dopo alcuni secondi nell'applicazione client viene visualizzato il testo seguente: Connessione a [Endpoint-servizio] in corso.</span><span class="sxs-lookup"><span data-stu-id="21ce5-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4.  <span data-ttu-id="21ce5-120">In Service.exe viene quindi visualizzato il testo seguente: Greeting request received, I will respond.</span><span class="sxs-lookup"><span data-stu-id="21ce5-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5.  <span data-ttu-id="21ce5-121">In Client.exe viene quindi visualizzato il testo seguente: Hello Client!</span><span class="sxs-lookup"><span data-stu-id="21ce5-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="21ce5-122">Chiudere le applicazioni</span><span class="sxs-lookup"><span data-stu-id="21ce5-122">Shut Down the Applications</span></span>  
  
1.  <span data-ttu-id="21ce5-123">Chiudere l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="21ce5-123">Shut down the client application.</span></span>  
  
2.  <span data-ttu-id="21ce5-124">Chiudere il servizio.</span><span class="sxs-lookup"><span data-stu-id="21ce5-124">Shut down the service.</span></span> <span data-ttu-id="21ce5-125">Il proxy di individuazione visualizza il testo seguente: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span><span class="sxs-lookup"><span data-stu-id="21ce5-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3.  <span data-ttu-id="21ce5-126">Chiudere il proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="21ce5-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ce5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21ce5-127">See Also</span></span>  
 [<span data-ttu-id="21ce5-128">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="21ce5-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="21ce5-129">Procedura: implementare un Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="21ce5-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [<span data-ttu-id="21ce5-130">Procedura: implementare un servizio individuabile che esegue la registrazione con il Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="21ce5-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [<span data-ttu-id="21ce5-131">Procedura: implementare un'applicazione Client che utilizza il Proxy di individuazione per trovare un servizio</span><span class="sxs-lookup"><span data-stu-id="21ce5-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
