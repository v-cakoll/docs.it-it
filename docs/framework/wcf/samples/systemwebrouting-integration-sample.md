---
title: Esempio di integrazione di SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 95372d6052690af30042061d623b6004699c21d9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779445"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="cedf5-102">Esempio di integrazione di SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="cedf5-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="cedf5-103">In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="cedf5-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="cedf5-104">Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica.</span><span class="sxs-lookup"><span data-stu-id="cedf5-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="cedf5-105">Uso del routing Web consente allo sviluppatore di creare indirizzi virtuali per il protocollo HTTP che vengono quindi rimappata alla effettivi dei servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="cedf5-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="cedf5-106">Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx.</span><span class="sxs-lookup"><span data-stu-id="cedf5-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="cedf5-107">In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax.</span><span class="sxs-lookup"><span data-stu-id="cedf5-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
>  <span data-ttu-id="cedf5-108">Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.</span><span class="sxs-lookup"><span data-stu-id="cedf5-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="cedf5-109">In questo esempio utilizza WCF per creare due feed RSS: una `movies` feed e un `channels` feed.</span><span class="sxs-lookup"><span data-stu-id="cedf5-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="cedf5-110">Gli URL per attivare i servizi non contengono un'estensione e vengono registrati nel `Application_Start` metodo per il `Global` classe derivata dal <xref:System.Web.HttpApplication> classe.</span><span class="sxs-lookup"><span data-stu-id="cedf5-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cedf5-111">In questo esempio funziona solo in Internet Information Services (IIS) 7.0 e versioni successive, come IIS 6.0 usa un metodo diverso per il supporto di URL senza estensione.</span><span class="sxs-lookup"><span data-stu-id="cedf5-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="cedf5-112">Per scaricare questo esempio</span><span class="sxs-lookup"><span data-stu-id="cedf5-112">To download this sample</span></span>
  
<span data-ttu-id="cedf5-113">In questo esempio potrebbe essere già installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="cedf5-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="cedf5-114">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="cedf5-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="cedf5-115">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="cedf5-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cedf5-116">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="cedf5-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="cedf5-117">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="cedf5-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="cedf5-118">Usa Visual Studio, aprire il file Webroutingintegration.</span><span class="sxs-lookup"><span data-stu-id="cedf5-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="cedf5-119">Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.</span><span class="sxs-lookup"><span data-stu-id="cedf5-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="cedf5-120">Verrà aperta la visualizzazione directory per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="cedf5-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="cedf5-121">Si noti che non sono presenti file con l'estensione di file svc.</span><span class="sxs-lookup"><span data-stu-id="cedf5-121">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="cedf5-122">Nella barra degli indirizzi, aggiungere `movies` all'URL, in modo che venga legge `http://localhost:[port]/movies` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cedf5-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="cedf5-123">Il feed movies verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="cedf5-123">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="cedf5-124">Nella barra degli indirizzi, aggiungere `channels` all'URL, ecco le letture `http://localhost:[port]/channels` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cedf5-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="cedf5-125">Il feed channels verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="cedf5-125">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="cedf5-126">Chiudere il browser premendo ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="cedf5-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="cedf5-127">Se il server di sviluppo non viene chiuso, fare doppio clic sull'icona di area di notifica e selezionare **arrestare**.</span><span class="sxs-lookup"><span data-stu-id="cedf5-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="cedf5-128">Per usare questo esempio ospitato in IIS</span><span class="sxs-lookup"><span data-stu-id="cedf5-128">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="cedf5-129">Usa Visual Studio, aprire il file Webroutingintegration.</span><span class="sxs-lookup"><span data-stu-id="cedf5-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="cedf5-130">Premere CTRL+MAIUSC+B per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="cedf5-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="cedf5-131">Creare un'applicazione Web in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="cedf5-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="cedf5-132">Fare clic in Gestione IIS, il **sito Web predefinito** e selezionare **aggiungere un'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="cedf5-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="cedf5-133">Per il **alias**, digitare `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="cedf5-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="cedf5-134">Per il **percorso fisico**, selezionare la cartella Service all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="cedf5-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="cedf5-135">Premere **OK**.</span><span class="sxs-lookup"><span data-stu-id="cedf5-135">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="cedf5-136">Avviare l'applicazione, facendo clic all'applicazione Web e selezionando **Gestione applicazioni** e quindi **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="cedf5-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="cedf5-137">Nella barra degli indirizzi, aggiungere `movies` all'URL, ecco le letture `http://localhost:[port]/movies` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cedf5-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="cedf5-138">Il feed movies verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="cedf5-138">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="cedf5-139">Nella barra degli indirizzi, aggiungere `channels` all'URL, ecco le letture `http://localhost:[port]/channels` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cedf5-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="cedf5-140">Il feed channels verrà visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="cedf5-140">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="cedf5-141">Chiudere il browser premendo ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="cedf5-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="cedf5-142">In questo esempio illustrato come il livello di hosting sia in grado di interagire con le classi nello spazio dei nomi <xref:System.Web.Routing> per l'indirizzamento delle richieste dei servizi ospitati su HTTP.</span><span class="sxs-lookup"><span data-stu-id="cedf5-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cedf5-143">È necessario aggiornare la versione predefinita dell'applicazione del pool per [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] se è impostata per la versione 2.</span><span class="sxs-lookup"><span data-stu-id="cedf5-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cedf5-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cedf5-144">See Also</span></span>  
 [<span data-ttu-id="cedf5-145">Hosting di AppFabric e salvataggio permanente</span><span class="sxs-lookup"><span data-stu-id="cedf5-145">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
