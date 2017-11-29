---
title: Esempio di integrazione di SystemWebRouting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5050834ff01ebb6a25e746d88f7d328ded505cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="6b412-102">Esempio di integrazione di SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="6b412-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="6b412-103">In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="6b412-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="6b412-104">Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica.</span><span class="sxs-lookup"><span data-stu-id="6b412-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="6b412-105">L'uso del routing Web consente allo sviluppatore di creare indirizzi virtuali per HTTP dei quali viene quindi eseguito il mapping ai servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] effettivi.</span><span class="sxs-lookup"><span data-stu-id="6b412-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="6b412-106">Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx.</span><span class="sxs-lookup"><span data-stu-id="6b412-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="6b412-107">In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax.</span><span class="sxs-lookup"><span data-stu-id="6b412-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> <span data-ttu-id="6b412-108">Per questo esempio vengono usati due feed RSS creati con WCF, ovvero un feed `movies` e un feed `channels`.</span><span class="sxs-lookup"><span data-stu-id="6b412-108">For this example, there are two RSS feeds created using WCF: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="6b412-109">Gli URL per l'attivazione dei servizi non contengono un'estensione e sono registrati nel `Application_Start` metodo il `Global` classe derivata dalla <xref:System.Web.HttpApplication.Application_Start> classe.</span><span class="sxs-lookup"><span data-stu-id="6b412-109">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication.Application_Start> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b412-110">Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.</span><span class="sxs-lookup"><span data-stu-id="6b412-110">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b412-111">Questo esempio può essere usato solo in [!INCLUDE[iisver](../../../../includes/iisver-md.md)], poiché [!INCLUDE[iis60](../../../../includes/iis60-md.md)] usa un metodo diverso per il supporto di URL senza estensione.</span><span class="sxs-lookup"><span data-stu-id="6b412-111">This sample only works in [!INCLUDE[iisver](../../../../includes/iisver-md.md)], as [!INCLUDE[iis60](../../../../includes/iis60-md.md)] uses a different method for supporting extension-less URLs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b412-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6b412-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6b412-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6b412-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6b412-114">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b412-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6b412-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6b412-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6b412-116">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="6b412-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="6b412-117">In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="6b412-117">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="6b412-118">Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.</span><span class="sxs-lookup"><span data-stu-id="6b412-118">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="6b412-119">Verrà aperta la visualizzazione directory per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="6b412-119">A directory listing for the sample appears.</span></span> <span data-ttu-id="6b412-120">Si noti che non sono presenti file con l'estensione di file svc.</span><span class="sxs-lookup"><span data-stu-id="6b412-120">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="6b412-121">Nella barra degli indirizzi aggiungere `movies` all'URL, in modo da ottenere http://localhost:[port]/movies, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="6b412-121">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="6b412-122">Il feed movies verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="6b412-122">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="6b412-123">Nella barra degli indirizzi aggiungere `channels` all'URL, in modo da ottenere http://localhost:[port]/channels, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="6b412-123">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="6b412-124">Il feed channels verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="6b412-124">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="6b412-125">Chiudere il browser premendo ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="6b412-125">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="6b412-126">Se il server di sviluppo non è stato chiuso, l'icona dell'area di notifica e scegliere **arrestare**.</span><span class="sxs-lookup"><span data-stu-id="6b412-126">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="6b412-127">Per usare questo esempio ospitato in IIS</span><span class="sxs-lookup"><span data-stu-id="6b412-127">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="6b412-128">In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="6b412-128">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="6b412-129">Premere CTRL+MAIUSC+B per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="6b412-129">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6b412-130">Creare un'applicazione Web in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="6b412-130">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="6b412-131">In Gestione IIS, fare clic destro la **sito Web predefinito** e selezionare **aggiungere un'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="6b412-131">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="6b412-132">Per il **alias**, digitare `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="6b412-132">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="6b412-133">Per il **percorso fisico**, selezionare la cartella Service all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="6b412-133">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="6b412-134">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b412-134">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="6b412-135">Avviare l'applicazione, facendo l'applicazione Web **Gestione applicazione** e quindi **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="6b412-135">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="6b412-136">Nella barra degli indirizzi aggiungere `movies` all'URL, in modo da ottenere http://localhost:[port]/movies, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="6b412-136">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="6b412-137">Il feed movies verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="6b412-137">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="6b412-138">Nella barra degli indirizzi aggiungere `channels` all'URL, in modo da ottenere http://localhost:[port]/channels, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="6b412-138">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="6b412-139">Il feed channels verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="6b412-139">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="6b412-140">Chiudere il browser premendo ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="6b412-140">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="6b412-141">In questo esempio illustrato come il livello di hosting sia in grado di interagire con le classi nello spazio dei nomi <xref:System.Web.Routing> per l'indirizzamento delle richieste dei servizi ospitati su HTTP.</span><span class="sxs-lookup"><span data-stu-id="6b412-141">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b412-142">Se è impostata sulla versione 2, aggiornare la versione del pool di applicazioni predefinito a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b412-142">Please update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b412-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b412-143">See Also</span></span>  
 [<span data-ttu-id="6b412-144">Hosting di AppFabric ed esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="6b412-144">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
