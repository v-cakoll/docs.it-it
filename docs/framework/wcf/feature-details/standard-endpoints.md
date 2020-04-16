---
title: Endpoint standard
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: 48924e06457cf9f91ce4f900bb38de4d22bfc550
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463782"
---
# <a name="standard-endpoints"></a><span data-ttu-id="ac636-102">Endpoint standard</span><span class="sxs-lookup"><span data-stu-id="ac636-102">Standard Endpoints</span></span>
<span data-ttu-id="ac636-103">Gli endpoint vengono definiti specificando un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="ac636-103">Endpoints are defined by specifying an address, a binding, and a contract.</span></span> <span data-ttu-id="ac636-104">Altri parametri che è possibile impostare su un endpoint includono la configurazione di comportamento, le intestazioni e gli URI di ascolto.</span><span class="sxs-lookup"><span data-stu-id="ac636-104">Other parameters that may be set on an endpoint include behavior configuration, headers, and listen URIs.</span></span>  <span data-ttu-id="ac636-105">Per determinati tipi di endpoint tali valori non cambiano.</span><span class="sxs-lookup"><span data-stu-id="ac636-105">For certain types of endpoints these values do not change.</span></span> <span data-ttu-id="ac636-106">Gli endpoint di scambio dei metadati utilizzano ad esempio sempre il contratto <xref:System.ServiceModel.Description.IMetadataExchange>.</span><span class="sxs-lookup"><span data-stu-id="ac636-106">For example, metadata exchange endpoints always use the <xref:System.ServiceModel.Description.IMetadataExchange> contract.</span></span> <span data-ttu-id="ac636-107">Altri endpoint, quali <xref:System.ServiceModel.Description.WebHttpEndpoint>, richiedono sempre un comportamento di endpoint specificato.</span><span class="sxs-lookup"><span data-stu-id="ac636-107">Other endpoints, such as <xref:System.ServiceModel.Description.WebHttpEndpoint> always require a specified endpoint behavior.</span></span> <span data-ttu-id="ac636-108">L'usabilità di un endpoint può essere migliorata grazie a endpoint con valori predefiniti per le proprietà di endpoint di uso comune.</span><span class="sxs-lookup"><span data-stu-id="ac636-108">The usability of an endpoint can be improved by having endpoints with default values for commonly used endpoint properties.</span></span> <span data-ttu-id="ac636-109">Gli endpoint standard consentono a uno sviluppatore di definire un endpoint che dispone di valori predefiniti o in cui una o più proprietà di endpoint non cambiano.</span><span class="sxs-lookup"><span data-stu-id="ac636-109">Standard endpoints enable a developer to define an endpoint that has default values or where one or more endpoint’s properties does not change.</span></span>  <span data-ttu-id="ac636-110">Questi endpoint consentono di utilizzare tale endpoint senza dovere specificare informazioni di natura statica.</span><span class="sxs-lookup"><span data-stu-id="ac636-110">These endpoints allow you to use such an endpoint without having to specify information of a static nature.</span></span> <span data-ttu-id="ac636-111">Gli endpoint standard possono essere utilizzati per endpoint infrastruttura ed endpoint applicazione.</span><span class="sxs-lookup"><span data-stu-id="ac636-111">Standard endpoints can be used for infrastructure and application endpoints.</span></span>  
  
## <a name="infrastructure-endpoints"></a><span data-ttu-id="ac636-112">Endpoint infrastruttura</span><span class="sxs-lookup"><span data-stu-id="ac636-112">Infrastructure Endpoints</span></span>  
 <span data-ttu-id="ac636-113">Un servizio può esporre endpoint con alcune proprietà non implementate in modo esplicito dall'autore del servizio.</span><span class="sxs-lookup"><span data-stu-id="ac636-113">A service may expose endpoints with some of the properties not explicitly implemented by the service author.</span></span> <span data-ttu-id="ac636-114">L'endpoint di scambio dei metadati espone ad esempio il contratto <xref:System.ServiceModel.Description.IMetadataExchange>, ma l'autore del servizio non implementa l'interfaccia, poiché viene implementata da WCF.</span><span class="sxs-lookup"><span data-stu-id="ac636-114">For example, the metadata exchange endpoint exposes the <xref:System.ServiceModel.Description.IMetadataExchange> contract but as a service author you do not implement that interface, it is implemented by WCF.</span></span> <span data-ttu-id="ac636-115">Tali endpoint infrastruttura dispongono di valori predefiniti per una o più proprietà di endpoint, alcune delle quali potrebbero non essere modificabili.</span><span class="sxs-lookup"><span data-stu-id="ac636-115">Such infrastructure endpoints have default values for one or more endpoint properties, some of which may be unalterable.</span></span> <span data-ttu-id="ac636-116">La proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> dell'endpoint di scambio dei metadati deve essere <xref:System.ServiceModel.Description.IMetadataExchange>, mentre altre proprietà, tra cui l'associazione, possono essere fornite dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="ac636-116">The <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> property of the metadata exchange endpoint must be <xref:System.ServiceModel.Description.IMetadataExchange>, while other properties like binding can be supplied by the developer.</span></span> <span data-ttu-id="ac636-117">Gli endpoint infrastruttura vengono identificati impostando la proprietà <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="ac636-117">Infrastructure endpoints are identified by setting the <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> property to `true`.</span></span>  
  
