---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 91c1d17ef450200c95d7f871e8cbee85ddd260d1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738912"
---
# <a name="mextcpbinding"></a><span data-ttu-id="86acd-101">\<mexTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="86acd-101">\<mexTcpBinding></span></span>
<span data-ttu-id="86acd-102">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite TCP.</span><span class="sxs-lookup"><span data-stu-id="86acd-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="86acd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86acd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86acd-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="86acd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="86acd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="86acd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="86acd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexTcpBinding** ></span><span class="sxs-lookup"><span data-stu-id="86acd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86acd-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86acd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86acd-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="86acd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="86acd-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="86acd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86acd-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="86acd-110">Attributes</span></span>  
  
|<span data-ttu-id="86acd-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="86acd-111">Attribute</span></span>|<span data-ttu-id="86acd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86acd-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="86acd-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="86acd-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="86acd-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="86acd-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="86acd-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="86acd-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="86acd-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="86acd-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="86acd-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="86acd-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="86acd-118">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="86acd-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="86acd-119">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="86acd-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="86acd-120">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="86acd-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="86acd-121">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="86acd-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="86acd-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="86acd-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="86acd-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="86acd-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="86acd-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="86acd-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="86acd-125">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="86acd-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="86acd-126">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="86acd-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="86acd-127">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="86acd-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="86acd-128">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="86acd-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="86acd-129">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="86acd-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="86acd-130">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="86acd-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86acd-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="86acd-131">Child Elements</span></span>  
 <span data-ttu-id="86acd-132">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="86acd-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86acd-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="86acd-133">Parent Elements</span></span>  
  
|<span data-ttu-id="86acd-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="86acd-134">Element</span></span>|<span data-ttu-id="86acd-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86acd-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86acd-136">\<bindings ></span><span class="sxs-lookup"><span data-stu-id="86acd-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="86acd-137">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="86acd-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86acd-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86acd-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="86acd-139">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="86acd-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="86acd-140">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="86acd-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="86acd-141">Metadati</span><span class="sxs-lookup"><span data-stu-id="86acd-141">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="86acd-142">Associazioni</span><span class="sxs-lookup"><span data-stu-id="86acd-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="86acd-143">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="86acd-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="86acd-144">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="86acd-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="86acd-145">\<binding ></span><span class="sxs-lookup"><span data-stu-id="86acd-145">\<binding></span></span>](bindings.md)
