---
title: "Più endpoint su un solo ListenUri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ffad4-4d47-4430-b7c2-79192ce6bcbd
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 909fb35f9b8e4628df06918f207c3c86770a2d4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="multiple-endpoints-at-a-single-listenuri"></a><span data-ttu-id="66621-102">Più endpoint su un solo ListenUri</span><span class="sxs-lookup"><span data-stu-id="66621-102">Multiple Endpoints at a Single ListenUri</span></span>
<span data-ttu-id="66621-103">In questo esempio viene descritto un servizio che ospita più endpoint in un solo `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="66621-103">This sample demonstrates a service that hosts multiple endpoints at a single `ListenUri`.</span></span> <span data-ttu-id="66621-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="66621-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66621-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="66621-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="66621-106">Come dimostrato nel [più endpoint](../../../../docs/framework/wcf/samples/multiple-endpoints.md) esempio, un servizio può ospitare più endpoint, ognuno con un indirizzo diverso ed eventualmente anche associazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="66621-106">As demonstrated in the [Multiple Endpoints](../../../../docs/framework/wcf/samples/multiple-endpoints.md) sample, a service can host multiple endpoints, each with different addresses and possibly also different bindings.</span></span> <span data-ttu-id="66621-107">Questo esempio mostra che è possibile ospitare più endpoint sullo stesso indirizzo.</span><span class="sxs-lookup"><span data-stu-id="66621-107">This sample shows that it is possible to host multiple endpoints at the same address.</span></span> <span data-ttu-id="66621-108">Questo esempio illustra anche le differenze tra i due tipi di indirizzi che un endpoint del servizio possiede: `EndpointAddress` e `ListenUri`.</span><span class="sxs-lookup"><span data-stu-id="66621-108">This sample also demonstrates the differences between the two kinds of addresses that a service endpoint has: `EndpointAddress` and `ListenUri`.</span></span>  
  
 <span data-ttu-id="66621-109">`EndpointAddress` è l'indirizzo logico del servizio.</span><span class="sxs-lookup"><span data-stu-id="66621-109">The `EndpointAddress` is the logical address of a service.</span></span> <span data-ttu-id="66621-110">È l'indirizzo cui vengono inviati i messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="66621-110">It is the address that SOAP messages are addressed to.</span></span> <span data-ttu-id="66621-111">`ListenUri` è l'indirizzo fisico del servizio.</span><span class="sxs-lookup"><span data-stu-id="66621-111">The `ListenUri` is the physical address of the service.</span></span> <span data-ttu-id="66621-112">Ha una porta e indirizza le informazioni laddove l'endpoint del servizio effettivamente è in ascolto per i messaggi sul computer corrente.</span><span class="sxs-lookup"><span data-stu-id="66621-112">It has the port and address information where the service endpoint actually listens for messages on the current machine.</span></span> <span data-ttu-id="66621-113">Nella maggior parte dei casi, non è necessario che questi indirizzi siano differenti; quando un `ListenUri` non è specificato in modo esplicito, imposta come valore predefinito l'URI dell'`EndpointAddress` dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="66621-113">In most cases, there is no need for these addresses to differ; when a `ListenUri` is not explicitly specified, it defaults to the URI of the `EndpointAddress` of the endpoint.</span></span> <span data-ttu-id="66621-114">In alcuni casi, è utile per distinguerli, ad esempio durante la configurazione di un router che potrebbe accettare messaggi indirizzati a vari servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="66621-114">In a few cases, it is useful to distinguish them, such as when configuring a router, which might accept messages addressed to a number of different services.</span></span>  
  
## <a name="service"></a><span data-ttu-id="66621-115">Service</span><span class="sxs-lookup"><span data-stu-id="66621-115">Service</span></span>  
 <span data-ttu-id="66621-116">Il servizio in questo esempio ha due contratti, `ICalculator` e `IEcho`.</span><span class="sxs-lookup"><span data-stu-id="66621-116">The service in this sample has two contracts, `ICalculator` and `IEcho`.</span></span> <span data-ttu-id="66621-117">Oltre all'endpoint `IMetadataExchange` consueto, sono tre gli endpoint dell'applicazione, come mostra il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="66621-117">In addition to the customary `IMetadataExchange` endpoint, there are three application endpoints, as shown in the following code.</span></span>  
  
```xml  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.ICalculator"   
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"   
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:OtherEcho"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"   
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
```  
  
 <span data-ttu-id="66621-118">Tutti e tre gli endpoint sono ospitati sullo stesso `ListenUri` e utilizzano la stessa `binding`- endpoint sullo stesso `ListenUri` devono avere la stessa associazione, perché condividono un solo stack di canali che ascolta i messaggi su quell'indirizzo fisico del computer.</span><span class="sxs-lookup"><span data-stu-id="66621-118">All three endpoints are hosted at the same `ListenUri` and use the same `binding` - endpoints at the same `ListenUri` must have the same binding, because they are sharing a single channel stack that listens for messages at that physical address on the machine.</span></span> <span data-ttu-id="66621-119">L' `address` di ogni endpoint è un URN; sebbene in genere gli indirizzi rappresentano posizioni fisiche, infatti l'indirizzo può essere qualsiasi tipo di URI, perché l'indirizzo viene utilizzato per far corrispondere e filtrare scopi come è dimostrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="66621-119">The `address` of each endpoint is a URN; though typically addresses represent physical locations, in fact the address can be any kind of URI, because the address is used for matching and filtering purposes as is demonstrated in this sample.</span></span>  
  
 <span data-ttu-id="66621-120">Perché tutti e tre gli endpoint condividono stesso `ListenUri`, quando un messaggio vi arriva, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] deve decidere a quale endpoint è destinato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="66621-120">Because all three endpoints share the same `ListenUri`, when a message arrives there, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] must decide which endpoint the message is destined for.</span></span> <span data-ttu-id="66621-121">Ogni endpoint ha un filtro messaggi composto di due parti: il filtro dell'indirizzo e il filtro del contratto.</span><span class="sxs-lookup"><span data-stu-id="66621-121">Each endpoint has a message filter that is comprised of two parts: the address filter and the contract filter.</span></span> <span data-ttu-id="66621-122">Il filtro dell'indirizzo adegua `To` del messaggio SOAP all'indirizzo dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="66621-122">The address filter matches the `To` of the SOAP message to the address of the service endpoint.</span></span> <span data-ttu-id="66621-123">Ad esempio, solo i messaggi con indirizzo `To "Urn:OtherEcho"` sono candidati per il terzo endpoint di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="66621-123">For example, only messages addressed `To "Urn:OtherEcho"` are candidates for the third endpoint of this service.</span></span> <span data-ttu-id="66621-124">Il filtro del contratto associa le azioni associate alle operazioni di un particolare contratto.</span><span class="sxs-lookup"><span data-stu-id="66621-124">The contract filter matches the Actions associated with the operations of a particular contract.</span></span> <span data-ttu-id="66621-125">Ad esempio, messaggi con l'azione `IEcho`.</span><span class="sxs-lookup"><span data-stu-id="66621-125">For example, messages with the action of `IEcho`.</span></span> <span data-ttu-id="66621-126">`Echo` fa corrispondere i filtri del contratto del secondo e del terzo endpoint di questo servizio, perché entrambi quegli endpoint ospitano il contratto `IEcho`.</span><span class="sxs-lookup"><span data-stu-id="66621-126">`Echo` matches the contract filters of both the second and third endpoints of this service, because both of those endpoints host the `IEcho` contract.</span></span>  
  
 <span data-ttu-id="66621-127">Così la combinazione di filtro dell'indirizzo e filtro del contratto rende possibile il routing di ogni messaggio che arriva al `ListenUri` di questo servizio all'endpoint corretto.</span><span class="sxs-lookup"><span data-stu-id="66621-127">Thus the combination of address filter and contract filter makes it possible to route each message that arrives at this service's `ListenUri` to the correct endpoint.</span></span> <span data-ttu-id="66621-128">Il terzo endpoint è differente dagli altri due perché accetta messaggi inviati a un indirizzo diverso dagli altri endpoint.</span><span class="sxs-lookup"><span data-stu-id="66621-128">The third endpoint is differentiated from the other two because it accepts messages sent to a different address from the other endpoints.</span></span> <span data-ttu-id="66621-129">I primo e secondo endpoint sono diversi uno dall'altro sulla base dei contratti (azione del messaggio in arrivo).</span><span class="sxs-lookup"><span data-stu-id="66621-129">The first and second endpoints are differentiated from each other based on their contracts (the Action of the incoming message).</span></span>  
  
## <a name="client"></a><span data-ttu-id="66621-130">Client</span><span class="sxs-lookup"><span data-stu-id="66621-130">Client</span></span>  
 <span data-ttu-id="66621-131">Nel momento in cui gli endpoint del server hanno due indirizzi diversi, anche gli endpoint client hanno due indirizzi.</span><span class="sxs-lookup"><span data-stu-id="66621-131">Just as endpoints on the server have two different addresses, client endpoints also have two addresses.</span></span> <span data-ttu-id="66621-132">Su server e client, viene chiamato l'indirizzo logico `EndpointAddress`.</span><span class="sxs-lookup"><span data-stu-id="66621-132">On both server and client, the logical address is called the `EndpointAddress`.</span></span> <span data-ttu-id="66621-133">Ma mentre l'indirizzo fisico è chiamato `ListenUri` nel server, sul client l'indirizzo fisico è chiamato `Via`.</span><span class="sxs-lookup"><span data-stu-id="66621-133">But whereas the physical address is called the `ListenUri` on the server, on the client, the physical address is called the `Via`.</span></span>  
  
 <span data-ttu-id="66621-134">Come nel server, per impostazione predefinita, questi due indirizzi sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="66621-134">As on the server, by default, these two addresses are the same.</span></span> <span data-ttu-id="66621-135">Per specificare una `Via` sul client diversa dall'indirizzo dell'endpoint viene utilizzato `ClientViaBehavior`:</span><span class="sxs-lookup"><span data-stu-id="66621-135">To specify a `Via` on the client that is different from the endpoint's address, `ClientViaBehavior` is used:</span></span>  
  
```  
Uri via = new Uri("http://localhost/ServiceModelSamples/service.svc");  
CalculatorClient calcClient = new CalculatorClient();  
calcClient.ChannelFactory.Endpoint.Behaviors.Add(  
        new ClientViaBehavior(via));  
