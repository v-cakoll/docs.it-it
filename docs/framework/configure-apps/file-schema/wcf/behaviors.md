---
title: '&lt;Comportamenti&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 4396aefd982dd29c6a9c9f2be9f2af43d00671b2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150097"
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="cec40-102">&lt;Comportamenti&gt;</span><span class="sxs-lookup"><span data-stu-id="cec40-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="cec40-103">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="cec40-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="cec40-104">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="cec40-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="cec40-105">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="cec40-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="cec40-106">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="cec40-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="cec40-107">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="cec40-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="cec40-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cec40-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec40-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cec40-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cec40-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cec40-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cec40-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cec40-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cec40-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cec40-112">Attributes</span></span>  
 <span data-ttu-id="cec40-113">nessuno</span><span class="sxs-lookup"><span data-stu-id="cec40-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cec40-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cec40-114">Child Elements</span></span>  
  
|<span data-ttu-id="cec40-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cec40-115">Element</span></span>|<span data-ttu-id="cec40-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cec40-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cec40-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cec40-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="cec40-118">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="cec40-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="cec40-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cec40-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="cec40-120">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="cec40-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cec40-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cec40-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cec40-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cec40-122">Element</span></span>|<span data-ttu-id="cec40-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cec40-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cec40-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cec40-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="cec40-125">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cec40-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cec40-126">Note</span><span class="sxs-lookup"><span data-stu-id="cec40-126">Remarks</span></span>  
 <span data-ttu-id="cec40-127">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="cec40-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="cec40-128">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="cec40-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="cec40-129">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="cec40-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec40-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cec40-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="cec40-131">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="cec40-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="cec40-132">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="cec40-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="cec40-133">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="cec40-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="cec40-134">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="cec40-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="cec40-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cec40-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
