---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139696"
---
# \<behaviors>
<span data-ttu-id="85a71-101">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="85a71-101">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="85a71-102">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="85a71-102">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="85a71-103">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="85a71-103">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="85a71-104">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="85a71-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="85a71-105">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="85a71-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="85a71-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85a71-106">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85a71-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="85a71-107">Attributes and Elements</span></span>  
 <span data-ttu-id="85a71-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="85a71-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85a71-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="85a71-109">Attributes</span></span>  
 <span data-ttu-id="85a71-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="85a71-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="85a71-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="85a71-111">Child Elements</span></span>  
  
|<span data-ttu-id="85a71-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="85a71-112">Element</span></span>|<span data-ttu-id="85a71-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85a71-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="85a71-114">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="85a71-114">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="85a71-115">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="85a71-115">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85a71-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="85a71-116">Parent Elements</span></span>  
  
|<span data-ttu-id="85a71-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="85a71-117">Element</span></span>|<span data-ttu-id="85a71-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85a71-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="85a71-119">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="85a71-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85a71-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="85a71-120">Remarks</span></span>  
 <span data-ttu-id="85a71-121">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="85a71-121">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="85a71-122">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="85a71-122">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="85a71-123">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="85a71-123">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a71-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="85a71-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="85a71-125">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="85a71-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="85a71-126">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="85a71-126">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="85a71-127">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="85a71-127">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="85a71-128">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="85a71-128">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="85a71-129">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="85a71-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
