---
title: '&lt;endpointDiscovery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a997ddffa2267cdeb9e54bb98d4122db254104d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltendpointdiscoverygt"></a><span data-ttu-id="84e21-102">&lt;endpointDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="84e21-102">&lt;endpointDiscovery&gt;</span></span>
<span data-ttu-id="84e21-103">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="84e21-103">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="84e21-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="84e21-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="84e21-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="84e21-105">\<behaviors></span></span>  
<span data-ttu-id="84e21-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="84e21-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="84e21-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="84e21-107">\<behavior></span></span>  
<span data-ttu-id="84e21-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="84e21-108">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e21-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84e21-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84e21-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="84e21-110">Attributes and Elements</span></span>  
 <span data-ttu-id="84e21-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="84e21-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84e21-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="84e21-112">Attributes</span></span>  
  
|<span data-ttu-id="84e21-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="84e21-113">Attribute</span></span>|<span data-ttu-id="84e21-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84e21-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84e21-115">enabled</span><span class="sxs-lookup"><span data-stu-id="84e21-115">enabled</span></span>|<span data-ttu-id="84e21-116">Valore booleano che specifica se è abilitata l'individuazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="84e21-116">A Boolean value that that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="84e21-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="84e21-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84e21-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="84e21-118">Child Elements</span></span>  
  
|<span data-ttu-id="84e21-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="84e21-119">Element</span></span>|<span data-ttu-id="84e21-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84e21-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84e21-121">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="84e21-121">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="84e21-122">Raccolta di URI di ambito per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="84e21-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="84e21-123">A un singolo endpoint è possibile associare più URI di ambito.</span><span class="sxs-lookup"><span data-stu-id="84e21-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="84e21-124">[\<estensioni >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [di \<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="84e21-124">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="84e21-125">Raccolta di elementi XML che consente di specificare metadati personalizzati da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="84e21-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="84e21-126">\<tipi ></span><span class="sxs-lookup"><span data-stu-id="84e21-126">\<types></span></span>|<span data-ttu-id="84e21-127">Raccolta di interfacce da cercare.</span><span class="sxs-lookup"><span data-stu-id="84e21-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84e21-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="84e21-128">Parent Elements</span></span>  
  
|<span data-ttu-id="84e21-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="84e21-129">Element</span></span>|<span data-ttu-id="84e21-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84e21-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84e21-131">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="84e21-131">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="84e21-132">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="84e21-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="84e21-133">Note</span><span class="sxs-lookup"><span data-stu-id="84e21-133">Remarks</span></span>  
 <span data-ttu-id="84e21-134">L'aggiunta di questo elemento di configurazione alla configurazione di comportamento dell'endpoint con l'attributo `enabled` impostato su `true` ne determina l'abilitazione dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="84e21-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="84e21-135">Inoltre, è possibile utilizzare il [ \<ambiti >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)elemento figlio per specificare l'URI che possono essere usato per filtrare gli endpoint del servizio durante l'esecuzione di query, di ambito personalizzati, nonché [ \<estensioni >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) elemento figlio di specificare metadati personalizzati che devono essere pubblicati insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, ambito e ListenURI).</span><span class="sxs-lookup"><span data-stu-id="84e21-135">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="84e21-136">Questo elemento di configurazione dipende il [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento che fornisce il controllo a livello di servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="84e21-136">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="84e21-137">Ciò significa che le impostazioni di questo elemento vengono ignorate se [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) non è presente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="84e21-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84e21-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="84e21-138">Example</span></span>  
 <span data-ttu-id="84e21-139">Nell'esempio di configurazione seguente vengono specificati ambiti di filtro e metadati di estensione da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="84e21-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enabled="true">  
        <scopes>  
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
        </scopes>  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84e21-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84e21-140">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
