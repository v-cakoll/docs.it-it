---
title: Configurazione semplificata
description: Informazioni sulla configurazione semplificata per i servizi WCF. .NET Framework 4.6.1 offre un modo per ridurre le dimensioni e la complessità della configurazione del servizio.
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: defaf536d5a5b9f1479271c0976b43e9b1eb5bc4
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246038"
---
# <a name="simplified-configuration"></a><span data-ttu-id="b60d6-104">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="b60d6-104">Simplified Configuration</span></span>
<span data-ttu-id="b60d6-105">La configurazione dei servizi Windows Communication Foundation (WCF) può essere un'attività complessa.</span><span class="sxs-lookup"><span data-stu-id="b60d6-105">Configuring Windows Communication Foundation (WCF) services can be a complex task.</span></span> <span data-ttu-id="b60d6-106">Esistono diverse opzioni e non è sempre semplice determinare quali impostazioni sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="b60d6-106">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="b60d6-107">Sebbene i file di configurazione aumentino la flessibilità dei servizi WCF, rappresentano anche l'origine di molti problemi difficili da trovare.</span><span class="sxs-lookup"><span data-stu-id="b60d6-107">While configuration files increase the flexibility of WCF services, they also are the source for many hard to find problems.</span></span> <span data-ttu-id="b60d6-108">In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] questi problemi vengono risolti e viene offerto un modo per ridurre la dimensione e la complessità della configurazione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="b60d6-108">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="b60d6-109">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="b60d6-109">Simplified Configuration</span></span>  
 <span data-ttu-id="b60d6-110">Nei file di configurazione del servizio WCF, la `system.serviceModel` sezione <> contiene un `service` elemento <> per ogni servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="b60d6-110">In WCF service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="b60d6-111">L' `service` elemento> <contiene una raccolta di `endpoint` elementi <> che specificano gli endpoint esposti per ogni servizio e, facoltativamente, un set di comportamenti del servizio.</span><span class="sxs-lookup"><span data-stu-id="b60d6-111">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="b60d6-112">Gli `endpoint` elementi <> specificano l'indirizzo, l'associazione e il contratto esposti dall'endpoint e, facoltativamente, l'associazione dei comportamenti dell'endpoint e della configurazione.</span><span class="sxs-lookup"><span data-stu-id="b60d6-112">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="b60d6-113">La `system.serviceModel` sezione <> contiene anche un `behaviors` elemento <> che consente di specificare i comportamenti del servizio o dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b60d6-113">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="b60d6-114">Nell'esempio seguente viene illustrata la `system.serviceModel` sezione <> di un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b60d6-114">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="b60d6-115">semplifica la configurazione di un servizio WCF rimuovendo il requisito per l' `service` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="b60d6-115">makes configuring a WCF service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="b60d6-116">Se non si aggiunge un <`service`> sezione o si aggiungono endpoint in una sezione <`service`> e il servizio non definisce alcun endpoint a livello di codice, viene automaticamente aggiunto al servizio un set di endpoint predefiniti, uno per ogni indirizzo di base del servizio e per ogni contratto implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b60d6-116">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="b60d6-117">In ognuno di questi endpoint l'indirizzo endpoint corrisponde all'indirizzo di base, l'associazione viene determinata dallo schema dell'indirizzo di base e il contratto corrisponde a quell'implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b60d6-117">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="b60d6-118">Se non è necessario specificare endpoint o comportamenti del servizio oppure apportare modifiche alle impostazioni dell'associazione, non è necessario specificare un file di configurazione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="b60d6-118">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="b60d6-119">Se un servizio implementa due contratti e l'host abilita sia il trasporto HTTP sia quello TCP, l'host del servizio crea quattro endpoint predefiniti, uno per ogni contratto che usa ogni trasporto.</span><span class="sxs-lookup"><span data-stu-id="b60d6-119">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="b60d6-120">Per creare endpoint predefiniti, l'host del servizio deve sapere quali associazioni usare.</span><span class="sxs-lookup"><span data-stu-id="b60d6-120">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="b60d6-121">Queste impostazioni vengono specificate in una `protocolMappings` sezione <> all'interno della `system.serviceModel` sezione <>.</span><span class="sxs-lookup"><span data-stu-id="b60d6-121">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="b60d6-122">La `protocolMappings` sezione <> contiene un elenco di schemi del protocollo di trasporto mappati ai tipi di associazione.</span><span class="sxs-lookup"><span data-stu-id="b60d6-122">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="b60d6-123">L'host del servizio usa gli indirizzi di base passati per determinare quale associazione usare.</span><span class="sxs-lookup"><span data-stu-id="b60d6-123">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="b60d6-124">Nell'esempio seguente viene usato l' `protocolMappings` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="b60d6-124">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="b60d6-125">La modifica di elementi predefiniti della configurazione, quali associazioni o comportamenti, potrebbe influire sugli eventuali servizi definiti nei livelli inferiori della gerarchia di configurazione che usino tali elementi.</span><span class="sxs-lookup"><span data-stu-id="b60d6-125">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="b60d6-126">Pertanto, quando ci si accinge a modificare le associazioni e i comportamenti predefiniti, tenere sempre presente che tali modifiche potrebbero avere effetto su altri servizi nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b60d6-126">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b60d6-127">I servizi ospitati in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS, Windows Process Activation Service) usano la directory virtuale come indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="b60d6-127">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="b60d6-128">Nell'esempio precedente un endpoint con un indirizzo di base che inizia con lo schema "http" usa <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="b60d6-128">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="b60d6-129">Un endpoint con un indirizzo di base che inizia con lo schema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="b60d6-129">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="b60d6-130">È possibile eseguire l'override delle impostazioni in un file App.config locale o un file Web.config.</span><span class="sxs-lookup"><span data-stu-id="b60d6-130">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="b60d6-131">Ogni elemento all'interno della `protocolMappings` sezione <> deve specificare uno schema e un'associazione.</span><span class="sxs-lookup"><span data-stu-id="b60d6-131">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="b60d6-132">Facoltativamente, è possibile specificare un `bindingConfiguration` attributo che specifichi una configurazione dell'associazione all'interno della `bindings` sezione <> del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b60d6-132">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="b60d6-133">Se non viene specificato alcun elemento `bindingConfiguration`, viene usata la configurazione di associazione anonima del tipo di associazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="b60d6-133">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="b60d6-134">I comportamenti del servizio vengono configurati per gli endpoint predefiniti usando <anonime `behavior`> sezioni all'interno <`serviceBehaviors` sezioni>.</span><span class="sxs-lookup"><span data-stu-id="b60d6-134">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="b60d6-135">`behavior`Per configurare i comportamenti del servizio vengono utilizzati tutti gli elementi <> senza nome all'interno `serviceBehaviors` di <>.</span><span class="sxs-lookup"><span data-stu-id="b60d6-135">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="b60d6-136">Il file di configurazione seguente abilita ad esempio la pubblicazione dei metadati del servizio per tutti i servizi all'interno del host.</span><span class="sxs-lookup"><span data-stu-id="b60d6-136">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 <span data-ttu-id="b60d6-137">I comportamenti dell'endpoint vengono configurati usando <anonime `behavior`> sezioni all'interno di <`serviceBehaviors`> sezioni.</span><span class="sxs-lookup"><span data-stu-id="b60d6-137">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="b60d6-138">L'esempio seguente è costituito da un file di configurazione equivalente a quello indicato all'inizio di questo argomento che usa il modello di configurazione semplificato.</span><span class="sxs-lookup"><span data-stu-id="b60d6-138">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> <span data-ttu-id="b60d6-139">Questa funzionalità si riferisce solo alla configurazione del servizio WCF, non alla configurazione client.</span><span class="sxs-lookup"><span data-stu-id="b60d6-139">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="b60d6-140">Nella maggior parte dei casi, la configurazione client WCF viene generata da uno strumento come svcutil.exe o aggiungendo un riferimento al servizio da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b60d6-140">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="b60d6-141">Se si configura manualmente un client WCF, sarà necessario aggiungere un \<client> elemento alla configurazione e specificare gli endpoint che si desidera chiamare.</span><span class="sxs-lookup"><span data-stu-id="b60d6-141">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60d6-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b60d6-142">See also</span></span>

- [<span data-ttu-id="b60d6-143">Configurazione dei servizi tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b60d6-143">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="b60d6-144">Configurazione di associazioni per servizi</span><span class="sxs-lookup"><span data-stu-id="b60d6-144">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="b60d6-145">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="b60d6-145">Configuring System-Provided Bindings</span></span>](./feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b60d6-146">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="b60d6-146">Configuring Services</span></span>](configuring-services.md)
- [<span data-ttu-id="b60d6-147">Configurazione dei servizi WCF</span><span class="sxs-lookup"><span data-stu-id="b60d6-147">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="b60d6-148">Configurazione dei servizi WCF nel codice</span><span class="sxs-lookup"><span data-stu-id="b60d6-148">Configuring WCF Services in Code</span></span>](configuring-wcf-services-in-code.md)
