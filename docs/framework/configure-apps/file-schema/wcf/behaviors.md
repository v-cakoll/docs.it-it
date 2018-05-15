---
title: '&lt;Comportamenti&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: ca9cf5daa6590c14d4b5fd15c502d67af1f93b52
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="cbcda-102">&lt;Comportamenti&gt;</span><span class="sxs-lookup"><span data-stu-id="cbcda-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="cbcda-103">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="cbcda-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="cbcda-104">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="cbcda-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="cbcda-105">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="cbcda-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="cbcda-106">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="cbcda-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="cbcda-107">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="cbcda-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="cbcda-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cbcda-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbcda-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbcda-109">Syntax</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbcda-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cbcda-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cbcda-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cbcda-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbcda-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cbcda-112">Attributes</span></span>  
 <span data-ttu-id="cbcda-113">Nessuno</span><span class="sxs-lookup"><span data-stu-id="cbcda-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cbcda-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cbcda-114">Child Elements</span></span>  
  
|<span data-ttu-id="cbcda-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cbcda-115">Element</span></span>|<span data-ttu-id="cbcda-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbcda-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbcda-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cbcda-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="cbcda-118">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="cbcda-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="cbcda-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cbcda-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="cbcda-120">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="cbcda-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cbcda-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cbcda-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cbcda-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cbcda-122">Element</span></span>|<span data-ttu-id="cbcda-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbcda-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbcda-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cbcda-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="cbcda-125">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cbcda-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbcda-126">Note</span><span class="sxs-lookup"><span data-stu-id="cbcda-126">Remarks</span></span>  
 <span data-ttu-id="cbcda-127">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="cbcda-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="cbcda-128">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="cbcda-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="cbcda-129">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="cbcda-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbcda-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbcda-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="cbcda-131">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="cbcda-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="cbcda-132">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="cbcda-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="cbcda-133">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="cbcda-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="cbcda-134">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="cbcda-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="cbcda-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cbcda-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
