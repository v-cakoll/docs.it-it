---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 491597da508487c3988b284c84411123d434fe72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932525"
---
# <a name="mextcpbinding"></a><span data-ttu-id="cb645-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="cb645-101">\<mexTcpBinding></span></span>
<span data-ttu-id="cb645-102">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite TCP.</span><span class="sxs-lookup"><span data-stu-id="cb645-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="cb645-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cb645-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb645-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="cb645-104">\<bindings></span></span>  
<span data-ttu-id="cb645-105">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="cb645-105">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb645-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb645-106">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb645-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cb645-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cb645-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cb645-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb645-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="cb645-109">Attributes</span></span>  
  
|<span data-ttu-id="cb645-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="cb645-110">Attribute</span></span>|<span data-ttu-id="cb645-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb645-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="cb645-112">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="cb645-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="cb645-113">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cb645-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cb645-114">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="cb645-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="cb645-115">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="cb645-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="cb645-116">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="cb645-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="cb645-117">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="cb645-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="cb645-118">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="cb645-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="cb645-119">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="cb645-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="cb645-120">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="cb645-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="cb645-121">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="cb645-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="cb645-122">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cb645-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cb645-123">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="cb645-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="cb645-124">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="cb645-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="cb645-125">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cb645-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cb645-126">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="cb645-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="cb645-127">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="cb645-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="cb645-128">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cb645-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cb645-129">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="cb645-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb645-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cb645-130">Child Elements</span></span>  
 <span data-ttu-id="cb645-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cb645-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb645-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cb645-132">Parent Elements</span></span>  
  
|<span data-ttu-id="cb645-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb645-133">Element</span></span>|<span data-ttu-id="cb645-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb645-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb645-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cb645-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="cb645-136">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cb645-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb645-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb645-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="cb645-138">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="cb645-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="cb645-139">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="cb645-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="cb645-140">Metadati</span><span class="sxs-lookup"><span data-stu-id="cb645-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="cb645-141">Associazioni</span><span class="sxs-lookup"><span data-stu-id="cb645-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cb645-142">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="cb645-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cb645-143">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="cb645-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cb645-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="cb645-144">\<binding></span></span>](../../../misc/binding.md)