```  
  
 <span data-ttu-id="66621-136">Come al solito, l'indirizzo proviene dal file di configurazione client, generato da Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="66621-136">As usual, the address comes from the client configuration file, which was generated by Svcutil.exe.</span></span> <span data-ttu-id="66621-137">`Via` (che corrisponde a `ListenUri` del servizio) non viene visualizzato nei metadati del servizio e così queste informazioni devono essere comunicate al client fuori banda (proprio come l'indirizzo dei metadati del servizio).</span><span class="sxs-lookup"><span data-stu-id="66621-137">The `Via` (which corresponds to the `ListenUri` of the service) does not appear in the service's metadata and so this information must be communicated to the client out-of-band (just like the service's metadata address).</span></span>  
  
 <span data-ttu-id="66621-138">Il client in questo esempio invia messaggi a ognuno dei tre endpoint dell'applicazione del server, per dimostrare che può comunicare con (e distinguere tra) i tre endpoint, anche se tutti hanno la stessa `Via`.</span><span class="sxs-lookup"><span data-stu-id="66621-138">The client in this sample sends messages to each of the server's three application endpoints, to demonstrate that it can communicate with (and differentiate) all three endpoints, even though they all have the same `Via`.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="66621-139">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="66621-139">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="66621-140">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="66621-140">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="66621-141">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="66621-141">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="66621-142">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="66621-142">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66621-143">Per un'esecuzione a più computer, è necessario sostituire localhost nel file Client.cs con il nome del computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="66621-143">For cross-machine, you must replace localhost in the Client.cs file with the name of the service machine.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66621-144">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="66621-144">The samples may already be installed on your machine.</span></span> <span data-ttu-id="66621-145">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="66621-145">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="66621-146">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66621-146">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="66621-147">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="66621-147">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleEndpointsSingleUri`  
  
## <a name="see-also"></a><span data-ttu-id="66621-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66621-148">See Also</span></span>
