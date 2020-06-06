---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398012"
---
# \<endpointDiscovery>
<span data-ttu-id="889c9-101">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="889c9-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="889c9-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="889c9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="889c9-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="889c9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="889c9-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="889c9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="889c9-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="889c9-105">Attributes</span></span>  
  
|<span data-ttu-id="889c9-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="889c9-106">Attribute</span></span>|<span data-ttu-id="889c9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="889c9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="889c9-108">Enabled</span><span class="sxs-lookup"><span data-stu-id="889c9-108">enabled</span></span>|<span data-ttu-id="889c9-109">Valore booleano che specifica se è abilitata l'individuabilità sull'endpoint.</span><span class="sxs-lookup"><span data-stu-id="889c9-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="889c9-110">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="889c9-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="889c9-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="889c9-111">Child Elements</span></span>  
  
|<span data-ttu-id="889c9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="889c9-112">Element</span></span>|<span data-ttu-id="889c9-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="889c9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="889c9-114">Raccolta di URI di ambito per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="889c9-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="889c9-115">A un singolo endpoint è possibile associare più URI di ambito.</span><span class="sxs-lookup"><span data-stu-id="889c9-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="889c9-116">[\<extensions>](extensions.md)[di \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="889c9-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="889c9-117">Raccolta di elementi XML che consente di specificare metadati personalizzati da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="889c9-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="889c9-118">Raccolta di interfacce da cercare.</span><span class="sxs-lookup"><span data-stu-id="889c9-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="889c9-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="889c9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="889c9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="889c9-120">Element</span></span>|<span data-ttu-id="889c9-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="889c9-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="889c9-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="889c9-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="889c9-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="889c9-123">Remarks</span></span>  
 <span data-ttu-id="889c9-124">L'aggiunta di questo elemento di configurazione alla configurazione di comportamento dell'endpoint con l'attributo `enabled` impostato su `true` ne determina l'abilitazione dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="889c9-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="889c9-125">Inoltre, è possibile utilizzare l' [\<scopes>](scopes.md) elemento figlio per specificare gli URI di ambito personalizzati che possono essere utilizzati per filtrare gli endpoint di servizio durante la query, nonché l' [\<extensions>](extensions.md) elemento figlio per specificare metadati personalizzati da pubblicare insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, scope e ListenUri).</span><span class="sxs-lookup"><span data-stu-id="889c9-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="889c9-126">Questo elemento di configurazione dipende dall' [\<serviceDiscovery>](servicediscovery.md) elemento che fornisce il controllo del livello di servizio dell'individuabilità.</span><span class="sxs-lookup"><span data-stu-id="889c9-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="889c9-127">Ciò significa che le impostazioni di questo elemento vengono ignorate se [\<serviceDiscovery>](servicediscovery.md) non è presente nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="889c9-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="889c9-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="889c9-128">Example</span></span>  
 <span data-ttu-id="889c9-129">Nell'esempio di configurazione seguente vengono specificati ambiti di filtro e metadati di estensione da pubblicare per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="889c9-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="889c9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="889c9-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
