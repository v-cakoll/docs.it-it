---
title: '&lt;mexHttpsBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c78c1d90e10a45245f53f1db0b6400fa0a91d81b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltmexhttpsbindinggt"></a><span data-ttu-id="7fbfb-102">&lt;mexHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7fbfb-102">&lt;mexHttpsBinding&gt;</span></span>
<span data-ttu-id="7fbfb-103">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="7fbfb-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7fbfb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7fbfb-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="7fbfb-105">\<bindings></span></span>  
<span data-ttu-id="7fbfb-106">\<mexHttpsBinding ></span><span class="sxs-lookup"><span data-stu-id="7fbfb-106">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fbfb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fbfb-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fbfb-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7fbfb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7fbfb-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fbfb-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="7fbfb-110">Attributes</span></span>  
  
|<span data-ttu-id="7fbfb-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="7fbfb-111">Attribute</span></span>|<span data-ttu-id="7fbfb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbfb-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="7fbfb-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7fbfb-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fbfb-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="7fbfb-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7fbfb-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7fbfb-118">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="7fbfb-119">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="7fbfb-120">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7fbfb-121">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7fbfb-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="7fbfb-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7fbfb-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fbfb-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7fbfb-125">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7fbfb-126">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fbfb-127">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="7fbfb-128">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7fbfb-129">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fbfb-130">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fbfb-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7fbfb-131">Child Elements</span></span>  
 <span data-ttu-id="7fbfb-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7fbfb-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7fbfb-133">Parent Elements</span></span>  
  
|<span data-ttu-id="7fbfb-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fbfb-134">Element</span></span>|<span data-ttu-id="7fbfb-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbfb-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fbfb-136">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="7fbfb-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="7fbfb-137">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fbfb-138">Note</span><span class="sxs-lookup"><span data-stu-id="7fbfb-138">Remarks</span></span>  
 <span data-ttu-id="7fbfb-139">Questa associazione fondamentalmente un'associazione `WSHttpBinding` che supporta la sicurezza a livello di trasporto mediante certificati.</span><span class="sxs-lookup"><span data-stu-id="7fbfb-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="7fbfb-140">Per ulteriori informazioni sulla configurazione e l'utilizzo di un endpoint di metadati, vedere [procedura: configurare un'associazione di personalizzato WS-Metadata Exchange](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [procedura: recuperare metadati su un'associazione non MEX](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)e il esempio [Endpoint di metadati protetto personalizzato](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="7fbfb-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fbfb-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fbfb-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [<span data-ttu-id="7fbfb-142">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7fbfb-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="7fbfb-143">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="7fbfb-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="7fbfb-144">Procedura: Configurare un'associazione WS-Metadata Exchange personalizzata</span><span class="sxs-lookup"><span data-stu-id="7fbfb-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [<span data-ttu-id="7fbfb-145">Procedura: Recuperare metadati attraverso un'associazione non MEX</span><span class="sxs-lookup"><span data-stu-id="7fbfb-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [<span data-ttu-id="7fbfb-146">Endpoint di metadati protetto personalizzato</span><span class="sxs-lookup"><span data-stu-id="7fbfb-146">Custom Secure Metadata Endpoint</span></span>](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [<span data-ttu-id="7fbfb-147">Metadati</span><span class="sxs-lookup"><span data-stu-id="7fbfb-147">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="7fbfb-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="7fbfb-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7fbfb-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="7fbfb-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="7fbfb-150">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="7fbfb-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="7fbfb-151">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="7fbfb-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
