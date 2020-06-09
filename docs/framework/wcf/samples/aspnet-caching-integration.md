---
title: Integrazione della memorizzazione nella cache di ASP.NET
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: c541f3caad8a500b9fdb33d00b58706bac876e37
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594751"
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="44326-102">Integrazione della memorizzazione nella cache di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="44326-102">ASP.NET Caching Integration</span></span>

<span data-ttu-id="44326-103">In questo esempio viene descritto come usare la cache di output ASP.NET con il modello di programmazione HTTP Web WCF.</span><span class="sxs-lookup"><span data-stu-id="44326-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="44326-104">In questo argomento viene illustrata la funzionalità di integrazione della cache di output ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="44326-104">This topic focuses on the ASP.NET output cache integration feature.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="44326-105">Dimostra</span><span class="sxs-lookup"><span data-stu-id="44326-105">Demonstrates</span></span>

<span data-ttu-id="44326-106">Integrazione con la cache di output ASP.NET</span><span class="sxs-lookup"><span data-stu-id="44326-106">Integration with the ASP.NET Output Cache</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44326-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="44326-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="44326-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="44326-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="44326-109">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="44326-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="44326-110">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="44326-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a><span data-ttu-id="44326-111">Discussione</span><span class="sxs-lookup"><span data-stu-id="44326-111">Discussion</span></span>

<span data-ttu-id="44326-112">Nell'esempio viene utilizzato <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> per utilizzare la memorizzazione nella cache dell'output ASP.NET con il servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="44326-112">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="44326-113"><xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> viene applicato alle operazioni del servizio e fornisce il profilo della cache in un file di configurazione che deve essere applicato alle risposte dell'operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="44326-113">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>

<span data-ttu-id="44326-114">Nel file Service.cs del progetto di servizio di esempio, entrambe le `GetCustomer` `GetCustomers` operazioni e sono contrassegnate con <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> , che fornisce il nome del profilo della cache "CacheFor60Seconds".</span><span class="sxs-lookup"><span data-stu-id="44326-114">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="44326-115">Nel file Web. config del progetto di servizio, il profilo della cache "CacheFor60Seconds" viene fornito nell'elemento < `caching` > di < `system.web` >.</span><span class="sxs-lookup"><span data-stu-id="44326-115">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="44326-116">Per questo profilo di cache, il valore dell' `duration` attributo è "60", quindi le risposte associate a questo profilo vengono memorizzate nella cache di output ASP.NET per 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="44326-116">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="44326-117">Per questo profilo della cache, inoltre, l' `varmByParam` attributo è impostato su "Format", pertanto le risposte alle richieste con valori diversi per il `format` parametro della stringa di query vengono memorizzate nella cache separatamente.</span><span class="sxs-lookup"><span data-stu-id="44326-117">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="44326-118">Infine, l'attributo del profilo della cache `varyByHeader` è impostato su "Accept", pertanto le risposte alle richieste con valori di intestazione Accept diversi sono memorizzate nella cache separatamente.</span><span class="sxs-lookup"><span data-stu-id="44326-118">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>

<span data-ttu-id="44326-119">Il file Program.cs nel progetto Client dimostra come è possibile creare tale client usando <xref:System.Net.HttpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="44326-119">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="44326-120">È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="44326-120">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="44326-121">È anche possibile accedere al servizio utilizzando altre classi .NET Framework come la channel factory WCF e <xref:System.Net.WebClient> .</span><span class="sxs-lookup"><span data-stu-id="44326-121">It is also possible to access the service using other .NET Framework classes like the WCF channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="44326-122">Altri esempi nell'SDK, ad esempio l'esempio di [servizio http di base](basic-http-service.md) , illustrano come usare queste classi per comunicare con un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="44326-122">Other samples in the SDK (such as the [Basic HTTP Service](basic-http-service.md) sample) illustrate how to use these classes to communicate with a WCF service.</span></span>

## <a name="to-run-the-sample"></a><span data-ttu-id="44326-123">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="44326-123">To run the sample</span></span>

<span data-ttu-id="44326-124">L'esempio è costituito da tre progetti:</span><span class="sxs-lookup"><span data-stu-id="44326-124">The sample consists of three projects:</span></span>

- <span data-ttu-id="44326-125">**Servizio**: un progetto di applicazione Web che include un servizio HTTP WCF ospitato in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="44326-125">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>

- <span data-ttu-id="44326-126">**Client**: un progetto di applicazione console che effettua chiamate al servizio.</span><span class="sxs-lookup"><span data-stu-id="44326-126">**Client**: A console application project that makes calls to the service.</span></span>

- <span data-ttu-id="44326-127">**Common**: una libreria condivisa che contiene il tipo di cliente utilizzato dal client e dal servizio.</span><span class="sxs-lookup"><span data-stu-id="44326-127">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>

<span data-ttu-id="44326-128">Quando viene eseguita l'applicazione console Client, il client effettua richieste al servizio e scrive le informazioni pertinenti dalle risposte nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="44326-128">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>

#### <a name="to-run-the-sample"></a><span data-ttu-id="44326-129">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="44326-129">To run the sample</span></span>

1. <span data-ttu-id="44326-130">Aprire la soluzione per l'esempio relativo all'integrazione della memorizzazione nella cache di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="44326-130">Open the solution for the ASP.NET Caching Integration Sample.</span></span>

2. <span data-ttu-id="44326-131">Premere CTRL+MAIUSC+B per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="44326-131">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="44326-132">Se la finestra **Esplora soluzioni** non è già aperta, premere CTRL + W + S.</span><span class="sxs-lookup"><span data-stu-id="44326-132">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>

4. <span data-ttu-id="44326-133">Nella finestra di **Esplora soluzioni** , fare clic con il pulsante destro del mouse sul progetto di **servizio** e scegliere **Avvia nuova istanza**.</span><span class="sxs-lookup"><span data-stu-id="44326-133">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="44326-134">Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.</span><span class="sxs-lookup"><span data-stu-id="44326-134">This launches the ASP.NET development server, which hosts the service.</span></span>

5. <span data-ttu-id="44326-135">Nella finestra di **Esplora soluzioni** , fare clic con il pulsante destro del mouse sul progetto **client** e scegliere **Avvia nuova istanza**.</span><span class="sxs-lookup"><span data-stu-id="44326-135">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>

6. <span data-ttu-id="44326-136">Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44326-136">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="44326-137">In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.</span><span class="sxs-lookup"><span data-stu-id="44326-137">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>

7. <span data-ttu-id="44326-138">Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="44326-138">As the sample runs, the client writes the status of the current activity.</span></span>

8. <span data-ttu-id="44326-139">Premere un tasto qualsiasi per chiudere l'applicazione console client.</span><span class="sxs-lookup"><span data-stu-id="44326-139">Press any key to terminate the client console application.</span></span>

9. <span data-ttu-id="44326-140">Premere MAIUSC+F5 per interrompere il debug del servizio.</span><span class="sxs-lookup"><span data-stu-id="44326-140">Press SHIFT+F5 to stop debugging the service.</span></span>

10. <span data-ttu-id="44326-141">Nell'area di notifica di Windows fare clic con il pulsante destro del mouse sull'icona del server di sviluppo ASP.NET e scegliere **Arresta**.</span><span class="sxs-lookup"><span data-stu-id="44326-141">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
