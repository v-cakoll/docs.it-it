---
title: Filtri avanzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a9d7ce5029e0f5b95b98dd4f44e42f6c07bb8e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="advanced-filters"></a><span data-ttu-id="dac10-102">Filtri avanzati</span><span class="sxs-lookup"><span data-stu-id="dac10-102">Advanced Filters</span></span>
<span data-ttu-id="dac10-103">Nell'esempio viene descritto un servizio di routing di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dac10-103">This sample demonstrates a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="dac10-104">Il servizio di routing è un componente di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che semplifica l'aggiunta nell'applicazione di un router basato sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="dac10-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="dac10-105">L'esempio adatta l'esempio standard relativo alla calcolatrice di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per comunicazioni tramite il servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="dac10-105">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator sample to communicate using the routing service.</span></span> <span data-ttu-id="dac10-106">In questo esempio viene illustrato come definire la logica di routing basata sul contenuto tramite l'utilizzo di filtri messaggi e tabelle dei filtri messaggi.</span><span class="sxs-lookup"><span data-stu-id="dac10-106">This sample shows how to define content-based routing logic through the use of message filters and message filter tables.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dac10-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dac10-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dac10-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="dac10-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dac10-109">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dac10-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dac10-110">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="dac10-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## <a name="sample-details"></a><span data-ttu-id="dac10-111">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="dac10-111">Sample Details</span></span>  
 <span data-ttu-id="dac10-112">Nella tabella seguente vengono mostrati i filtri messaggi aggiunti alla tabella dei filtri messaggi del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="dac10-112">The following table shows the message filters that are added to the message filter table of the routing service.</span></span>  
  