## <a name="application-endpoints"></a><span data-ttu-id="ac636-118">Endpoint applicazione</span><span class="sxs-lookup"><span data-stu-id="ac636-118">Application Endpoints</span></span>  
 <span data-ttu-id="ac636-119">Gli sviluppatori di applicazioni possono definire endpoint standard specifici che indicano valori predefiniti per l'indirizzo, l'associazione o il contratto.</span><span class="sxs-lookup"><span data-stu-id="ac636-119">Application developers can define their own standard endpoints which specify default values for the address, binding, or contract.</span></span> <span data-ttu-id="ac636-120">Un endpoint standard viene definito deducendo una classe da <xref:System.ServiceModel.Description.ServiceEndpoint> e impostando le proprietà di endpoint appropriate.</span><span class="sxs-lookup"><span data-stu-id="ac636-120">You define a standard endpoint by deriving a class from <xref:System.ServiceModel.Description.ServiceEndpoint> and setting the appropriate endpoint properties.</span></span> <span data-ttu-id="ac636-121">È possibile fornire valori predefiniti per proprietà che possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="ac636-121">You can provide default values for properties that can be changed.</span></span> <span data-ttu-id="ac636-122">Altre proprietà disporranno di valori statici che non sarà possibile modificare.</span><span class="sxs-lookup"><span data-stu-id="ac636-122">Some other properties will have static values that cannot change.</span></span> <span data-ttu-id="ac636-123">Nell'esempio riportato di seguito viene illustrato come implementare un endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="ac636-123">The following example shows how to implement a standard endpoint.</span></span>  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 <span data-ttu-id="ac636-124">Per utilizzare un endpoint personalizzato definito dall'utente in <xref:System.ServiceModel.Configuration.StandardEndpointElement>un file di <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>configurazione, è necessario derivare una classe da , derivare una classe da e registrare il nuovo endpoint standard nella sezione extensions in app.config o machine.config.  Fornisce <xref:System.ServiceModel.Configuration.StandardEndpointElement> il supporto della configurazione per l'endpoint standard, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ac636-124">To use a user-defined custom endpoint in a configuration file you must derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointElement>, derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>, and register the new standard endpoint in the extensions section in app.config or machine.config.  The <xref:System.ServiceModel.Configuration.StandardEndpointElement> provides configuration support for the standard endpoint, as shown in the following example.</span></span>  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 <span data-ttu-id="ac636-125">L'oggetto <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> fornisce il tipo di supporto `standardEndpoints` per la raccolta visualizzato nella sezione> <della configurazione per l'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="ac636-125">The <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> provides the backing type for the collection that appears under the <`standardEndpoints`> section in the configuration for the standard endpoint.</span></span>  <span data-ttu-id="ac636-126">Nell'esempio seguente viene illustrato come implementare la classe.</span><span class="sxs-lookup"><span data-stu-id="ac636-126">The following example shows how to implement this class.</span></span>  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

<span data-ttu-id="ac636-127">Nell'esempio seguente viene mostrato come registrare un endpoint standard nella sezione delle estensioni.</span><span class="sxs-lookup"><span data-stu-id="ac636-127">The following example shows how to register a standard endpoint in the extensions section.</span></span>

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
      </standardEndpointExtensions>
