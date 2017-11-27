---
title: '&lt;mexNamedPipeBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e786d2f18fca2b04e0a46536e539895890fc67d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmexnamedpipebindinggt"></a><span data-ttu-id="c7728-102">&lt;mexNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="c7728-102">&lt;mexNamedPipeBinding&gt;</span></span>
<span data-ttu-id="c7728-103">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite named pipe.</span><span class="sxs-lookup"><span data-stu-id="c7728-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="c7728-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c7728-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c7728-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="c7728-105">\<bindings></span></span>  
<span data-ttu-id="c7728-106">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="c7728-106">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7728-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7728-107">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7728-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c7728-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c7728-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c7728-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7728-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="c7728-110">Attributes</span></span>  
  
|<span data-ttu-id="c7728-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="c7728-111">Attribute</span></span>|<span data-ttu-id="c7728-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7728-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c7728-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="c7728-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="c7728-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7728-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7728-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c7728-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="c7728-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="c7728-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="c7728-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="c7728-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="c7728-118">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="c7728-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="c7728-119">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="c7728-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="c7728-120">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="c7728-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c7728-121">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="c7728-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="c7728-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="c7728-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="c7728-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7728-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7728-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c7728-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="c7728-125">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="c7728-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="c7728-126">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7728-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7728-127">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="c7728-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="c7728-128">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="c7728-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="c7728-129">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="c7728-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c7728-130">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="c7728-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7728-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c7728-131">Child Elements</span></span>  
 <span data-ttu-id="c7728-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c7728-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7728-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c7728-133">Parent Elements</span></span>  
  
|<span data-ttu-id="c7728-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7728-134">Element</span></span>|<span data-ttu-id="c7728-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7728-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7728-136">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="c7728-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="c7728-137">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="c7728-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7728-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7728-138">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>  
 [<span data-ttu-id="c7728-139">Procedura: pubblicare metadati per un servizio utilizzando un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c7728-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="c7728-140">La pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="c7728-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="c7728-141">Metadati</span><span class="sxs-lookup"><span data-stu-id="c7728-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="c7728-142">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c7728-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c7728-143">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="c7728-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c7728-144">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c7728-144">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="c7728-145">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="c7728-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