|<span data-ttu-id="dac10-113">Filtro</span><span class="sxs-lookup"><span data-stu-id="dac10-113">Filter</span></span>|<span data-ttu-id="dac10-114">Regola</span><span class="sxs-lookup"><span data-stu-id="dac10-114">Rule</span></span>|<span data-ttu-id="dac10-115">Priorità</span><span class="sxs-lookup"><span data-stu-id="dac10-115">Priority</span></span>|  
|------------|----------|--------------|  
|<span data-ttu-id="dac10-116">If (dispone di intestazione)</span><span class="sxs-lookup"><span data-stu-id="dac10-116">If (has header)</span></span>|<span data-ttu-id="dac10-117">Rounding</span><span class="sxs-lookup"><span data-stu-id="dac10-117">Rounding</span></span>|<span data-ttu-id="dac10-118">2</span><span class="sxs-lookup"><span data-stu-id="dac10-118">2</span></span>|  
|<span data-ttu-id="dac10-119">If (mostrato in Ep2)</span><span class="sxs-lookup"><span data-stu-id="dac10-119">If (showed up on Ep2)</span></span>|<span data-ttu-id="dac10-120">Regular</span><span class="sxs-lookup"><span data-stu-id="dac10-120">Regular</span></span>|<span data-ttu-id="dac10-121">1</span><span class="sxs-lookup"><span data-stu-id="dac10-121">1</span></span>|  
|<span data-ttu-id="dac10-122">If (mostrato con Address2)</span><span class="sxs-lookup"><span data-stu-id="dac10-122">If (showed up with Address2)</span></span>|<span data-ttu-id="dac10-123">Rounding</span><span class="sxs-lookup"><span data-stu-id="dac10-123">Rounding</span></span>|<span data-ttu-id="dac10-124">1</span><span class="sxs-lookup"><span data-stu-id="dac10-124">1</span></span>|  
|<span data-ttu-id="dac10-125">If (RoundRobin1)</span><span class="sxs-lookup"><span data-stu-id="dac10-125">If (RoundRobin1)</span></span>|<span data-ttu-id="dac10-126">Regular</span><span class="sxs-lookup"><span data-stu-id="dac10-126">Regular</span></span>|<span data-ttu-id="dac10-127">0</span><span class="sxs-lookup"><span data-stu-id="dac10-127">0</span></span>|  
|<span data-ttu-id="dac10-128">If (RoundRobin2)</span><span class="sxs-lookup"><span data-stu-id="dac10-128">If (RoundRobin2)</span></span>|<span data-ttu-id="dac10-129">Rounding</span><span class="sxs-lookup"><span data-stu-id="dac10-129">Rounding</span></span>|<span data-ttu-id="dac10-130">0</span><span class="sxs-lookup"><span data-stu-id="dac10-130">0</span></span>|  
  
 <span data-ttu-id="dac10-131">I filtri messaggi e le tabelle dei filtri messaggi possono essere creati e configurati tramite codice o nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dac10-131">The message filters and message filter tables can be created and configured either through code or in the application configuration file.</span></span> <span data-ttu-id="dac10-132">Per questo esempio, è possibile trovare i filtri messaggi e le tabelle dei filtri messaggi definiti tramite codice nel file RoutingService\routing.cs o definiti nel file di configurazione dell'applicazione nel file RoutingService\App.config.</span><span class="sxs-lookup"><span data-stu-id="dac10-132">For this sample, you can find the message filters and message filter tables defined through code in the RoutingService\routing.cs file, or defined in the application configuration file in the RoutingService\App.config file.</span></span> <span data-ttu-id="dac10-133">Nei paragrafi seguenti viene descritta la creazione tramite codice di filtri messaggi e di tabelle dei filtri messaggi per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="dac10-133">The following paragraphs describe how the message filters and message filter tables are created for this sample through code.</span></span>  
  
 <span data-ttu-id="dac10-134">In primo luogo, <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> effettua la ricerca dell'intestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dac10-134">First, an <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> looks for the custom header.</span></span> <span data-ttu-id="dac10-135">Si noti che <xref:System.ServiceModel.WSHttpBinding> determina una versione envelope che utilizza SOAP 1.2, pertanto l'istruzione XPath è definita per utilizzare lo spazio dei nomi di SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="dac10-135">Note that <xref:System.ServiceModel.WSHttpBinding> results in an envelope version using SOAP 1.2, so the XPath statement is defined to use the SOAP 1.2 namespace.</span></span> <span data-ttu-id="dac10-136">Il gestore dello spazio dei nomi predefinito per <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> definisce già un prefisso per lo spazio dei nomi di SOAP 1.2, /s12, che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="dac10-136">The default namespace manager for <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>s already defines a prefix for the SOAP 1.2 namespace, /s12, which can be used.</span></span> <span data-ttu-id="dac10-137">Tuttavia, il gestore dello spazio dei nomi predefinito non dispone dello spazio dei nomi personalizzato utilizzato dal client per definire il valore dell'intestazione effettivo, pertanto il prefisso deve essere definito.</span><span class="sxs-lookup"><span data-stu-id="dac10-137">However, the default namespace manager does not have the custom namespace that the client uses to define the actual header value, so that prefix must be defined.</span></span> <span data-ttu-id="dac10-138">Qualsiasi messaggio visualizzato con questa intestazione corrisponde al filtro.</span><span class="sxs-lookup"><span data-stu-id="dac10-138">Any message that shows up with this header matches this filter.</span></span>  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
```  
  
 <span data-ttu-id="dac10-139">Il secondo filtro è un oggetto <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, che corrisponde a qualsiasi messaggio ricevuto nell'oggetto `calculatorEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="dac10-139">The second filter is an <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, which matches any message that was received on the `calculatorEndpoint`.</span></span> <span data-ttu-id="dac10-140">Il nome dell'endpoint viene definito quando viene creato un oggetto endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="dac10-140">The endpoint name is defined when a service endpoint object is created.</span></span>  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