</extensions>  
```  
  
## <a name="configuring-a-standard-endpoint"></a><span data-ttu-id="ac636-128">Configurazione di un endpoint standard</span><span class="sxs-lookup"><span data-stu-id="ac636-128">Configuring a Standard Endpoint</span></span>  
 <span data-ttu-id="ac636-129">È possibile aggiungere endpoint standard al codice o alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="ac636-129">Standard endpoints can be added in code or in configuration.</span></span>  <span data-ttu-id="ac636-130">Per aggiungere un endpoint standard al codice, è sufficiente creare un'istanza del tipo di endpoint standard appropriato e aggiungerla all'host del servizio, come indicato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ac636-130">To add a standard endpoint in code simply instantiate the appropriate standard endpoint type and add it to the service host as shown in the following example:</span></span>  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 <span data-ttu-id="ac636-131">Per aggiungere un endpoint standard nella `endpoint` configurazione, aggiungere `service` un elemento <> all'elemento> <e le impostazioni di configurazione necessarie nell'elemento <`standardEndpoints`>.</span><span class="sxs-lookup"><span data-stu-id="ac636-131">To add a standard endpoint in configuration, add an <`endpoint`> element to the <`service`> element and any needed configuration settings in the <`standardEndpoints`> element.</span></span> <span data-ttu-id="ac636-132">Nell'esempio seguente viene mostrato come aggiungere <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, uno degli endpoint standard disponibili con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac636-132">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, one of the standard endpoints that ships with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 <span data-ttu-id="ac636-133">Il tipo di endpoint standard viene specificato `endpoint` utilizzando l'attributo kind nell'elemento <>.</span><span class="sxs-lookup"><span data-stu-id="ac636-133">The type of standard endpoint is specified using the kind attribute in the <`endpoint`> element.</span></span> <span data-ttu-id="ac636-134">L'endpoint è configurato `standardEndpoints` all'interno dell'elemento> <.</span><span class="sxs-lookup"><span data-stu-id="ac636-134">The endpoint is configured within the <`standardEndpoints`> element.</span></span> <span data-ttu-id="ac636-135">Nell'esempio precedente viene aggiunto e configurato un endpoint <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="ac636-135">In the example above, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint is added and configured.</span></span> <span data-ttu-id="ac636-136">L'elemento> `udpDiscoveryEndpoint` <`standardEndpoint` contiene un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A>> <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint><che imposta la proprietà dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="ac636-136">The <`udpDiscoveryEndpoint`> element contains a <`standardEndpoint`> that sets the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> property of the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a><span data-ttu-id="ac636-137">Endpoint standard forniti con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ac636-137">Standard Endpoints Shipped with the .NET Framework</span></span>  
 <span data-ttu-id="ac636-138">Nella tabella seguente sono elencati gli endpoint standard forniti con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac636-138">The following table lists the standard endpoints shipped with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 `Mex Endpoint`  
 <span data-ttu-id="ac636-139">Endpoint standard utilizzato per esporre metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="ac636-139">A standard endpoint that is used to expose service metadata.</span></span>  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 <span data-ttu-id="ac636-140">Endpoint standard utilizzato dai servizi per inviare messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="ac636-140">A standard endpoint that is used by services to send announcement messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 <span data-ttu-id="ac636-141">Endpoint standard utilizzato dai servizi per inviare messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="ac636-141">A standard endpoint that is used by services to send discovery messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 <span data-ttu-id="ac636-142">Endpoint standard preconfigurato per le operazioni di individuazione su un'associazione multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="ac636-142">A standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 <span data-ttu-id="ac636-143">Endpoint standard utilizzato dai servizi per inviare messaggi di annuncio su un'associazione UDP.</span><span class="sxs-lookup"><span data-stu-id="ac636-143">A standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <span data-ttu-id="ac636-144">Endpoint standard che utilizza WS-Discovery per cercare l'indirizzo endpoint in modo dinamico al runtime.</span><span class="sxs-lookup"><span data-stu-id="ac636-144">A standard endpoint that uses WS-Discovery to find the endpoint address dynamically at runtime.</span></span>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 <span data-ttu-id="ac636-145">Endpoint standard per lo scambio dei metadati.</span><span class="sxs-lookup"><span data-stu-id="ac636-145">A standard endpoint for metadata exchange.</span></span>  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <span data-ttu-id="ac636-146">Endpoint standard con un'associazione <xref:System.ServiceModel.WebHttpBinding> che aggiunge in modo automatico il comportamento <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ac636-146">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior</span></span>  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <span data-ttu-id="ac636-147">Endpoint standard con un'associazione <xref:System.ServiceModel.WebHttpBinding> che aggiunge in modo automatico il comportamento <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ac636-147">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior.</span></span>  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 <span data-ttu-id="ac636-148">Endpoint standard con un'associazione <xref:System.ServiceModel.WebHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="ac636-148">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 <span data-ttu-id="ac636-149">Un endpoint standard che consente di chiamare operazioni di controllo sulle istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ac636-149">A standard endpoint that enables you to call control operations on workflow instances.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 <span data-ttu-id="ac636-150">Endpoint standard che supporta la creazione del flusso di lavoro e la ripresa dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="ac636-150">A standard endpoint that supports workflow creation and bookmark resumption.</span></span>
