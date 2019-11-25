---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139696"
---
# <a name="behaviors"></a><span data-ttu-id="463f2-101">comportamenti di \<</span><span class="sxs-lookup"><span data-stu-id="463f2-101">\<behaviors></span></span>
<span data-ttu-id="463f2-102">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="463f2-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="463f2-103">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="463f2-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="463f2-104">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="463f2-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="463f2-105">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="463f2-105">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="463f2-106">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="463f2-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="463f2-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="463f2-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="463f2-108">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="463f2-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="463f2-109">&nbsp;&nbsp;&nbsp;**comportamenti\<** &nbsp;</span><span class="sxs-lookup"><span data-stu-id="463f2-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="463f2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="463f2-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="463f2-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="463f2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="463f2-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="463f2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="463f2-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="463f2-113">Attributes</span></span>  
 <span data-ttu-id="463f2-114">Nessuno</span><span class="sxs-lookup"><span data-stu-id="463f2-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="463f2-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="463f2-115">Child Elements</span></span>  
  
|<span data-ttu-id="463f2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="463f2-116">Element</span></span>|<span data-ttu-id="463f2-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="463f2-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="463f2-118">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="463f2-118">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="463f2-119">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="463f2-119">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="463f2-120">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="463f2-120">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="463f2-121">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="463f2-121">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="463f2-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="463f2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="463f2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="463f2-123">Element</span></span>|<span data-ttu-id="463f2-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="463f2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="463f2-125">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="463f2-125">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="463f2-126">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="463f2-126">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="463f2-127">Note</span><span class="sxs-lookup"><span data-stu-id="463f2-127">Remarks</span></span>  
 <span data-ttu-id="463f2-128">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="463f2-128">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="463f2-129">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="463f2-129">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="463f2-130">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="463f2-130">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="463f2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="463f2-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="463f2-132">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="463f2-132">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="463f2-133">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="463f2-133">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="463f2-134">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="463f2-134">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="463f2-135">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="463f2-135">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="463f2-136">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="463f2-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
