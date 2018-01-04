---
title: Integrazione della memorizzazione nella cache di ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d56c435088be383821d17250e230cae848d2bab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="c8f7d-102">Integrazione della memorizzazione nella cache di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c8f7d-102">ASP.NET Caching Integration</span></span>
<span data-ttu-id="c8f7d-103">In questo esempio viene descritto come usare la cache di output ASP.NET con il modello di programmazione HTTP Web WCF.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="c8f7d-104">Vedere il [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio per una versione indipendente di questo scenario che illustra l'implementazione del servizio in modo approfondito.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-104">Please see the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample for a self-hosted version of this scenario that discusses the service implementation in depth.</span></span> <span data-ttu-id="c8f7d-105">In questo argomento viene illustrata la funzionalità di integrazione della cache di output ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-105">This topic focuses on the ASP.NET output cache integration feature.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="c8f7d-106">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="c8f7d-106">Demonstrates</span></span>  
 <span data-ttu-id="c8f7d-107">Integrazione con la cache di output ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c8f7d-107">Integration with the ASP.NET Output Cache</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c8f7d-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c8f7d-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c8f7d-110">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8f7d-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c8f7d-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a><span data-ttu-id="c8f7d-112">Discussione</span><span class="sxs-lookup"><span data-stu-id="c8f7d-112">Discussion</span></span>  
 <span data-ttu-id="c8f7d-113">Nell'esempio viene usato <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> per la memorizzazione nella cache di output ASP.NET con il servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8f7d-113">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="c8f7d-114"><xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> viene applicato alle operazioni del servizio e fornisce il profilo della cache in un file di configurazione che deve essere applicato alle risposte dell'operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-114">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>  
  
 <span data-ttu-id="c8f7d-115">Nel file Service.cs del progetto di servizio di esempio, sia il `GetCustomer` e `GetCustomers` operazioni sono contrassegnate con il <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, che fornisce il nome del profilo della cache "CacheFor60Seconds".</span><span class="sxs-lookup"><span data-stu-id="c8f7d-115">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="c8f7d-116">Nel file Web. config del progetto del servizio, il profilo della cache "CacheFor60Seconds" viene fornito con il <`caching`> dell'elemento di <`system.web`>.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-116">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="c8f7d-117">Per questo profilo di cache, il valore di `duration` attributo è "60", pertanto le risposte associate a questo profilo vengono memorizzati nella cache nella cache di output ASP.NET per 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-117">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="c8f7d-118">Inoltre, per questo profilo di cache di `varmByParam` attributo è impostato su "format" in questo caso richieste con valori diversi per il `format` query parametro stringa hanno le risposte memorizzate nella cache separatamente.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-118">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="c8f7d-119">Del infine, il profilo della cache `varyByHeader` attributo è impostato su "Accetto", in modo che le richieste con valori di intestazione Accept diversi delle risposte memorizzate nella cache separatamente.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-119">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>  
  
 <span data-ttu-id="c8f7d-120">Il file Program.cs nel progetto Client dimostra come è possibile creare tale client usando <xref:System.Net.HttpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-120">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="c8f7d-121">È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-121">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="c8f7d-122">È infatti possibile accedere al servizio usando altre classi .NET Framework come la channel factory [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-122">It is also possible to access the service using other .NET Framework classes like the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="c8f7d-123">Altri esempi in SDK (ad esempio il [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) esempio e [la selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) esempio) viene illustrato come utilizzare queste classi per comunicare con un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-123">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample and the [Automatic Format Selection](../../../../docs/framework/wcf/samples/automatic-format-selection.md) sample) illustrate how to use these classes to communicate with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
## <a name="to-run-the-sample"></a><span data-ttu-id="c8f7d-124">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="c8f7d-124">To run the sample</span></span>  
 <span data-ttu-id="c8f7d-125">L'esempio è costituito da tre progetti:</span><span class="sxs-lookup"><span data-stu-id="c8f7d-125">The sample consists of three projects:</span></span>  
  
-   <span data-ttu-id="c8f7d-126">**Servizio**: progetto Web che include un servizio WCF HTTP ospitato in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-126">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>  
  
-   <span data-ttu-id="c8f7d-127">**Client**: un progetto di applicazione console che effettua chiamate al servizio.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-127">**Client**: A console application project that makes calls to the service.</span></span>  
  
-   <span data-ttu-id="c8f7d-128">**Comuni**: una libreria condivisa che contiene il tipo Customer usato dal client e servizio.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-128">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>  
  
 <span data-ttu-id="c8f7d-129">Quando viene eseguita l'applicazione console Client, il client effettua richieste al servizio e scrive le informazioni pertinenti dalle risposte nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-129">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="c8f7d-130">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="c8f7d-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="c8f7d-131">Aprire la soluzione per l'esempio relativo all'integrazione della memorizzazione nella cache di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-131">Open the solution for the ASP.NET Caching Integration Sample.</span></span>  
  
2.  <span data-ttu-id="c8f7d-132">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="c8f7d-133">Se il **Esplora** finestra non è già aperta, premere CTRL + W + S.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-133">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>  
  
4.  <span data-ttu-id="c8f7d-134">Dal **Esplora** finestra fare clic destro la **servizio** del progetto e selezionare **Avvia nuova istanza**.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-134">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="c8f7d-135">Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-135">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="c8f7d-136">Dal **Esplora** finestra fare clic destro la **Client** del progetto e selezionare **Avvia nuova istanza**.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-136">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="c8f7d-137">Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-137">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="c8f7d-138">In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-138">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7.  <span data-ttu-id="c8f7d-139">Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-139">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8.  <span data-ttu-id="c8f7d-140">Premere un tasto qualsiasi per chiudere l'applicazione console client.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-140">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="c8f7d-141">Premere MAIUSC+F5 per interrompere il debug del servizio.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-141">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="c8f7d-142">Nell'Area di notifica Windows, fare clic sull'icona del server di sviluppo ASP.NET e selezionare **arrestare**.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-142">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
