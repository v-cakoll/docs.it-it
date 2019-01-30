---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 9d37a4918101b18c3002f2dcb926b9a03e0057a2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266333"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="11f5c-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="11f5c-101">\<mexHttpBinding></span></span>
<span data-ttu-id="11f5c-102">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="11f5c-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="11f5c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="11f5c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="11f5c-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="11f5c-104">\<bindings></span></span>  
<span data-ttu-id="11f5c-105">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="11f5c-105">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f5c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11f5c-106">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11f5c-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="11f5c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="11f5c-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="11f5c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11f5c-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="11f5c-109">Attributes</span></span>  
  
|<span data-ttu-id="11f5c-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="11f5c-110">Attribute</span></span>|<span data-ttu-id="11f5c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11f5c-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="11f5c-112">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="11f5c-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="11f5c-113">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11f5c-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11f5c-114">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11f5c-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="11f5c-115">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="11f5c-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="11f5c-116">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="11f5c-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="11f5c-117">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="11f5c-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="11f5c-118">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="11f5c-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="11f5c-119">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="11f5c-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="11f5c-120">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="11f5c-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="11f5c-121">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="11f5c-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="11f5c-122">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11f5c-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11f5c-123">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11f5c-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="11f5c-124">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="11f5c-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="11f5c-125">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11f5c-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11f5c-126">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="11f5c-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="11f5c-127">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="11f5c-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="11f5c-128">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="11f5c-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="11f5c-129">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="11f5c-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11f5c-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="11f5c-130">Child Elements</span></span>  
 <span data-ttu-id="11f5c-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="11f5c-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11f5c-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="11f5c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="11f5c-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="11f5c-133">Element</span></span>|<span data-ttu-id="11f5c-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11f5c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11f5c-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="11f5c-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="11f5c-136">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="11f5c-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11f5c-137">Note</span><span class="sxs-lookup"><span data-stu-id="11f5c-137">Remarks</span></span>  
 <span data-ttu-id="11f5c-138">Questa associazione è fondamentalmente un'associazione `WSHttpBinding` con sicurezza disabilitata.</span><span class="sxs-lookup"><span data-stu-id="11f5c-138">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="11f5c-139">Supporta la maggior parte delle richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="11f5c-139">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f5c-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11f5c-140">See also</span></span>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="11f5c-141">Procedura: Pubblicare i metadati per un servizio utilizzando un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="11f5c-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="11f5c-142">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="11f5c-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="11f5c-143">Metadati</span><span class="sxs-lookup"><span data-stu-id="11f5c-143">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="11f5c-144">Associazioni</span><span class="sxs-lookup"><span data-stu-id="11f5c-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="11f5c-145">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="11f5c-145">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="11f5c-146">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="11f5c-146">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="11f5c-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="11f5c-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
