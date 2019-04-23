---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 125baba917a49135aaa426df2cfa1a4dbe8ac1e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119496"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="1ad09-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="1ad09-101">\<endpointDiscovery></span></span>
<span data-ttu-id="1ad09-102">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="1ad09-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="1ad09-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1ad09-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1ad09-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1ad09-104">\<behaviors></span></span>  
<span data-ttu-id="1ad09-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="1ad09-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="1ad09-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1ad09-106">\<behavior></span></span>  
<span data-ttu-id="1ad09-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="1ad09-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad09-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ad09-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ad09-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1ad09-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1ad09-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1ad09-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ad09-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ad09-111">Attributes</span></span>  
  
|<span data-ttu-id="1ad09-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="1ad09-112">Attribute</span></span>|<span data-ttu-id="1ad09-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ad09-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ad09-114">enabled</span><span class="sxs-lookup"><span data-stu-id="1ad09-114">enabled</span></span>|<span data-ttu-id="1ad09-115">Valore booleano che specifica se l'individuazione è abilitata in questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ad09-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="1ad09-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="1ad09-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ad09-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ad09-117">Child Elements</span></span>  
  
|<span data-ttu-id="1ad09-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ad09-118">Element</span></span>|<span data-ttu-id="1ad09-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ad09-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ad09-120">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="1ad09-120">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="1ad09-121">Raccolta di URI di ambito per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ad09-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="1ad09-122">A un singolo endpoint è possibile associare più URI di ambito.</span><span class="sxs-lookup"><span data-stu-id="1ad09-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="1ad09-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span><span class="sxs-lookup"><span data-stu-id="1ad09-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="1ad09-124">Raccolta di elementi XML che consente di specificare metadati personalizzati da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ad09-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="1ad09-125">\<types></span><span class="sxs-lookup"><span data-stu-id="1ad09-125">\<types></span></span>|<span data-ttu-id="1ad09-126">Raccolta di interfacce da cercare.</span><span class="sxs-lookup"><span data-stu-id="1ad09-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ad09-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1ad09-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1ad09-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ad09-128">Element</span></span>|<span data-ttu-id="1ad09-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ad09-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ad09-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1ad09-130">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1ad09-131">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="1ad09-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="1ad09-132">Note</span><span class="sxs-lookup"><span data-stu-id="1ad09-132">Remarks</span></span>  
 <span data-ttu-id="1ad09-133">L'aggiunta di questo elemento di configurazione alla configurazione di comportamento dell'endpoint con l'attributo `enabled` impostato su `true` ne determina l'abilitazione dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="1ad09-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="1ad09-134">Inoltre, è possibile usare la [ \<ambiti >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)elemento figlio alla definizione degli ambiti personalizzata gli URI che possono essere usati per filtrare gli endpoint di servizio durante l'esecuzione di query, nonché il [ \<estensioni >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) elemento figlio per specificare metadati personalizzati da pubblicare insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, ambito e ListenURI).</span><span class="sxs-lookup"><span data-stu-id="1ad09-134">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="1ad09-135">Questo elemento di configurazione dipende il [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento che fornisce il controllo a livello di servizio dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="1ad09-135">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="1ad09-136">Ciò significa che le impostazioni dell'elemento vengono ignorate se [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) non è presente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="1ad09-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ad09-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ad09-137">Example</span></span>  
 <span data-ttu-id="1ad09-138">Nell'esempio di configurazione seguente vengono specificati ambiti di filtro e metadati di estensione da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ad09-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
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
  
## <a name="see-also"></a><span data-ttu-id="1ad09-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ad09-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
