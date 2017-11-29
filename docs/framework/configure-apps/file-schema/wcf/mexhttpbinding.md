---
title: '&lt;mexHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4e8e9a13553e8b7463f7bb7f66c1a38dc1d4ac36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="3907b-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="3907b-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="3907b-103">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="3907b-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="3907b-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3907b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3907b-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="3907b-105">\<bindings></span></span>  
<span data-ttu-id="3907b-106">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3907b-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3907b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3907b-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3907b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3907b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3907b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3907b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3907b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3907b-110">Attributes</span></span>  
  
|<span data-ttu-id="3907b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3907b-111">Attribute</span></span>|<span data-ttu-id="3907b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3907b-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="3907b-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="3907b-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3907b-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3907b-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3907b-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3907b-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="3907b-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="3907b-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3907b-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="3907b-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3907b-118">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="3907b-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="3907b-119">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="3907b-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="3907b-120">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="3907b-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3907b-121">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3907b-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="3907b-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="3907b-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3907b-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3907b-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3907b-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3907b-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="3907b-125">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="3907b-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3907b-126">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3907b-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3907b-127">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3907b-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="3907b-128">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="3907b-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3907b-129">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3907b-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3907b-130">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3907b-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3907b-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3907b-131">Child Elements</span></span>  
 <span data-ttu-id="3907b-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3907b-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3907b-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3907b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="3907b-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="3907b-134">Element</span></span>|<span data-ttu-id="3907b-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3907b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3907b-136">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="3907b-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="3907b-137">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3907b-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3907b-138">Note</span><span class="sxs-lookup"><span data-stu-id="3907b-138">Remarks</span></span>  
 <span data-ttu-id="3907b-139">Questa associazione è fondamentalmente un'associazione `WSHttpBinding` con sicurezza disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3907b-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="3907b-140">Supporta la maggior parte delle richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="3907b-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3907b-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3907b-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpBindingElement>  
 [<span data-ttu-id="3907b-142">Procedura: pubblicare metadati per un servizio utilizzando un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3907b-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="3907b-143">La pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3907b-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="3907b-144">Metadati</span><span class="sxs-lookup"><span data-stu-id="3907b-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="3907b-145">Associazioni</span><span class="sxs-lookup"><span data-stu-id="3907b-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3907b-146">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="3907b-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3907b-147">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="3907b-147">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="3907b-148">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="3907b-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
