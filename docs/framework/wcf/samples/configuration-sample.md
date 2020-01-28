---
title: Esempio di configurazione
ms.date: 03/30/2017
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
ms.openlocfilehash: eb02b5d01b3f95ef741aa689cc66616fd598577b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741963"
---
# <a name="configuration-sample"></a><span data-ttu-id="24975-102">Esempio di configurazione</span><span class="sxs-lookup"><span data-stu-id="24975-102">Configuration Sample</span></span>
<span data-ttu-id="24975-103">Questo esempio illustra l'utilizzo di un file di configurazione per rendere individuabile un servizio.</span><span class="sxs-lookup"><span data-stu-id="24975-103">This sample demonstrates the use of a configuration file to make a service discoverable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24975-104">L'esempio implementa l'individuazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="24975-104">This sample implements discovery in configuration.</span></span> <span data-ttu-id="24975-105">Per un esempio che implementa l'individuazione nel codice, vedere [Basic](../../../../docs/framework/wcf/samples/basic-sample.md).</span><span class="sxs-lookup"><span data-stu-id="24975-105">For a sample that implements discovery in code, see [Basic](../../../../docs/framework/wcf/samples/basic-sample.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="24975-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="24975-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="24975-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="24975-107">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="24975-108">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="24975-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="24975-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="24975-109">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## <a name="service-configuration"></a><span data-ttu-id="24975-110">Configurazione del servizio</span><span class="sxs-lookup"><span data-stu-id="24975-110">Service Configuration</span></span>  
 <span data-ttu-id="24975-111">Il file di configurazione in questo esempio illustra due funzionalità:</span><span class="sxs-lookup"><span data-stu-id="24975-111">The configuration file in this sample demonstrates two features:</span></span>  
  
- <span data-ttu-id="24975-112">Rendere individuabile il servizio su un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard.</span><span class="sxs-lookup"><span data-stu-id="24975-112">Making the service discoverable over a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
- <span data-ttu-id="24975-113">Modificare le informazioni correlate all'individuazione per l'endpoint dell'applicazione del servizio e modificare alcune delle impostazioni correlate all'individuazione nell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="24975-113">Adjusting discovery-related information for the service’s application endpoint and adjusting some of the discovery-related settings on the standard endpoint.</span></span>  
  
 <span data-ttu-id="24975-114">Per abilitare l'individuazione, è necessario effettuare alcune modifiche nel file di configurazione dell'applicazione per il servizio:</span><span class="sxs-lookup"><span data-stu-id="24975-114">To enable discovery, a few changes must be made in the application configuration file for the service:</span></span>  
  
- <span data-ttu-id="24975-115">È necessario aggiungere un endpoint di individuazione all'elemento `<service>`.</span><span class="sxs-lookup"><span data-stu-id="24975-115">A discovery endpoint must be added to the `<service>` element.</span></span> <span data-ttu-id="24975-116">Si tratta di un endpoint <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard.</span><span class="sxs-lookup"><span data-stu-id="24975-116">This is a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span> <span data-ttu-id="24975-117">Si tratta di un endpoint del sistema che il runtime associa al servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="24975-117">This is a system endpoint that the runtime associates with the discovery service.</span></span> <span data-ttu-id="24975-118">Il servizio di individuazione è in ascolto dei messaggi su tale endpoint.</span><span class="sxs-lookup"><span data-stu-id="24975-118">The discovery service listens for messages on this endpoint.</span></span>  
  
- <span data-ttu-id="24975-119">Un comportamento `<serviceDiscovery>` viene aggiunto alla sezione `<serviceBehaviors>`.</span><span class="sxs-lookup"><span data-stu-id="24975-119">A `<serviceDiscovery>` behavior is added to the `<serviceBehaviors>` section.</span></span> <span data-ttu-id="24975-120">Ciò consente al servizio di essere individuato in fase di runtime e l'endpoint di individuazione menzionato in precedenza viene utilizzato per rimanere in ascolto di messaggi `Probe` e `Resolve` di individuazione.</span><span class="sxs-lookup"><span data-stu-id="24975-120">This enables the service to be discovered at runtime and uses the discovery endpoint mentioned previously to listen for discovery `Probe` and `Resolve` messages.</span></span> <span data-ttu-id="24975-121">Con queste due aggiunte, il servizio è individuabile in corrispondenza dell'endpoint di individuazione specificato.</span><span class="sxs-lookup"><span data-stu-id="24975-121">With these two additions, the service is discoverable at the discovery endpoint specified.</span></span>  
  
 <span data-ttu-id="24975-122">Nel frammento di configurazione seguente viene illustrato un servizio con un endpoint dell'applicazione e un endpoint di individuazione definito:</span><span class="sxs-lookup"><span data-stu-id="24975-122">The following config snippet shows a service with an application endpoint and a discovery endpoint defined:</span></span>  
  
```xml
<services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
          <endpoint name="udpDiscovery"   
                    kind="udpDiscoveryEndpoint"   
                endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
```  
  
 <span data-ttu-id="24975-123">Per sfruttare i vantaggi degli annunci, è necessario aggiungere un endpoint dell'annuncio.</span><span class="sxs-lookup"><span data-stu-id="24975-123">To take advantage of announcements, you will need to add an announcement endpoint.</span></span> <span data-ttu-id="24975-124">A tale scopo, modificare il file di configurazione come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="24975-124">To do this, modify the configuration file as shown in the following code.</span></span>  
  
```xml  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
```  
  
 <span data-ttu-id="24975-125">L'aggiunta di un endpoint dell'annuncio al comportamento del servizio di individuazione crea un client dell'annuncio predefinito per il servizio.</span><span class="sxs-lookup"><span data-stu-id="24975-125">Adding an announcement endpoint to the discovery service behavior creates a default announcement client for the service.</span></span> <span data-ttu-id="24975-126">Ciò garantisce che il servizio invii un annuncio online oppure offline rispettivamente quando il servizio viene aperto e chiuso.</span><span class="sxs-lookup"><span data-stu-id="24975-126">This guarantees that the service will send an online and offline announcement when the service is opened and closed respectively.</span></span>  
  
 <span data-ttu-id="24975-127">Il file di configurazione va oltre tali semplici passaggi modificando i comportamenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="24975-127">This configuration file goes beyond just those simple steps by modifying additional behaviors.</span></span> <span data-ttu-id="24975-128">È possibile controllare le informazioni correlate all'individuazione tramite endpoint specifici.</span><span class="sxs-lookup"><span data-stu-id="24975-128">It is possible to control discovery-related information by using specific endpoints.</span></span> <span data-ttu-id="24975-129">Ovvero, un utente può controllare se è possibile individuare un endpoint e può anche contrassegnare tale endpoint con <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> e metadati XML personalizzati.</span><span class="sxs-lookup"><span data-stu-id="24975-129">That is, a user can control whether an endpoint can be discovered and the user can also mark that endpoint with <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> and custom XML metadata.</span></span> <span data-ttu-id="24975-130">A tale scopo, l'utente deve aggiungere una proprietà `behaviorConfiguration` all'endpoint dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24975-130">To do this, the user must add a `behaviorConfiguration` property to the application endpoint.</span></span> <span data-ttu-id="24975-131">In questo caso, la proprietà seguente viene aggiunta all'endpoint dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24975-131">In this case, the following property is added to the application endpoint.</span></span>  
  
`behaviorConfiguration="endpointBehaviorConfiguration"`  
  
 <span data-ttu-id="24975-132">Tramite l'elemento di configurazione del comportamento, è possibile controllare gli attributi correlati all'individuazione.</span><span class="sxs-lookup"><span data-stu-id="24975-132">Now, through the behavior configuration element, you can control discovery-related attributes.</span></span> <span data-ttu-id="24975-133">In questo caso, due ambiti vengono aggiunti all'endpoint dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24975-133">In this case, two scopes are added to the application endpoint.</span></span>  
  
```xml  
<endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
```  
  
 <span data-ttu-id="24975-134">Per ulteriori informazioni sugli ambiti, vedere [Discovery Find e FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="24975-134">For more information about scopes, see [Discovery Find and FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).</span></span>  
  
 <span data-ttu-id="24975-135">È inoltre possibile controllare dettagli specifici dell'endpoint di individuazione.</span><span class="sxs-lookup"><span data-stu-id="24975-135">You can also control specific details of the discovery endpoint.</span></span> <span data-ttu-id="24975-136">Questa operazione viene effettuata tramite <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span><span class="sxs-lookup"><span data-stu-id="24975-136">This is done through the <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span></span> <span data-ttu-id="24975-137">In questo esempio, viene modificata la versione del protocollo utilizzata e viene aggiunto un attributo `maxResponseDelay`, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="24975-137">In this sample, the version of the protocol used is modified as well as adding a `maxResponseDelay` attribute as shown in the following code example.</span></span>  
  
```xml  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
```  
  
 <span data-ttu-id="24975-138">Di seguito è riportato il file di configurazione completo utilizzato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="24975-138">The following is the complete configuration file used in this example:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
  
      <services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
         <!-- Define the discovery endpoint -->            
<endpoint name="udpDiscovery" kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
      <behaviors>  
  
        <serviceBehaviors>  
          <behavior name="calculatorServiceBehavior">  
  
            <!-- Add an announcement endpoint -->  
            <serviceDiscovery>  
              <announcementEndpoints>  
                <endpoint kind="udpAnnouncementEndpoint"/>  
              </announcementEndpoints>  
            </serviceDiscovery>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <!-- Add scopes used to identify the service -->  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
  
      </behaviors>  
  
      <standardEndpoints>  
        <udpDiscoveryEndpoint>  
         <!-- Configure the UDP discovery endpoint -->  
          <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
        </udpDiscoveryEndpoint>  
      </standardEndpoints>  
  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client-configuration"></a><span data-ttu-id="24975-139">Configurazione del client</span><span class="sxs-lookup"><span data-stu-id="24975-139">Client Configuration</span></span>  
 <span data-ttu-id="24975-140">Nel file di configurazione dell'applicazione per il client, un oggetto `standardEndpoint` di tipo `dynamicEndpoint` viene impiegato per utilizzare l'individuazione come illustrato nel frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="24975-140">In the application configuration file for the client, a `standardEndpoint` of type `dynamicEndpoint` is used to utilize discovery as shown in the following config snippet.</span></span>  
  
```xml  
<client>  
   <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
   <endpoint name="calculatorEndpoint"  
             binding="wsHttpBinding"  
             contract="ICalculatorService"  
             kind ="dynamicEndpoint"  
             endpointConfiguration="dynamicEndpointConfiguration">  
   </endpoint>  
</client>  
```  
  
 <span data-ttu-id="24975-141">Quando un client sta utilizzando un `dynamicEndpoint`, il runtime esegue automaticamente l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="24975-141">When a client is using a `dynamicEndpoint`, the runtime performs discovery automatically.</span></span> <span data-ttu-id="24975-142">Durante l'individuazione vengono utilizzate varie impostazioni, ad esempio quelle definite nella sezione `discoveryClientSettings`, in cui viene specificato il tipo di endpoint di individuazione da utilizzare:</span><span class="sxs-lookup"><span data-stu-id="24975-142">Various settings are used during discovery, such as those defined in the  `discoveryClientSettings` section, which specifies the type of discovery endpoint to use:</span></span>  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
```  
  
 <span data-ttu-id="24975-143">Criteri di ricerca utilizzati per cercare i servizi:</span><span class="sxs-lookup"><span data-stu-id="24975-143">The find criteria used to search for services:</span></span>  
  
```xml  
<!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
<findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
   <scopes>  
      <add scope="http://www.microsoft.com/building42/floor1"/>  
   </scopes>  
   <!-- These extensions are sent from the client to the service as part of the probe message -->  
   <extensions>  
      <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
   </extensions>  
</findCriteria>  
```  
  
 <span data-ttu-id="24975-144">L'esempio estende tale funzionalità e modifica i <xref:System.ServiceModel.Discovery.FindCriteria> utilizzati dal client e alcune proprietà dell'`updDiscoveryEndpoint` standard utilizzate per l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="24975-144">This sample extends this feature and modifies the <xref:System.ServiceModel.Discovery.FindCriteria> used by the client, as well as some properties of the standard `updDiscoveryEndpoint` used for discovery.</span></span> <span data-ttu-id="24975-145">I <xref:System.ServiceModel.Discovery.FindCriteria> vengono modificati per utilizzare un ambito e un algoritmo `scopeMatchBy` specifico, oltre a criteri di chiusura personalizzati.</span><span class="sxs-lookup"><span data-stu-id="24975-145">The <xref:System.ServiceModel.Discovery.FindCriteria> are modified to use a scope and a specific `scopeMatchBy` algorithm, as well as custom termination criteria.</span></span> <span data-ttu-id="24975-146">Inoltre, l'esempio mostra anche come un client è in grado di inviare elementi XML utilizzando messaggi `Probe`.</span><span class="sxs-lookup"><span data-stu-id="24975-146">Furthermore, the sample also shows how a client can send XML elements using `Probe` messages.</span></span> <span data-ttu-id="24975-147">Infine, alcune modifiche vengono apportate a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, ad esempio la versione del protocollo utilizzata e impostazioni specifiche dell'UDP, come mostrato nel file di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="24975-147">Lastly, some changes are made to the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, such as the version of the protocol used and UDP-specific settings as shown in the following configuration file.</span></span>  
  
```xml  
<udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
```  
  
 <span data-ttu-id="24975-148">Di seguito è riportata la configurazione client completa utilizzata nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="24975-148">The following is the complete client configuration used in the sample.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
      <endpoint name="calculatorEndpoint"  
                binding="wsHttpBinding"  
                contract="ICalculatorService"  
                kind ="dynamicEndpoint"  
                endpointConfiguration="dynamicEndpointConfiguration">  
      </endpoint>  
    </client>  
  
    <standardEndpoints>  
  
      <dynamicEndpoint>        
        <standardEndpoint name="dynamicEndpointConfiguration">  
          <discoveryClientSettings>  
            <!-- Controls where the discovery happens. In this case, Probe message is sent over UdpDiscoveryEndpoint. -->  
            <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
            <!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
            <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>  
              <!-- These extensions are sent from the client to the service as part of the probe message -->  
              <extensions>  
                <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
              </extensions>  
            </findCriteria>  
          </discoveryClientSettings>  
        </standardEndpoint>     
      </dynamicEndpoint>  
  
      <udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
  
    </standardEndpoints>  
  
  </system.serviceModel>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="24975-149">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="24975-149">To use this sample</span></span>  
  
1. <span data-ttu-id="24975-150">Questo esempio usa endpoint HTTP e per eseguirlo è necessario aggiungere elenchi di controllo di accesso (ACL) agli URL appropriati.</span><span class="sxs-lookup"><span data-stu-id="24975-150">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="24975-151">Per ulteriori informazioni, vedere [configurazione di http e HTTPS](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="24975-151">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="24975-152">L'esecuzione del comando seguente con privilegi elevati consente di aggiungere gli elenchi di controllo di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="24975-152">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="24975-153">È possibile che si desideri sostituire il dominio e il nome utente per gli argomenti seguenti quando il comando non funziona nella forma originale.</span><span class="sxs-lookup"><span data-stu-id="24975-153">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2. <span data-ttu-id="24975-154">Compila la soluzione.</span><span class="sxs-lookup"><span data-stu-id="24975-154">Build the solution.</span></span>  
  
3. <span data-ttu-id="24975-155">Eseguire il servizio eseguibile dalla directory di compilazione.</span><span class="sxs-lookup"><span data-stu-id="24975-155">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="24975-156">Eseguire il file eseguibile del client.</span><span class="sxs-lookup"><span data-stu-id="24975-156">Run the client executable.</span></span> <span data-ttu-id="24975-157">Il client è in grado di individuare il servizio.</span><span class="sxs-lookup"><span data-stu-id="24975-157">Note that the client is able to locate the service.</span></span>  
