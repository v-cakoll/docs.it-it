---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398012"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="e5ae2-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="e5ae2-101">\<endpointDiscovery></span></span>
<span data-ttu-id="e5ae2-102">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="e5ae2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5ae2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5ae2-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5ae2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e5ae2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5ae2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e5ae2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5ae2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e5ae2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e5ae2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e5ae2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> endpointDiscovery**</span><span class="sxs-lookup"><span data-stu-id="e5ae2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ae2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5ae2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5ae2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e5ae2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5ae2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5ae2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e5ae2-112">Attributes</span></span>  
  
|<span data-ttu-id="e5ae2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e5ae2-113">Attribute</span></span>|<span data-ttu-id="e5ae2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5ae2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5ae2-115">enabled</span><span class="sxs-lookup"><span data-stu-id="e5ae2-115">enabled</span></span>|<span data-ttu-id="e5ae2-116">Valore booleano che specifica se è abilitata l'individuabilità sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-116">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="e5ae2-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5ae2-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e5ae2-118">Child Elements</span></span>  
  
|<span data-ttu-id="e5ae2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5ae2-119">Element</span></span>|<span data-ttu-id="e5ae2-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5ae2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5ae2-121">\<ambiti ></span><span class="sxs-lookup"><span data-stu-id="e5ae2-121">\<scopes></span></span>](scopes.md)|<span data-ttu-id="e5ae2-122">Raccolta di URI di ambito per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="e5ae2-123">A un singolo endpoint è possibile associare più URI di ambito.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="e5ae2-124">estensioni > [of \<endpointDiscovery >] [ \<](extensions.md)</span><span class="sxs-lookup"><span data-stu-id="e5ae2-124">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="e5ae2-125">Raccolta di elementi XML che consente di specificare metadati personalizzati da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="e5ae2-126">\<tipi ></span><span class="sxs-lookup"><span data-stu-id="e5ae2-126">\<types></span></span>|<span data-ttu-id="e5ae2-127">Raccolta di interfacce da cercare.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5ae2-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e5ae2-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e5ae2-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5ae2-129">Element</span></span>|<span data-ttu-id="e5ae2-130">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e5ae2-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5ae2-131">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e5ae2-131">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e5ae2-132">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="e5ae2-133">Note</span><span class="sxs-lookup"><span data-stu-id="e5ae2-133">Remarks</span></span>  
 <span data-ttu-id="e5ae2-134">L'aggiunta di questo elemento di configurazione alla configurazione di comportamento dell'endpoint con l'attributo `enabled` impostato su `true` ne determina l'abilitazione dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="e5ae2-135">Inoltre, è possibile utilizzare gli [ \<ambiti >](scopes.md)elemento figlio per specificare gli URI di ambito personalizzati che possono essere utilizzati per filtrare gli endpoint di servizio durante la query, nonché le [ \<estensioni >](extensions.md) elemento figlio per specificare Custom metadati che devono essere pubblicati insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, scope e ListenURI).</span><span class="sxs-lookup"><span data-stu-id="e5ae2-135">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="e5ae2-136">Questo elemento di configurazione dipende [ \<dall'elemento > serviceDiscovery](servicediscovery.md) che fornisce il controllo del livello di servizio dell'individuabilità.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-136">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="e5ae2-137">Questo significa che le impostazioni di questo elemento vengono ignorate se [ \<serviceDiscovery >](servicediscovery.md) non è presente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5ae2-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5ae2-138">Example</span></span>  
 <span data-ttu-id="e5ae2-139">Nell'esempio di configurazione seguente vengono specificati ambiti di filtro e metadati di estensione da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5ae2-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5ae2-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5ae2-140">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