```  
  
 <span data-ttu-id="dac10-141">Il terzo filtro è un oggetto <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="dac10-141">The third filter is a <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>.</span></span> <span data-ttu-id="dac10-142">Corrisponde a qualsiasi messaggio visualizzato in un endpoint con un indirizzo che corrisponde al prefisso dell'indirizzo fornito (o alla prima parte di tale indirizzo).</span><span class="sxs-lookup"><span data-stu-id="dac10-142">This matches any message that showed up on an endpoint with an address that matches the address prefix (or the front portion) provided.</span></span> <span data-ttu-id="dac10-143">In questo esempio il prefisso dell'indirizzo è definito come "http://localhost/routingservice/router/rounding/".</span><span class="sxs-lookup"><span data-stu-id="dac10-143">In this example the address prefix is defined as "http://localhost/routingservice/router/rounding/".</span></span> <span data-ttu-id="dac10-144">Ciò significa che per qualsiasi messaggio in arrivo indirizzato a "http://localhost/routingservice/router/rounding/*" viene individuata una corrispondenza da parte di tale filtro.</span><span class="sxs-lookup"><span data-stu-id="dac10-144">This means that any incoming messages that are addressed to "http://localhost/routingservice/router/rounding/*" are matched by this filter.</span></span> <span data-ttu-id="dac10-145">In questo caso, si tratta di messaggi visualizzati nell'endpoint del servizio di calcolo che esegue l'arrotondamento e che dispone dell'indirizzo "http://localhost/routingservice/router/rounding/calculator".</span><span class="sxs-lookup"><span data-stu-id="dac10-145">In this case, it is messages that show up on the Rounding Calculator endpoint, which has the address of "http://localhost/routingservice/router/rounding/calculator".</span></span>  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
```  
  
 <span data-ttu-id="dac10-146">Gli ultimi due filtri messaggi sono oggetti <xref:System.ServiceModel.Dispatcher.MessageFilter> personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dac10-146">The last two message filters are custom <xref:System.ServiceModel.Dispatcher.MessageFilter>s.</span></span> <span data-ttu-id="dac10-147">In questo esempio, viene utilizzato un filtro messaggi "RoundRobin".</span><span class="sxs-lookup"><span data-stu-id="dac10-147">In this example, a "RoundRobin" message filter is used.</span></span> <span data-ttu-id="dac10-148">Il filtro messaggi viene creato nel file RoutingService\RoundRobinMessageFilter.cs fornito.</span><span class="sxs-lookup"><span data-stu-id="dac10-148">This message filter is created in the provided RoutingService\RoundRobinMessageFilter.cs file.</span></span> <span data-ttu-id="dac10-149">Quando sono impostati sullo stesso gruppo, questi filtri alternano segnalazioni relative alla corrispondenza o meno con il messaggio, in modo tale che solo uno di essi alla volta restituisca `true`.</span><span class="sxs-lookup"><span data-stu-id="dac10-149">These filters, when set to the same group, alternate between reporting that they match the message and that they do not, such that only one of them responds `true` at a time.</span></span>  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
