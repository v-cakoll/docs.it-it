---
title: Convalida della sicurezza
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
ms.openlocfilehash: 90d335f32c43ecf575c69cf800ab69bee05f39ee
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728380"
---
# <a name="security-validation"></a><span data-ttu-id="0fd14-102">Convalida della sicurezza</span><span class="sxs-lookup"><span data-stu-id="0fd14-102">Security validation</span></span>
<span data-ttu-id="0fd14-103">In questo esempio viene illustrato come utilizzare un comportamento personalizzato per convalidare i servizi in un computer per garantire che soddisfino criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="0fd14-103">This sample demonstrates how to use a custom behavior to validate services on a computer to ensure they meet specific criteria.</span></span> <span data-ttu-id="0fd14-104">Nell'esempio i servizi vengono convalidati dal comportamento personalizzato mediante l'analisi di ogni endpoint nel servizio e verificando se contengono elementi di associazione protetti.</span><span class="sxs-lookup"><span data-stu-id="0fd14-104">In this sample, services are validated by the custom behavior by scanning through each endpoint on the service and checking to see whether they contain secure binding elements.</span></span> <span data-ttu-id="0fd14-105">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0fd14-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fd14-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0fd14-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="endpoint-validation-custom-behavior"></a><span data-ttu-id="0fd14-107">Comportamento personalizzato di convalida dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="0fd14-107">Endpoint Validation Custom Behavior</span></span>  
 <span data-ttu-id="0fd14-108">Aggiungendo il codice utente al metodo `Validate` contenuto nell'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior>, il comportamento personalizzato può essere assegnato a un servizio o a un endpoint per eseguire azioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0fd14-108">By adding user code to the `Validate` method contained in the <xref:System.ServiceModel.Description.IServiceBehavior> interface, custom behavior can be given to a service or endpoint to perform user-defined actions.</span></span> <span data-ttu-id="0fd14-109">Il codice seguente viene utilizzato per eseguire un ciclo in ogni endpoint contenuto in un servizio allo scopo di esaminare le raccolte di associazioni per individuare le associazioni protette.</span><span class="sxs-lookup"><span data-stu-id="0fd14-109">The following code is used to loop through each endpoint contained in a service, which searches through their binding collections for secure bindings.</span></span>  
  
