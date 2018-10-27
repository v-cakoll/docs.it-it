---
title: '&lt;mexTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: dbe9e6c3b7a515ee4b5bb147f973423df0f175ea
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187699"
---
# <a name="ltmextcpbindinggt"></a><span data-ttu-id="1243e-102">&lt;mexTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1243e-102">&lt;mexTcpBinding&gt;</span></span>
<span data-ttu-id="1243e-103">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite TCP.</span><span class="sxs-lookup"><span data-stu-id="1243e-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="1243e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1243e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1243e-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1243e-105">\<bindings></span></span>  
<span data-ttu-id="1243e-106">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="1243e-106">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1243e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1243e-107">Syntax</span></span>  
  
```xml  
<mexTcpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1243e-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1243e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1243e-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1243e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1243e-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1243e-110">Attributes</span></span>  
  
|<span data-ttu-id="1243e-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1243e-111">Attribute</span></span>|<span data-ttu-id="1243e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1243e-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="1243e-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="1243e-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="1243e-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1243e-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1243e-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1243e-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="1243e-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="1243e-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="1243e-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="1243e-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="1243e-118">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="1243e-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="1243e-119">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="1243e-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="1243e-120">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="1243e-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1243e-121">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1243e-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="1243e-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="1243e-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="1243e-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1243e-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1243e-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1243e-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="1243e-125">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="1243e-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="1243e-126">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1243e-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1243e-127">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="1243e-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="1243e-128">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="1243e-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="1243e-129">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="1243e-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1243e-130">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1243e-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1243e-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1243e-131">Child Elements</span></span>  
 <span data-ttu-id="1243e-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1243e-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1243e-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1243e-133">Parent Elements</span></span>  
  
|<span data-ttu-id="1243e-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="1243e-134">Element</span></span>|<span data-ttu-id="1243e-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1243e-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1243e-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1243e-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="1243e-137">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1243e-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1243e-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1243e-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MexTcpBindingElement>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>  
 [<span data-ttu-id="1243e-139">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1243e-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="1243e-140">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="1243e-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="1243e-141">Metadati</span><span class="sxs-lookup"><span data-stu-id="1243e-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="1243e-142">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1243e-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1243e-143">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1243e-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1243e-144">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="1243e-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="1243e-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="1243e-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
