---
title: Configurazione dell'individuazione in un file di configurazione
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: b2e604f6168e4adff36bfb0c22861124743b358d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185321"
---
# <a name="configuring-discovery-in-a-configuration-file"></a><span data-ttu-id="71944-102">Configurazione dell'individuazione in un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="71944-102">Configuring Discovery in a Configuration File</span></span>
<span data-ttu-id="71944-103">Nell'individuazione vengono usati quattro gruppi principali di impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="71944-103">There are four major groups of configuration settings used in discovery.</span></span> <span data-ttu-id="71944-104">In questo argomento viene illustrato brevemente ciascuno di questi gruppi e vengono mostrati esempi per poterli configurare.</span><span class="sxs-lookup"><span data-stu-id="71944-104">This topic will briefly describe each and show examples of how to configure them.</span></span> <span data-ttu-id="71944-105">Al termine di ogni sezione sarà disponibile un collegamento a documenti più dettagliati su ogni area.</span><span class="sxs-lookup"><span data-stu-id="71944-105">Following each section will be a link to more in-depth documentation about each area.</span></span>  
  
## <a name="behavior-configuration"></a><span data-ttu-id="71944-106">Comportamento di configurazione</span><span class="sxs-lookup"><span data-stu-id="71944-106">Behavior Configuration</span></span>  
 <span data-ttu-id="71944-107">L'individuazione usa comportamenti del servizio e dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="71944-107">Discovery uses service behaviors and endpoint behaviors.</span></span> <span data-ttu-id="71944-108">Il comportamento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> abilita l'individuazione per tutti gli endpoint di un servizio e consente di specificare endpoint annunci.</span><span class="sxs-lookup"><span data-stu-id="71944-108">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> behavior enables discovery for all of a service’s endpoints and allows you to specify announcement endpoints.</span></span>  <span data-ttu-id="71944-109">Nell'esempio seguente viene illustrato come aggiungere l'elemento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> e specificare un endpoint annunci.</span><span class="sxs-lookup"><span data-stu-id="71944-109">The following example shows how to add the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and specify an announcement endpoint.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
```  
  
 <span data-ttu-id="71944-110">Dopo aver specificato il comportamento, `service` fare riferimento a un elemento> <, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="71944-110">Once you specify the behavior, reference it from a <`service`> element as shown in the following sample.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
         <!-- Application Endpoint -->  
         <endpoint address="endpoint0"  
                   binding="basicHttpBinding"  
                   contract="IHelloWorldService" />  
         <!-- Discovery Endpoints -->  
         <endpoint kind="udpDiscoveryEndpoint" />  
        </service>  
    </service>  
```  
  
 <span data-ttu-id="71944-111">Affinché un servizio sia individuabile, è necessario aggiungere anche un endpoint di individuazione. Nell'esempio precedente viene aggiunto un endpoint <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard.</span><span class="sxs-lookup"><span data-stu-id="71944-111">In order for a service to be discoverable, you must also add a discovery endpoint, the example above adds a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard endpoint.</span></span>  
  
 <span data-ttu-id="71944-112">Quando si aggiungono endpoint annuncio, è necessario aggiungere `services` anche un servizio listener di annunci all'elemento> <, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="71944-112">When you add announcement endpoints you must also add an announcement listener service to the <`services`> element as shown in the following example.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
      <!-- Application Endpoint -->  
      <endpoint address="endpoint0"  
                binding="basicHttpBinding"  
                contract="IHelloWorldService" />  
      <!-- Discovery Endpoints -->  
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <!-- Announcement Listener Configuration -->  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
```  
  
 <span data-ttu-id="71944-113">Il comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> viene usato per abilitare o disabilitare l'individuazione di un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="71944-113">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is used to enable or disable discovery of a specific endpoint.</span></span>  <span data-ttu-id="71944-114">Nell'esempio seguente viene configurato un servizio con due endpoint dell'applicazione, uno con l'individuazione abilitata e uno con l'individuazione disabilitata.</span><span class="sxs-lookup"><span data-stu-id="71944-114">The following example configures a service with two application endpoints, one with discovery enabled and one with discovery disabled.</span></span> <span data-ttu-id="71944-115">Per ogni endpoint viene aggiunto un comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="71944-115">For each endpoint an <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior is added.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService"  
               behaviorConfiguration="helloWorldServiceBehavior">  
  
        <!-- Application Endpoints -->  
        <endpoint address="endpoint0"  
                 binding="basicHttpBinding"  
                 contract="IHelloWorldService"
                 behaviorConfiguration="ep0Behavior" />  
  
        <endpoint address="endpoint1"  
                  binding="basicHttpBinding"  
                  contract="IHelloWorldService"  
                  behaviorConfiguration="ep1Behavior" />  
  
        <!-- Discovery Endpoints -->  
        <endpoint kind="udpDiscoveryEndpoint" />  
      </service>  
   </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery />  
        </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="ep0Behavior">  
          <endpointDiscovery enabled="true"/>  
        </behavior>  
        <behavior name="ep1Behavior">  
          <endpointDiscovery enabled="false"/>  
        </behavior>  
     </endpointBehaviors>  
   </behaviors>  
```  
  
 <span data-ttu-id="71944-116">Il comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> può essere inoltre usato per aggiungere metadati personalizzati ai metadati dell'endpoint restituiti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="71944-116">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add custom metadata to the endpoint metadata returned by the service.</span></span> <span data-ttu-id="71944-117">L'esempio seguente illustra come farlo.</span><span class="sxs-lookup"><span data-stu-id="71944-117">The following example shows how to do this.</span></span>  
  
