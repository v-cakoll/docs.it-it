---
title: Uso di endpoint standard
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 85dda1619fe3a77c4716806de2467cb96287b2f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="13229-102">Uso di endpoint standard</span><span class="sxs-lookup"><span data-stu-id="13229-102">Usage of Standard Endpoints</span></span>
<span data-ttu-id="13229-103">In questo esempio viene illustrato come usare endpoint standard in file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="13229-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="13229-104">Un endpoint standard consente all'utente di semplificare le definizioni degli endpoint usando una singola proprietà per descrivere un indirizzo, un'associazione e una combinazione del contratto con proprietà aggiuntive associate.</span><span class="sxs-lookup"><span data-stu-id="13229-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="13229-105">In questo esempio viene descritto come definire e implementare un endpoint standard personalizzato e come definire proprietà specifiche nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="13229-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="13229-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="13229-106">Sample Details</span></span>  
 <span data-ttu-id="13229-107">È possibile specificare gli endpoint del servizio fornendo tre parametri: indirizzo, associazione e contratto.</span><span class="sxs-lookup"><span data-stu-id="13229-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="13229-108">Gli altri parametri che è possibile fornire includono la configurazione del comportamento, le intestazioni, l'URI di ascolto e così via.</span><span class="sxs-lookup"><span data-stu-id="13229-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="13229-109">In alcuni casi, alcuni o tutti gli indirizzi, le associazioni e i contratti dispongono di valori che non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="13229-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="13229-110">Per questo motivo, è possibile usare endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="13229-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="13229-111">Alcuni esempi di tali endpoint includono endpoint per lo scambio di metadati ed endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="13229-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="13229-112">Gli endpoint standard migliorano inoltre l'usabilità consentendo la configurazione degli endpoint del servizio senza che sia necessario fornire informazioni di natura fissa o creare endpoint standard personalizzati, migliorando ad esempio l'usabilità attraverso la specifica di un set limitato di valori predefiniti e la conseguente riduzione del livello di dettaglio dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="13229-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>  
  
 <span data-ttu-id="13229-113">Questo esempio è costituito da due progetti, ovvero dal servizio che definisce due endpoint standard e dal client che comunica con il servizio.</span><span class="sxs-lookup"><span data-stu-id="13229-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="13229-114">Il modo in cui gli endpoint standard sono definiti per il servizio nel file di configurazione è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="13229-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <endpointExtensions>  
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">  
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />  
        <endpoint kind="mexEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <standardEndpoints>  
      <customEndpoint>  
        <standardEndpoint property="True" />  
      </customEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="13229-115">Il primo endpoint definito per il servizio è di tipo `customEndpoint`, la cui definizione è inclusa nella sezione `<standardEndpoints>` dove alla proprietà `property` è assegnato il valore `true`.</span><span class="sxs-lookup"><span data-stu-id="13229-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="13229-116">Si tratta del caso di un endpoint personalizzato con una nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="13229-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="13229-117">Il secondo endpoint corrisponde a un endpoint di metadati, in cui i valori per indirizzo, associazione e contratto sono fissi.</span><span class="sxs-lookup"><span data-stu-id="13229-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>  
  
 <span data-ttu-id="13229-118">Per definire l'elemento dell'endpoint standard, è necessario creare una classe che deriva da `StandardEndpointElement`.</span><span class="sxs-lookup"><span data-stu-id="13229-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="13229-119">In questo esempio la classe `CustomEndpointElement` è stata definita come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="13229-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>  
  
```csharp  
public class CustomEndpointElement : StandardEndpointElement  
{  
    public bool Property  
    {  
        get { return (bool)base["property"]; }  
        set { base["property"] = value; }  
    }  
  
    protected override ConfigurationPropertyCollection Properties  
    {  
        get  
        {  
            ConfigurationPropertyCollection properties = base.Properties;  
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));  
            return properties;  
        }  
    }  
  
    protected override Type EndpointType  
    {  
        get { return typeof(CustomEndpoint); }  
    }  
  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)  
    {  
        return new CustomEndpoint();  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="13229-120">Nella funzione `CreateServiceEndpoint` viene creato un oggetto `CustomEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="13229-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="13229-121">La definizione corrispondente è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="13229-121">Its definition is shown in the following example.</span></span>  
  
```  
public class CustomEndpoint : ServiceEndpoint  
    {  
        public CustomEndpoint()  
            : this(string.Empty)  
        {  
        }  
  
        public CustomEndpoint(string address)  
            : this(address, ContractDescription.GetContract(typeof(ICalculator)))  
        {  
        }  
  
        public CustomEndpoint(string address, ContractDescription contract)  
            : base(contract)  
        {  
            this.Binding = new BasicHttpBinding();  
            this.IsSystemEndpoint = false;  
        }  
  
        public bool Property  
        {  
            get;  
            set;  
        }  
    }  
```  
  
 <span data-ttu-id="13229-122">Per stabilire la comunicazione tra il servizio e il client, nel client viene creato un riferimento al servizio.</span><span class="sxs-lookup"><span data-stu-id="13229-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="13229-123">Quando l'esempio viene compilato ed eseguito, il servizio viene eseguito e il client comunica con il servizio.</span><span class="sxs-lookup"><span data-stu-id="13229-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="13229-124">Si noti che il riferimento al servizio deve essere aggiornato ogni volta che viene apportata una modifica nel servizio.</span><span class="sxs-lookup"><span data-stu-id="13229-124">Note that the service reference should be updated every time there is some change in the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="13229-125">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="13229-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="13229-126">Tramite [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file StandardEndpoints.sln.</span><span class="sxs-lookup"><span data-stu-id="13229-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the StandardEndpoints.sln file.</span></span>  
  
2.  <span data-ttu-id="13229-127">Consentire l'avvio di più progetti.</span><span class="sxs-lookup"><span data-stu-id="13229-127">Enable multiple projects to start up.</span></span>  
  
    1.  <span data-ttu-id="13229-128">In **Esplora**, fare doppio clic su soluzione Standard Endpoints, quindi selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="13229-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="13229-129">In **proprietà comuni**selezionare **progetto di avvio**, quindi fare clic su **più progetti di avvio**.</span><span class="sxs-lookup"><span data-stu-id="13229-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>  
  
    3.  <span data-ttu-id="13229-130">Spostare il progetto di servizio all'inizio dell'elenco, con la **azione** impostato su **avviare**.</span><span class="sxs-lookup"><span data-stu-id="13229-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>  
  
    4.  <span data-ttu-id="13229-131">Spostare il progetto Client dopo il progetto di servizio, anche con il **azione** impostato su **avviare**.</span><span class="sxs-lookup"><span data-stu-id="13229-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>  
  
         <span data-ttu-id="13229-132">In questo modo si specifica che il progetto Client viene eseguito dopo il progetto Service.</span><span class="sxs-lookup"><span data-stu-id="13229-132">This specifies that the Client project is executed after the Service project.</span></span>  
  
3.  <span data-ttu-id="13229-133">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="13229-133">To run the solution, press F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13229-134">Se questi passaggi non funzionano, verificare che l'ambiente sia stato configurato correttamente, usando i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="13229-134">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="13229-135">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13229-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="13229-136">Per compilare la soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13229-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="13229-137">Per eseguire l'esempio in uno o più configurazioni di computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13229-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="13229-138">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="13229-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="13229-139">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="13229-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="13229-140">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13229-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13229-141">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="13229-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`  
  
## <a name="see-also"></a><span data-ttu-id="13229-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13229-142">See Also</span></span>
