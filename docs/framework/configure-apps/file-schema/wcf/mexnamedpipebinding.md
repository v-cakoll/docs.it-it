---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: f9f6186cc88f2cc0fed8404f9e4d5776d41e2818
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284863"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="d5b4b-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="d5b4b-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="d5b4b-102">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite named pipe.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="d5b4b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d5b4b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d5b4b-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="d5b4b-104">\<bindings></span></span>  
<span data-ttu-id="d5b4b-105">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="d5b4b-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b4b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5b4b-106">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5b4b-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d5b4b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d5b4b-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5b4b-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="d5b4b-109">Attributes</span></span>  
  
|<span data-ttu-id="d5b4b-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="d5b4b-110">Attribute</span></span>|<span data-ttu-id="d5b4b-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5b4b-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d5b4b-112">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d5b4b-113">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5b4b-114">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d5b4b-115">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d5b4b-116">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d5b4b-117">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="d5b4b-118">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="d5b4b-119">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d5b4b-120">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5b4b-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d5b4b-121">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d5b4b-122">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5b4b-123">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d5b4b-124">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d5b4b-125">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5b4b-126">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d5b4b-127">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d5b4b-128">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d5b4b-129">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5b4b-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d5b4b-130">Child Elements</span></span>  
 <span data-ttu-id="d5b4b-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5b4b-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d5b4b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d5b4b-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5b4b-133">Element</span></span>|<span data-ttu-id="d5b4b-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5b4b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5b4b-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d5b4b-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="d5b4b-136">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d5b4b-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5b4b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5b4b-137">See also</span></span>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="d5b4b-138">Procedura: Pubblicare i metadati per un servizio utilizzando un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d5b4b-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d5b4b-139">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="d5b4b-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="d5b4b-140">Metadati</span><span class="sxs-lookup"><span data-stu-id="d5b4b-140">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="d5b4b-141">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d5b4b-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d5b4b-142">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d5b4b-142">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d5b4b-143">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d5b4b-143">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d5b4b-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="d5b4b-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
