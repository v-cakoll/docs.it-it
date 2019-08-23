---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 8fcb5ac0c552d1ac2e849c95a5c0757d0c142f3d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926390"
---
# <a name="behaviors"></a><span data-ttu-id="d6d2d-101">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="d6d2d-101">\<behaviors></span></span>
<span data-ttu-id="d6d2d-102">Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="d6d2d-103">Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="d6d2d-104">Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="d6d2d-105">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d6d2d-106">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d6d2d-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="d6d2d-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6d2d-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6d2d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6d2d-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6d2d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6d2d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d6d2d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6d2d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6d2d-111">Attributes</span></span>  
 <span data-ttu-id="d6d2d-112">Nessuna</span><span class="sxs-lookup"><span data-stu-id="d6d2d-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6d2d-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6d2d-113">Child Elements</span></span>  
  
|<span data-ttu-id="d6d2d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6d2d-114">Element</span></span>|<span data-ttu-id="d6d2d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6d2d-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6d2d-116">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d6d2d-116">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="d6d2d-117">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="d6d2d-118">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d6d2d-118">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="d6d2d-119">Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6d2d-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6d2d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d6d2d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6d2d-121">Element</span></span>|<span data-ttu-id="d6d2d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6d2d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6d2d-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d6d2d-123">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="d6d2d-124">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d6d2d-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6d2d-125">Note</span><span class="sxs-lookup"><span data-stu-id="d6d2d-125">Remarks</span></span>  
 <span data-ttu-id="d6d2d-126">È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="d6d2d-127">A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="d6d2d-128">È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="d6d2d-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d2d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6d2d-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="d6d2d-130">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="d6d2d-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="d6d2d-131">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="d6d2d-131">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="d6d2d-132">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="d6d2d-132">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="d6d2d-133">Specifica del comportamento in fase di esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="d6d2d-133">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="d6d2d-134">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6d2d-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