```  
  
 <span data-ttu-id="dac10-150">In seguito, tutti i messaggi in questione vengono aggiunti a un oggetto <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>.</span><span class="sxs-lookup"><span data-stu-id="dac10-150">Next, all of those messages are added to a <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>.</span></span> <span data-ttu-id="dac10-151">In questo modo, vengono specificate le priorità per influenzare l'ordine di esecuzione dei filtri nella tabella dei filtri messaggi.</span><span class="sxs-lookup"><span data-stu-id="dac10-151">In doing so, priorities are specified to influence the order in which the message filter table executes the filters.</span></span> <span data-ttu-id="dac10-152">Maggiore è la priorità, prima viene eseguito il filtro; minore è la priorità, più tardi viene eseguito un filtro.</span><span class="sxs-lookup"><span data-stu-id="dac10-152">The higher the priority, the sooner the filter is executed; the lower the priority, the later a filter is executed.</span></span> <span data-ttu-id="dac10-153">Pertanto, un filtro con priorità 2 viene eseguito prima di un filtro con priorità 1.</span><span class="sxs-lookup"><span data-stu-id="dac10-153">Thus a filter at priority 2 runs before a filter at priority 1.</span></span> <span data-ttu-id="dac10-154">Se non viene specificato alcun livello di priorità, viene utilizzato quello predefinito, ovvero 0.</span><span class="sxs-lookup"><span data-stu-id="dac10-154">The default priority level if none is specified is 0.</span></span> <span data-ttu-id="dac10-155">Una tabella dei filtri messaggi esegue tutti i filtri a un determinato livello di priorità prima di passare al livello di priorità inferiore successivo.</span><span class="sxs-lookup"><span data-stu-id="dac10-155">A message filter table executes all of the filters at a given priority level before moving to the next lowest priority level.</span></span> <span data-ttu-id="dac10-156">Se viene individuata una corrispondenza a un livello di priorità specifico, la tabella dei filtri messaggi interrompe la ricerca di corrispondenze per il livello di priorità inferiore successivo.</span><span class="sxs-lookup"><span data-stu-id="dac10-156">If a match is found at a particular priority, then the message filter table does not continue trying to find matches at the next lower priority.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dac10-157">Sebbene in questo esempio venga illustrato come utilizzare le priorità dei filtri messaggi, in genere la scelta migliore e più efficace è progettare e configurare i filtri in modo che non richiedano la definizione di priorità per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="dac10-157">While this example shows how to use message filter priorities, in general it is more performant and better design to design and configure your filters such that they do not require prioritization to function correctly.</span></span>  
  
 <span data-ttu-id="dac10-158">Il primo filtro da aggiungere è il filtro XPath e la priorità viene impostata su 2.</span><span class="sxs-lookup"><span data-stu-id="dac10-158">The first filter to be added is the XPath filter and its priority is set to 2.</span></span> <span data-ttu-id="dac10-159">Si tratta del primo filtro messaggi in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dac10-159">This is the first message filter that executes.</span></span> <span data-ttu-id="dac10-160">Se tale filtro individua l'intestazione personalizzata, a prescindere dai risultati degli altri filtri, il messaggio viene indirizzato all'endpoint del servizio di calcolo che esegue l'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="dac10-160">If it finds the custom header, regardless of what the results of the other filters would be, the message is routed to the Rounding Calculator endpoint.</span></span>  
  
 <span data-ttu-id="dac10-161">Al livello di priorità 1, vengono aggiunti due filtri.</span><span class="sxs-lookup"><span data-stu-id="dac10-161">At priority 1, two filters are added.</span></span> <span data-ttu-id="dac10-162">Anche in questo caso, tali filtri vengono eseguiti solo se il filtro XPath con priorità 2 non corrisponde al messaggio.</span><span class="sxs-lookup"><span data-stu-id="dac10-162">Again, these only run if the XPath filter at priority 2 does not match the message.</span></span> <span data-ttu-id="dac10-163">Questi due filtri mostrano due diverse modalità per determinare dove è stato indirizzato il messaggio al momento della visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="dac10-163">These two filters show two different ways to determine where the message was addressed when it showed up.</span></span> <span data-ttu-id="dac10-164">Poiché i due filtri verificano di fatto se il messaggio è arrivato a uno dei due endpoint, possono essere eseguiti allo stesso livello di priorità, dal momento che non restituiscono entrambi `true` contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="dac10-164">Because the two filters effectively check to see whether the message arrived at one of the two endpoints, they can be run at the same priority level because they do not both return `true` at the same time.</span></span>  
  
 <span data-ttu-id="dac10-165">Infine, al livello di priorità 0 (la priorità minima) vengono eseguiti i filtri messaggi RoundRobin.</span><span class="sxs-lookup"><span data-stu-id="dac10-165">Finally, at Priority 0 (the lowest priority) run the RoundRobin message filters.</span></span> <span data-ttu-id="dac10-166">Poiché i filtri vengono configurati con lo stesso nome del gruppo, solo uno di essi alla volta individua una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="dac10-166">Because the filters are configured with the same group name, only one of them matches at a time.</span></span> <span data-ttu-id="dac10-167">Dal momento che tutti i messaggi con l'intestazione personalizzata sono stati indirizzati a specifici endpoint virtualizzati, i messaggi gestiti dai filtri messaggi RoundRobin sono gli unici messaggi indirizzati all'endpoint del router predefinito senza l'intestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dac10-167">Because all messages with the custom header have been routed and all those addressed to the specific virtualized endpoints, messages handled by the RoundRobin message filters are only messages that were addressed to the default router endpoint without the custom header.</span></span> <span data-ttu-id="dac10-168">Poiché tali messaggi attivano un messaggio per ogni chiamata, metà delle operazioni viene indirizzata all'endpoint del servizio di calcolatrice normale e l'altra metà all'endpoint del servizio di calcolatrice che esegue l'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="dac10-168">Because these messages switch on a message for each call, half of the operations go to the Regular Calculator endpoint and the other half go to the Rounding Calculator endpoint.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dac10-169">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="dac10-169">To use this sample</span></span>  
  
1.  <span data-ttu-id="dac10-170">Utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], aprire AdvancedFilters.sln.</span><span class="sxs-lookup"><span data-stu-id="dac10-170">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedFilters.sln.</span></span>  
  
2.  <span data-ttu-id="dac10-171">Per aprire **Esplora**selezionare **Esplora** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="dac10-171">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="dac10-172">Premere F5 o CTRL+MAIUSC+B in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dac10-172">Press F5 or CTRL+SHIFT+B in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="dac10-173">Se si desidera avviare automaticamente i progetti necessari quando si preme F5, la soluzione e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dac10-173">If you would like to auto-launch the necessary projects when you press F5, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="dac10-174">Selezionare il **progetto di avvio** nodo **proprietà comuni** nel riquadro a sinistra.</span><span class="sxs-lookup"><span data-stu-id="dac10-174">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="dac10-175">Selezionare il **più progetti di avvio** pulsante di opzione e impostare tutti i progetti per il **avviare** azione.</span><span class="sxs-lookup"><span data-stu-id="dac10-175">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="dac10-176">Se si compila il progetto con CTRL+MAIUSC+B, sarà necessario avviare le applicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dac10-176">If you build the project with CTRL+SHIFT+B, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="dac10-177">Client calcolatrice (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="dac10-177">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="dac10-178">Servizio di calcolatrice (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="dac10-178">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="dac10-179">Servizio di routing relativo alla calcolatrice (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="dac10-179">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="dac10-180">RoutingService (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="dac10-180">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="dac10-181">Nella finestra console del client calcolatrice premere INVIO per avviare il client.</span><span class="sxs-lookup"><span data-stu-id="dac10-181">In the console window of the Calculator client, press ENTER to start the client.</span></span> <span data-ttu-id="dac10-182">Il client restituisce un elenco di endpoint di destinazione da selezionare.</span><span class="sxs-lookup"><span data-stu-id="dac10-182">The client returns a list of destination endpoints to choose from.</span></span>  
  
5.  <span data-ttu-id="dac10-183">Scegliere un endpoint di destinazione digitando la lettera corrispondente, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="dac10-183">Choose a destination endpoint by typing its corresponding letter and press ENTER.</span></span>  
  
6.  <span data-ttu-id="dac10-184">In seguito, il client chiede se si desidera aggiungere un'intestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dac10-184">Next, the client asks you if you want to add a custom header.</span></span> <span data-ttu-id="dac10-185">Premere Y per Sì o N per No, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="dac10-185">Press Y for Yes or N for No, then press ENTER.</span></span>  
  
7.  <span data-ttu-id="dac10-186">In base alle selezioni effettuate, verranno visualizzati output diversi.</span><span class="sxs-lookup"><span data-stu-id="dac10-186">Depending on the selections you made, you should see different outputs.</span></span>  
  
    1.  <span data-ttu-id="dac10-187">Quello riportato di seguito è l'output restituito se è stata aggiunta un'intestazione personalizzata ai messaggi.</span><span class="sxs-lookup"><span data-stu-id="dac10-187">The following is the output returned if you added a custom header to the messages.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="dac10-188">Quello riportato di seguito è l'output restituito se è stato selezionato l'endpoint del servizio di calcolatrice che esegue l'arrotondamento senza un'intestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dac10-188">The following is the output returned if you chose the Rounding Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    3.  <span data-ttu-id="dac10-189">Quello riportato di seguito è l'output restituito se è stato selezionato l'endpoint del servizio di calcolatrice normale senza un'intestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dac10-189">The following is the output returned if you chose the Regular Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68. 46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
    4.  <span data-ttu-id="dac10-190">Quello riportato di seguito è l'output restituito se è stato selezionato l'endpoint del router predefinito senza un'intestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dac10-190">The following is the output returned if you chose the Default Router endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.14285714285714  
        ```  
  
