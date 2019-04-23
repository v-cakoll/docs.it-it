---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 108c349a44ed3ac902652f86241c1e96a622549b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204237"
---
# <a name="behaviors"></a><span data-ttu-id="c9bcf-101">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c9bcf-101">\<behaviors></span></span>
<span data-ttu-id="c9bcf-102">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="c9bcf-103">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="c9bcf-104">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="c9bcf-105">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c9bcf-106">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9bcf-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="c9bcf-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c9bcf-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bcf-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9bcf-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9bcf-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c9bcf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c9bcf-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9bcf-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c9bcf-111">Attributes</span></span>  
 <span data-ttu-id="c9bcf-112">nessuno</span><span class="sxs-lookup"><span data-stu-id="c9bcf-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9bcf-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c9bcf-113">Child Elements</span></span>  
  
|<span data-ttu-id="c9bcf-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9bcf-114">Element</span></span>|<span data-ttu-id="c9bcf-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9bcf-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9bcf-116">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c9bcf-116">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="c9bcf-117">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="c9bcf-118">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c9bcf-118">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="c9bcf-119">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9bcf-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c9bcf-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c9bcf-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9bcf-121">Element</span></span>|<span data-ttu-id="c9bcf-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9bcf-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9bcf-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c9bcf-123">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="c9bcf-124">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c9bcf-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9bcf-125">Note</span><span class="sxs-lookup"><span data-stu-id="c9bcf-125">Remarks</span></span>  
 <span data-ttu-id="c9bcf-126">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="c9bcf-127">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="c9bcf-128">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bcf-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9bcf-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="c9bcf-130">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="c9bcf-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="c9bcf-131">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="c9bcf-131">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="c9bcf-132">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="c9bcf-132">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="c9bcf-133">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="c9bcf-133">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="c9bcf-134">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9bcf-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
