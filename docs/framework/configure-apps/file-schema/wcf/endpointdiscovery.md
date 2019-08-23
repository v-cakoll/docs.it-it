---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 5cb64c54067ba695f67d86c0026db77ebbe7d5ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919043"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="d34a0-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="d34a0-101">\<endpointDiscovery></span></span>
<span data-ttu-id="d34a0-102">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="d34a0-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="d34a0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d34a0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d34a0-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="d34a0-104">\<behaviors></span></span>  
<span data-ttu-id="d34a0-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d34a0-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="d34a0-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="d34a0-106">\<behavior></span></span>  
<span data-ttu-id="d34a0-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="d34a0-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34a0-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d34a0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d34a0-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d34a0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d34a0-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d34a0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d34a0-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d34a0-111">Attributes</span></span>  
  
|<span data-ttu-id="d34a0-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d34a0-112">Attribute</span></span>|<span data-ttu-id="d34a0-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d34a0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d34a0-114">enabled</span><span class="sxs-lookup"><span data-stu-id="d34a0-114">enabled</span></span>|<span data-ttu-id="d34a0-115">Valore booleano che specifica se è abilitata l'individuabilità sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d34a0-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="d34a0-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="d34a0-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d34a0-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d34a0-117">Child Elements</span></span>  
  
|<span data-ttu-id="d34a0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d34a0-118">Element</span></span>|<span data-ttu-id="d34a0-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d34a0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d34a0-120">\<ambiti ></span><span class="sxs-lookup"><span data-stu-id="d34a0-120">\<scopes></span></span>](scopes.md)|<span data-ttu-id="d34a0-121">Raccolta di URI di ambito per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d34a0-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="d34a0-122">A un singolo endpoint è possibile associare più URI di ambito.</span><span class="sxs-lookup"><span data-stu-id="d34a0-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="d34a0-123">estensioni > [of \<endpointDiscovery >] [ \<](extensions.md)</span><span class="sxs-lookup"><span data-stu-id="d34a0-123">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="d34a0-124">Raccolta di elementi XML che consente di specificare metadati personalizzati da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="d34a0-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="d34a0-125">\<tipi ></span><span class="sxs-lookup"><span data-stu-id="d34a0-125">\<types></span></span>|<span data-ttu-id="d34a0-126">Raccolta di interfacce da cercare.</span><span class="sxs-lookup"><span data-stu-id="d34a0-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d34a0-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d34a0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d34a0-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d34a0-128">Element</span></span>|<span data-ttu-id="d34a0-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d34a0-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d34a0-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d34a0-130">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d34a0-131">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="d34a0-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="d34a0-132">Note</span><span class="sxs-lookup"><span data-stu-id="d34a0-132">Remarks</span></span>  
 <span data-ttu-id="d34a0-133">L'aggiunta di questo elemento di configurazione alla configurazione di comportamento dell'endpoint con l'attributo `enabled` impostato su `true` ne determina l'abilitazione dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="d34a0-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="d34a0-134">Inoltre, è possibile utilizzare gli [ \<ambiti >](scopes.md)elemento figlio per specificare gli URI di ambito personalizzati che possono essere utilizzati per filtrare gli endpoint di servizio durante la query, nonché le [ \<estensioni >](extensions.md) elemento figlio per specificare Custom metadati che devono essere pubblicati insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, scope e ListenURI).</span><span class="sxs-lookup"><span data-stu-id="d34a0-134">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="d34a0-135">Questo elemento di configurazione dipende [ \<dall'elemento > serviceDiscovery](servicediscovery.md) che fornisce il controllo del livello di servizio dell'individuabilità.</span><span class="sxs-lookup"><span data-stu-id="d34a0-135">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="d34a0-136">Questo significa che le impostazioni di questo elemento vengono ignorate se [ \<serviceDiscovery >](servicediscovery.md) non è presente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="d34a0-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d34a0-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="d34a0-137">Example</span></span>  
 <span data-ttu-id="d34a0-138">Nell'esempio di configurazione seguente vengono specificati ambiti di filtro e metadati di estensione da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="d34a0-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d34a0-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d34a0-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