```xml  
<behavior name="ep4Behavior">  
   <endpointDiscovery enabled="true">  
      <extensions>  
         <CustomMetadata>This is custom metadata.</CustomMetadata>  
         <d:Types xmlns:d="http://schemas.xmlsoap.org/ws/2005/04/discovery" xmlns:i="http://printer.example.org/2003/imaging">i:PrintBasic</d:Types>  
         <CustomMetadata netsted="true">  
            <NestedMetadata>This is a nested custom metadata.</NestedMetadata>  
         </CustomMetadata>  
      </extensions>  
   </endpointDiscovery>  
</behavior>  
```  
  
 <span data-ttu-id="71944-118">Il comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> può essere inoltre usato per aggiungere ambiti e tipi usati dai client per cercare servizi.</span><span class="sxs-lookup"><span data-stu-id="71944-118">The <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> behavior can also be used to add scopes and types that clients use to search for services.</span></span> <span data-ttu-id="71944-119">Nell'esempio seguente viene descritto come effettuare questa operazione in un file di configurazione lato client.</span><span class="sxs-lookup"><span data-stu-id="71944-119">The following example shows how to do this in a client side configuration file.</span></span>  
  
```xml  
<behavior name="ep2Behavior">  
   <endpointDiscovery enabled="true">  
      <scopes>  
         <add scope="http://www.microsoft.com/building42/floor1"/>  
         <add scope="ldap:///ou=engineeringo=examplecomc=us"/>  
      </scopes>  
      <types>  
         <add name="test" namespace="http://example.microsoft.com/" />  
         <add name="additionalContract" namespace="http://example.microsoft.com/" />  
      </types>  
   </endpointDiscovery>  
</behavior>  
```  
  
 <span data-ttu-id="71944-120">Per ulteriori <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> informazioni <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> e vedere [Cenni preliminari sull'individuazione WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span><span class="sxs-lookup"><span data-stu-id="71944-120">For more information about <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> see [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span></span>  
  
## <a name="binding-element-configuration"></a><span data-ttu-id="71944-121">Configurazione di elementi di associazione</span><span class="sxs-lookup"><span data-stu-id="71944-121">Binding Element Configuration</span></span>  
 <span data-ttu-id="71944-122">La configurazione degli elementi di associazione è particolarmente interessante nel lato client.</span><span class="sxs-lookup"><span data-stu-id="71944-122">Binding element configuration is most interesting on the client side.</span></span> <span data-ttu-id="71944-123">È possibile usare la configurazione per specificare i criteri di ricerca usata per individuare servizi da un'applicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="71944-123">You can use configuration to specify the find criteria used to discover services from a WCF client application.</span></span>  <span data-ttu-id="71944-124">Nell'esempio seguente viene creata un'associazione personalizzata con il canale <xref:System.ServiceModel.Discovery.DiscoveryClient> e vengono specificati criteri di ricerca che includono un tipo e un ambito.</span><span class="sxs-lookup"><span data-stu-id="71944-124">The following example creates a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClient> channel and specifies find criteria that includes a type and scope.</span></span> <span data-ttu-id="71944-125">Vengono inoltre specificati valori per le proprietà <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> e <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>.</span><span class="sxs-lookup"><span data-stu-id="71944-125">In addition it specifies values for the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> and <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> properties.</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <!-- Binding Configuration for the Application Endpoint -->  
      <binding name="discoBindingConfiguration">  
         <discoveryClient>  
            <endpoint kind="discoveryEndpoint"  
                      address="http://localhost:8000/ConfigTest/Discovery"  
                      binding="customBinding"  
                      bindingConfiguration="httpSoap12WSAddressing10"/>  
            <findCriteria duration="00:00:10" maxResults="2">  
              <types>  
                <add name="IHelloWorldService"/>  
              </types>  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>
            </findCriteria>  
          </discoveryClient>  
          <textMessageEncoding messageVersion="Soap11"/>  
          <httpTransport />  
        </binding>  
```  
  
 <span data-ttu-id="71944-126">È necessario che un endpoint client faccia riferimento a questa configurazione di associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="71944-126">This custom binding configuration must be referenced by a client endpoint:</span></span>  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
    </client>  
```  
  
 <span data-ttu-id="71944-127">Per ulteriori informazioni sui criteri di ricerca, vedere [Discovery Find e FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="71944-127">For more information about find criteria see [Discovery Find and FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span></span> <span data-ttu-id="71944-128">Per altre informazioni sugli elementi di individuazione e associazione, vedere Cenni preliminari [sull'individuazione WCFFor](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md) more information about discovery and binding elements see, WCF Discovery Overview</span><span class="sxs-lookup"><span data-stu-id="71944-128">For more information about discovery and binding elements see, [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)</span></span>  
  
## <a name="standard-endpoint-configuration"></a><span data-ttu-id="71944-129">Configurazione di endpoint standard</span><span class="sxs-lookup"><span data-stu-id="71944-129">Standard Endpoint Configuration</span></span>  
 <span data-ttu-id="71944-130">Gli endpoint standard sono endpoint con valori predefiniti per una o più proprietà (indirizzo, associazione o contratto) o uno o più valori di proprietà non modificabili.</span><span class="sxs-lookup"><span data-stu-id="71944-130">Standard endpoints are predefined endpoints that have default values for one or more properties (address, binding, or contract) or one or more property values that cannot change.</span></span> <span data-ttu-id="71944-131">.NET 4 viene fornito con 3 endpoint standard relativi all'individuazione: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> e <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="71944-131">.NET 4 ships with 3 discovery related standard endpoints: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>, and <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  <span data-ttu-id="71944-132"><xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> è un endpoint standard preconfigurato per le operazioni di individuazione su un'associazione multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="71944-132">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is a standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span> <span data-ttu-id="71944-133"><xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> è un endpoint standard preconfigurato per l'invio di messaggi di annuncio su un'associazione multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="71944-133">The <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> is a standard endpoint that is pre-configured to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="71944-134"><xref:System.ServiceModel.Discovery.DynamicEndpoint> è un endpoint standard che usa l'individuazione per cercare l'indirizzo endpoint di un servizio individuato in modo dinamico al runtime.</span><span class="sxs-lookup"><span data-stu-id="71944-134">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint that uses discovery to find the endpoint address of a discovered service dynamically at runtime.</span></span>  <span data-ttu-id="71944-135">Le associazioni standard vengono `endpoint` specificate con un <elemento> che contiene l'attributo Kind che specifica il tipo di endpoint standard da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="71944-135">Standard bindings are specified with an <`endpoint`> element that contains kind attribute that specified the type of standard endpoint to add.</span></span> <span data-ttu-id="71944-136">Nell'esempio seguente viene illustrato come aggiungere un elemento <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> e un elemento <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="71944-136">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
</services>  
```  
  
 <span data-ttu-id="71944-137">Gli endpoint standard sono `standardEndpoints` configurati in un <> elemento.</span><span class="sxs-lookup"><span data-stu-id="71944-137">Standard endpoints are configured in a <`standardEndpoints`> element.</span></span> <span data-ttu-id="71944-138">Nell'esempio seguente viene illustrato come configurare l'elemento <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> e l'elemento <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="71944-138">The following example shows how to configure the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> and the <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.</span></span>  
  
```xml  
<standardEndpoints>  
      <udpAnnouncementEndpoint>  
        <standardEndpoint
            name="udpAnnouncementEndpointSettings"
            multicastAddress="soap.udp://239.255.255.250:3703"
            maxAnnouncementDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="1028"  
            maxPendingMessageCount="10"  
            maxMulticastRetransmitCount="3"  
            maxUnicastRetransmitCount="2"  
            socketReceiveBufferSize="131072"  
            timeToLive="2" />  
        </standardEndpoint>  
      </udpAnnouncementEndpoint>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
            name="udpDiscoveryEndpointSettings"  
            multicastAddress="soap.udp://239.255.255.252:3704"  
            maxResponseDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="2048"  
            maxPendingMessageCount="5"  
            maxReceivedMessageSize="8192"  
            maxBufferPoolSize="262144"/>  
        </standardEndpoint>  
      </udpDiscoveryEndpoint>  
```  
  
 <span data-ttu-id="71944-139">Dopo aver aggiunto la configurazione dell'endpoint standard, `endpoint` fare riferimento alla configurazione nell'elemento> <per ogni endpoint, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="71944-139">Once you’ve added the standard endpoint configuration, reference the configuration in the <`endpoint`> element for each endpoint as shown in the following sample.</span></span>  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="udpDiscoveryEndpointSettings"/>  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" endpointConfiguration="udpAnnouncementEndpointSettings" >  
   </service>  
</services>  
```  
  
 <span data-ttu-id="71944-140">A differenza degli altri endpoint standard usati nell'individuazione, vengono specificati un'associazione e un contratto per <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="71944-140">Unlike the other standard endpoints used in discovery, you specify a binding and contract for <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span> <span data-ttu-id="71944-141">Nell'esempio seguente viene illustrato come aggiungere e configurare un elemento <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="71944-141">The following example shows how to add and configure a <xref:System.ServiceModel.Discovery.DynamicEndpoint>.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <endpoint kind="dynamicEndpoint" binding="basicHttpBinding" contract="IHelloWorldService" endpointConfiguration="dynamicEndpointConfiguration" />  
    </client>
   <standardEndpoints>  
      <dynamicEndpoint>  
         <standardEndpoint name="dynamicEndpointConfiguration">  
             <discoveryClientSettings>  
              <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="2">  
                 <types>  
                   <add name="IHelloWorldService"/>  
                 </types>  
                 <scopes>  
                   <add scope="http://www.microsoft.com/building42/floor1"/>  
                 </scopes>  
                 <extensions>  
                   <CustomMetadata>This is custom metadata.</CustomMetadata>
                 </extensions>  
               </findCriteria>  
             </discoveryClientSettings>  
           </standardEndpoint>  
         </dynamicEndpoint>  
   </standardEndpoints>  
</system.ServiceModel>  
```  
  
 <span data-ttu-id="71944-142">Per ulteriori informazioni sugli endpoint [standard,](standard-endpoints.md)vedere Endpoint standard .</span><span class="sxs-lookup"><span data-stu-id="71944-142">For more information about standard endpoints see [Standard Endpoints](standard-endpoints.md).</span></span>