```csharp
public void Validate(ServiceDescription serviceDescription,
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any
        // secure binding elements. Transport, Asymmetric, and Symmetric
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 <span data-ttu-id="0fd14-110">L'aggiunta del codice seguente a file Web.config aggiunge l'estensione del comportamento `serviceValidate` affinché venga riconosciuta dal servizio.</span><span class="sxs-lookup"><span data-stu-id="0fd14-110">Adding the following code to Web.config file adds the `serviceValidate` behavior extension for the service to recognize.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>
    ...
</system.serviceModel>
```  
  
 <span data-ttu-id="0fd14-111">Quando l'estensione del comportamento è stata aggiunta al servizio, è possibile aggiungere il comportamento `endpointValidate` all'elenco dei comportamenti nel file Web.config e, di conseguenza, al servizio.</span><span class="sxs-lookup"><span data-stu-id="0fd14-111">Once the behavior extension is added to the service, it is now possible to add the `endpointValidate` behavior to the list of behaviors in the Web.config file and thus, to the service.</span></span>  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="0fd14-112">I comportamenti e le estensioni aggiunti al file Web.config applicano il comportamento ai singoli servizi, mentre se sono aggiunti al file Machine.config applicano il comportamento a ogni servizio attivo nel computer.</span><span class="sxs-lookup"><span data-stu-id="0fd14-112">Behaviors and their extensions that are added to the Web.config file apply behavior to individual services, while when added to the Machine.config file apply behavior to every service active on the computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fd14-113">Quando si aggiunge il comportamento a tutti i servizi, è consigliabile eseguire il backup del file Machine.config prima di apportare qualsiasi modifica.</span><span class="sxs-lookup"><span data-stu-id="0fd14-113">When adding behavior to all services, it is suggested to backup the Machine.config file before making any change.</span></span>  
  
 <span data-ttu-id="0fd14-114">Eseguire quindi il client fornito nella directory client\bin di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="0fd14-114">Now run the client provided in the client\bin directory of this sample.</span></span> <span data-ttu-id="0fd14-115">Viene generata un'eccezione con il messaggio seguente: "Impossibile attivare il servizio richiestohttp://localhost/servicemodelsamples/service.svc''.</span><span class="sxs-lookup"><span data-stu-id="0fd14-115">An exception is thrown with the following message: "The requested service, 'http://localhost/servicemodelsamples/service.svc' could not be activated."</span></span> <span data-ttu-id="0fd14-116">Si tratta di un problema previsto poiché un endpoint viene considerato non protetto dall'endpoint che convalida il comportamento e impedisce l'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="0fd14-116">This is expected because an endpoint is considered insecure by the endpoint validating behavior and prevents the service from being started.</span></span> <span data-ttu-id="0fd14-117">Il comportamento genera anche un'eccezione interna che descrive quale endpoint non è protetto e scrive un messaggio nel visualizzatore eventi di sistema nell'origine "System.ServiceModel 4.0.0.0", categoria "WebHost".</span><span class="sxs-lookup"><span data-stu-id="0fd14-117">The behavior also throws an internal exception that describes which endpoint is insecure and writes a message to the system Event Viewer under the "System.ServiceModel 4.0.0.0" source and the "WebHost" category.</span></span> <span data-ttu-id="0fd14-118">È anche possibile attivare la traccia nel servizio in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="0fd14-118">It is also possible to turn on tracing on the service in this sample.</span></span> <span data-ttu-id="0fd14-119">Questa operazione consente all'utente di visualizzare le eccezioni generate dall'endpoint che convalida il comportamento aprendo le tracce del servizio risultanti mediante Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="0fd14-119">This allows the user to view the exceptions thrown by endpoint validating behavior by opening the resulting service traces using the Service Trace Viewer tool.</span></span>  
  
### <a name="view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a><span data-ttu-id="0fd14-120">Visualizza i messaggi di eccezione di convalida endpoint non riusciti nel Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="0fd14-120">View failed endpoint validation exception messages in the Event Viewer</span></span>  
  
1. <span data-ttu-id="0fd14-121">Fare clic sul menu **Start** e selezionare **Esegui...**.</span><span class="sxs-lookup"><span data-stu-id="0fd14-121">Click the **Start** menu and select **Run…**.</span></span>  
  
2. <span data-ttu-id="0fd14-122">Digitare `eventvwr` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fd14-122">Type `eventvwr` and click **OK**.</span></span>  
  
3. <span data-ttu-id="0fd14-123">Nella finestra di Visualizzatore eventi fare clic su **applicazione**.</span><span class="sxs-lookup"><span data-stu-id="0fd14-123">In the Event Viewer window, click **Application**.</span></span>  
  
4. <span data-ttu-id="0fd14-124">Fare doppio clic sull'evento "System. ServiceModel 4.0.0.0" aggiunto di recente nella categoria "provider" nella finestra **dell'applicazione** per visualizzare i messaggi dell'endpoint non protetto.</span><span class="sxs-lookup"><span data-stu-id="0fd14-124">Double-click the recently added "System.ServiceModel 4.0.0.0" event under the "WebHost" category in the **Application** window to view insecure endpoint messages.</span></span>  
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="0fd14-125">Configurare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0fd14-125">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0fd14-126">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0fd14-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0fd14-127">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0fd14-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0fd14-128">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0fd14-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0fd14-129">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0fd14-129">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0fd14-130">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0fd14-130">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0fd14-131">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi.</span><span class="sxs-lookup"><span data-stu-id="0fd14-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0fd14-132">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0fd14-132">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a><span data-ttu-id="0fd14-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fd14-133">See also</span></span>

- <span data-ttu-id="0fd14-134">[Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0fd14-134">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
