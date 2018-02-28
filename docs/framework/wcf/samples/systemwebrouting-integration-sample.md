---
title: Esempio di integrazione di SystemWebRouting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: de8869956a59cb47623dbc4d84763e19d6f181bf
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="a3f0d-102">Esempio di integrazione di SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="a3f0d-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="a3f0d-103">In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="a3f0d-104">Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="a3f0d-105">L'uso del routing Web consente allo sviluppatore di creare indirizzi virtuali per HTTP dei quali viene quindi eseguito il mapping ai servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] effettivi.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="a3f0d-106">Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="a3f0d-107">In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
>  <span data-ttu-id="a3f0d-108">Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="a3f0d-109">In questo esempio vengono usati WCF per creare due feed RSS: un `movies` feed e un `channels` feed.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="a3f0d-110">Gli URL per l'attivazione dei servizi non contengono un'estensione e sono registrati nel `Application_Start` metodo il `Global` classe derivata dalla <xref:System.Web.HttpApplication> classe.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3f0d-111">Questo esempio funziona solo in Internet Information Services (IIS) 7.0 e versioni successive, come IIS 6.0 utilizza un metodo diverso per il supporto di URL senza estensione.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="a3f0d-112">Per scaricare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a3f0d-112">To download this sample</span></span>
  
<span data-ttu-id="a3f0d-113">In questo esempio siano già installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="a3f0d-114">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="a3f0d-115">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3f0d-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a3f0d-116">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a3f0d-117">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a3f0d-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="a3f0d-118">Utilizzando Visual Studio, aprire il file WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="a3f0d-119">Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="a3f0d-120">Verrà aperta la visualizzazione directory per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="a3f0d-121">Si noti che non sono presenti file con l'estensione di file svc.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-121">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="a3f0d-122">Nella barra degli indirizzi, aggiungere `movies` all'URL, in modo che legge http://localhost: [port] /Movies, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-122">In the address bar, add `movies` to the URL, so that it reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="a3f0d-123">Il feed movies verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-123">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="a3f0d-124">Nella barra degli indirizzi aggiungere `channels` all'URL, in modo da ottenere http://localhost:[port]/channels, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-124">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="a3f0d-125">Il feed channels verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-125">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="a3f0d-126">Chiudere il browser premendo ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="a3f0d-127">Se il server di sviluppo non è stato chiuso, l'icona dell'area di notifica e scegliere **arrestare**.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="a3f0d-128">Per usare questo esempio ospitato in IIS</span><span class="sxs-lookup"><span data-stu-id="a3f0d-128">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="a3f0d-129">Utilizzando Visual Studio, aprire il file WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="a3f0d-130">Premere CTRL+MAIUSC+B per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a3f0d-131">Creare un'applicazione Web in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a3f0d-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="a3f0d-132">In Gestione IIS, fare clic destro la **sito Web predefinito** e selezionare **aggiungere un'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="a3f0d-133">Per il **alias**, digitare `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="a3f0d-134">Per il **percorso fisico**, selezionare la cartella Service all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="a3f0d-135">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-135">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="a3f0d-136">Avviare l'applicazione, facendo l'applicazione Web **Gestione applicazione** e quindi **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="a3f0d-137">Nella barra degli indirizzi aggiungere `movies` all'URL, in modo da ottenere http://localhost:[port]/movies, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-137">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="a3f0d-138">Il feed movies verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-138">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="a3f0d-139">Nella barra degli indirizzi aggiungere `channels` all'URL, in modo da ottenere http://localhost:[port]/channels, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-139">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="a3f0d-140">Il feed channels verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-140">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="a3f0d-141">Chiudere il browser premendo ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="a3f0d-142">In questo esempio illustrato come il livello di hosting sia in grado di interagire con le classi nello spazio dei nomi <xref:System.Web.Routing> per l'indirizzamento delle richieste dei servizi ospitati su HTTP.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3f0d-143">È necessario aggiornare la versione di pool di applicazioni predefinita da [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] se è impostato per la versione 2.</span><span class="sxs-lookup"><span data-stu-id="a3f0d-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f0d-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3f0d-144">See Also</span></span>  
 [<span data-ttu-id="a3f0d-145">Hosting di AppFabric ed esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="a3f0d-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
