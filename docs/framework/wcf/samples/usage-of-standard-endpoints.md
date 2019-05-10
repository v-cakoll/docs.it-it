---
title: Uso di endpoint standard
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: a2af1ae793166d1ed3742782b911ded30d0b9d35
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662386"
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="51f6b-102">Uso di endpoint standard</span><span class="sxs-lookup"><span data-stu-id="51f6b-102">Usage of Standard Endpoints</span></span>

<span data-ttu-id="51f6b-103">In questo esempio viene illustrato come usare endpoint standard in file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="51f6b-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="51f6b-104">Un endpoint standard consente all'utente di semplificare le definizioni degli endpoint usando una singola proprietà per descrivere un indirizzo, un'associazione e una combinazione del contratto con proprietà aggiuntive associate.</span><span class="sxs-lookup"><span data-stu-id="51f6b-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="51f6b-105">In questo esempio viene descritto come definire e implementare un endpoint standard personalizzato e come definire proprietà specifiche nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="51f6b-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>

## <a name="sample-details"></a><span data-ttu-id="51f6b-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="51f6b-106">Sample Details</span></span>

<span data-ttu-id="51f6b-107">È possibile specificare gli endpoint del servizio fornendo tre parametri: indirizzo, associazione e contratto.</span><span class="sxs-lookup"><span data-stu-id="51f6b-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="51f6b-108">Gli altri parametri che è possibile fornire includono la configurazione del comportamento, le intestazioni, l'URI di ascolto e così via.</span><span class="sxs-lookup"><span data-stu-id="51f6b-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="51f6b-109">In alcuni casi, alcuni o tutti gli indirizzi, le associazioni e i contratti dispongono di valori che non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="51f6b-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="51f6b-110">Per questo motivo, è possibile usare endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="51f6b-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="51f6b-111">Alcuni esempi di tali endpoint includono endpoint per lo scambio di metadati ed endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="51f6b-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="51f6b-112">Gli endpoint standard migliorano inoltre l'usabilità consentendo la configurazione degli endpoint del servizio senza che sia necessario fornire informazioni di natura fissa o creare endpoint standard personalizzati, migliorando ad esempio l'usabilità attraverso la specifica di un set limitato di valori predefiniti e la conseguente riduzione del livello di dettaglio dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="51f6b-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>

<span data-ttu-id="51f6b-113">Questo esempio è costituito da due progetti, ovvero dal servizio che definisce due endpoint standard e dal client che comunica con il servizio.</span><span class="sxs-lookup"><span data-stu-id="51f6b-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="51f6b-114">Il modo in cui gli endpoint standard sono definiti per il servizio nel file di configurazione è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="51f6b-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>

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

<span data-ttu-id="51f6b-115">Il primo endpoint definito per il servizio è di tipo `customEndpoint`, la cui definizione è inclusa nella sezione `<standardEndpoints>` dove alla proprietà `property` è assegnato il valore `true`.</span><span class="sxs-lookup"><span data-stu-id="51f6b-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="51f6b-116">Si tratta del caso di un endpoint personalizzato con una nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="51f6b-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="51f6b-117">Il secondo endpoint corrisponde a un endpoint di metadati, in cui i valori per indirizzo, associazione e contratto sono fissi.</span><span class="sxs-lookup"><span data-stu-id="51f6b-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>

<span data-ttu-id="51f6b-118">Per definire l'elemento dell'endpoint standard, è necessario creare una classe che deriva da `StandardEndpointElement`.</span><span class="sxs-lookup"><span data-stu-id="51f6b-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="51f6b-119">In questo esempio la classe `CustomEndpointElement` è stata definita come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="51f6b-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>

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

<span data-ttu-id="51f6b-120">Nella funzione `CreateServiceEndpoint` viene creato un oggetto `CustomEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="51f6b-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="51f6b-121">La relativa definizione è illustrata nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="51f6b-121">Its definition is shown in the following example:</span></span>

```csharp
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

 <span data-ttu-id="51f6b-122">Per stabilire la comunicazione tra il servizio e il client, nel client viene creato un riferimento al servizio.</span><span class="sxs-lookup"><span data-stu-id="51f6b-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="51f6b-123">Quando l'esempio viene compilato ed eseguito, il servizio viene eseguito e il client comunica con il servizio.</span><span class="sxs-lookup"><span data-stu-id="51f6b-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="51f6b-124">Si noti che il riferimento al servizio deve essere aggiornato ogni volta che viene apportata una modifica nel servizio.</span><span class="sxs-lookup"><span data-stu-id="51f6b-124">Note that the service reference should be updated every time there is some change in the service.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="51f6b-125">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="51f6b-125">To use this sample</span></span>

1. <span data-ttu-id="51f6b-126">Usa Visual Studio 2012, aprire il file standardEndpoints.</span><span class="sxs-lookup"><span data-stu-id="51f6b-126">Using Visual Studio 2012, open the StandardEndpoints.sln file.</span></span>

2. <span data-ttu-id="51f6b-127">Consentire l'avvio di più progetti.</span><span class="sxs-lookup"><span data-stu-id="51f6b-127">Enable multiple projects to start up.</span></span>

    1. <span data-ttu-id="51f6b-128">Nelle **Esplora soluzioni**, fare doppio clic su soluzione Standard Endpoints, quindi selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="51f6b-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>

    2. <span data-ttu-id="51f6b-129">Nelle **proprietà comuni**, selezionare **progetto di avvio**, quindi fare clic su **progetti di avvio multipli**.</span><span class="sxs-lookup"><span data-stu-id="51f6b-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>

    3. <span data-ttu-id="51f6b-130">Spostare il progetto di servizio all'inizio dell'elenco, con la **azione** impostata su **avviare**.</span><span class="sxs-lookup"><span data-stu-id="51f6b-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>

    4. <span data-ttu-id="51f6b-131">Spostare il progetto Client dopo il progetto di servizio, anche con il **azione** impostata su **avviare**.</span><span class="sxs-lookup"><span data-stu-id="51f6b-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>

         <span data-ttu-id="51f6b-132">In questo modo si specifica che il progetto Client viene eseguito dopo il progetto Service.</span><span class="sxs-lookup"><span data-stu-id="51f6b-132">This specifies that the Client project is executed after the Service project.</span></span>

3. <span data-ttu-id="51f6b-133">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="51f6b-133">To run the solution, press F5.</span></span>

> [!NOTE]
> <span data-ttu-id="51f6b-134">Se questi passaggi risolve il problema, assicurarsi che l'ambiente è stato configurato correttamente, usando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="51f6b-134">If these steps don't work, then make sure that your environment has been properly set up, using the following steps:</span></span>
>
> 1. <span data-ttu-id="51f6b-135">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51f6b-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>
> 2. <span data-ttu-id="51f6b-136">Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51f6b-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>
> 3. <span data-ttu-id="51f6b-137">Per eseguire l'esempio in una o più configurazioni di computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51f6b-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51f6b-138">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="51f6b-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="51f6b-139">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="51f6b-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="51f6b-140">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="51f6b-140">If this directory doesn't exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51f6b-141">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="51f6b-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
