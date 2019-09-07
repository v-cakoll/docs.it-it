---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: a87966f643fe46d0ef69f843dc306151ca7c18bb
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400587"
---
# <a name="behaviors"></a><span data-ttu-id="979b9-101">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="979b9-101">\<behaviors></span></span>
<span data-ttu-id="979b9-102">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="979b9-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="979b9-103">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="979b9-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="979b9-104">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="979b9-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="979b9-105">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="979b9-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="979b9-106">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="979b9-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="979b9-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="979b9-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="979b9-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="979b9-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="979b9-109">&nbsp;&nbsp;&nbsp;&nbsp; **\<comportamenti >**</span><span class="sxs-lookup"><span data-stu-id="979b9-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="979b9-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="979b9-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="979b9-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="979b9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="979b9-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="979b9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="979b9-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="979b9-113">Attributes</span></span>  
 <span data-ttu-id="979b9-114">Nessuna</span><span class="sxs-lookup"><span data-stu-id="979b9-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="979b9-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="979b9-115">Child Elements</span></span>  
  
|<span data-ttu-id="979b9-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="979b9-116">Element</span></span>|<span data-ttu-id="979b9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="979b9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="979b9-118">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="979b9-118">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="979b9-119">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="979b9-119">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="979b9-120">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="979b9-120">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="979b9-121">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="979b9-121">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="979b9-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="979b9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="979b9-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="979b9-123">Element</span></span>|<span data-ttu-id="979b9-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="979b9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="979b9-125">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="979b9-125">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="979b9-126">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="979b9-126">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="979b9-127">Note</span><span class="sxs-lookup"><span data-stu-id="979b9-127">Remarks</span></span>  
 <span data-ttu-id="979b9-128">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="979b9-128">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="979b9-129">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="979b9-129">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="979b9-130">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="979b9-130">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="979b9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="979b9-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="979b9-132">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="979b9-132">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="979b9-133">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="979b9-133">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="979b9-134">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="979b9-134">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="979b9-135">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="979b9-135">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="979b9-136">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="979b9-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
