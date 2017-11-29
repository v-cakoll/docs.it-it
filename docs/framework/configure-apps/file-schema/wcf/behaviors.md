---
title: '&lt;comportamenti&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b38b27a7b196026e2ff873c7748ed46b96ba9b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="790e1-102">&lt;comportamenti&gt;</span><span class="sxs-lookup"><span data-stu-id="790e1-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="790e1-103">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="790e1-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="790e1-104">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="790e1-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="790e1-105">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="790e1-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="790e1-106">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="790e1-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="790e1-107">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="790e1-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="790e1-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="790e1-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790e1-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="790e1-109">Syntax</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="790e1-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="790e1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="790e1-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="790e1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="790e1-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="790e1-112">Attributes</span></span>  
 <span data-ttu-id="790e1-113">Nessuna</span><span class="sxs-lookup"><span data-stu-id="790e1-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="790e1-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="790e1-114">Child Elements</span></span>  
  
|<span data-ttu-id="790e1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="790e1-115">Element</span></span>|<span data-ttu-id="790e1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="790e1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="790e1-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="790e1-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="790e1-118">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="790e1-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="790e1-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="790e1-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="790e1-120">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="790e1-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="790e1-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="790e1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="790e1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="790e1-122">Element</span></span>|<span data-ttu-id="790e1-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="790e1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="790e1-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="790e1-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="790e1-125">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="790e1-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="790e1-126">Note</span><span class="sxs-lookup"><span data-stu-id="790e1-126">Remarks</span></span>  
 <span data-ttu-id="790e1-127">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="790e1-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="790e1-128">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="790e1-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="790e1-129">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="790e1-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790e1-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="790e1-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="790e1-131">La configurazione e l'estensione del Runtime dei comportamenti</span><span class="sxs-lookup"><span data-stu-id="790e1-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="790e1-132">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="790e1-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="790e1-133">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="790e1-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="790e1-134">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="790e1-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="790e1-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="790e1-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