8.  <span data-ttu-id="dac10-191">Il servizio di calcolatrice e il servizio di calcolo che esegue l'arrotondamento stampano inoltre un log delle operazioni richiamate nelle rispettive finestre della console.</span><span class="sxs-lookup"><span data-stu-id="dac10-191">The Calculator Service and the Rounding Calculator Service also prints out a log of the operations invoked to their respective console windows.</span></span>  
  
9. <span data-ttu-id="dac10-192">Nella finestra della console client, digitare `quit` e premere INVIO per uscire.</span><span class="sxs-lookup"><span data-stu-id="dac10-192">In the client console window, type `quit` and press ENTER to exit.</span></span>  
  
10. <span data-ttu-id="dac10-193">Premere INVIO nelle finestre della console dei servizi per terminare i servizi.</span><span class="sxs-lookup"><span data-stu-id="dac10-193">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="dac10-194">Configurabile tramite codice o App.config</span><span class="sxs-lookup"><span data-stu-id="dac10-194">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="dac10-195">L'esempio proposto è configurato per l'uso di un file App.config per la definizione del comportamento del router.</span><span class="sxs-lookup"><span data-stu-id="dac10-195">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="dac10-196">È inoltre possibile modificare il nome del file RoutingService\App.config affinché non venga riconosciuto e rimuovere i commenti dalla chiamata al metodo `ConfigureRouterViaCode()` in RoutingService\routing.cs.</span><span class="sxs-lookup"><span data-stu-id="dac10-196">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()` in RoutingService\routing.cs.</span></span> <span data-ttu-id="dac10-197">Entrambi i metodi restituiscono lo stesso comportamento da parte del router.</span><span class="sxs-lookup"><span data-stu-id="dac10-197">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="dac10-198">Scenario</span><span class="sxs-lookup"><span data-stu-id="dac10-198">Scenario</span></span>  
 <span data-ttu-id="dac10-199">In questo esempio il router agisce come router basato sul contenuto consentendo a più tipi o implementazioni di servizi di essere esposti mediante un endpoint.</span><span class="sxs-lookup"><span data-stu-id="dac10-199">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="dac10-200">Scenario reale</span><span class="sxs-lookup"><span data-stu-id="dac10-200">Real World Scenario</span></span>  
 <span data-ttu-id="dac10-201">Contoso desidera virtualizzare i propri servizi per esporre pubblicamente solo un endpoint tramite il quale viene offerto l'accesso a più tipi diversi di servizi.</span><span class="sxs-lookup"><span data-stu-id="dac10-201">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="dac10-202">In questo caso, le funzionalità di routing basate sul contenuto del servizio di routing vengono utilizzate per determinare dove devono essere inviate le richieste in entrata.</span><span class="sxs-lookup"><span data-stu-id="dac10-202">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac10-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dac10-203">See Also</span></span>  
 [<span data-ttu-id="dac10-204">Hosting di AppFabric ed esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="dac10-204">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
