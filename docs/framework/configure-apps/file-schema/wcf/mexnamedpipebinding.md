---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 41f5b19f5067d9ac7faa2c7329dd07dd9d48e9b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430869"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="44cbb-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="44cbb-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="44cbb-102">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite named pipe.</span><span class="sxs-lookup"><span data-stu-id="44cbb-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
<span data-ttu-id="44cbb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44cbb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44cbb-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="44cbb-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44cbb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="44cbb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="44cbb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexNamedPipeBinding>**</span><span class="sxs-lookup"><span data-stu-id="44cbb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44cbb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44cbb-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44cbb-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44cbb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44cbb-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44cbb-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="44cbb-110">Attributes</span></span>  
  
|<span data-ttu-id="44cbb-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="44cbb-111">Attribute</span></span>|<span data-ttu-id="44cbb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44cbb-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="44cbb-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="44cbb-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="44cbb-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44cbb-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44cbb-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="44cbb-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="44cbb-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="44cbb-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="44cbb-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="44cbb-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="44cbb-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="44cbb-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="44cbb-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="44cbb-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="44cbb-120">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="44cbb-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="44cbb-121">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44cbb-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44cbb-122">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="44cbb-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="44cbb-123">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="44cbb-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="44cbb-124">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44cbb-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44cbb-125">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="44cbb-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="44cbb-126">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="44cbb-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="44cbb-127">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44cbb-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44cbb-128">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="44cbb-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44cbb-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44cbb-129">Child Elements</span></span>  
 <span data-ttu-id="44cbb-130">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="44cbb-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44cbb-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44cbb-131">Parent Elements</span></span>  
  
|<span data-ttu-id="44cbb-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="44cbb-132">Element</span></span>|<span data-ttu-id="44cbb-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44cbb-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44cbb-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="44cbb-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="44cbb-135">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="44cbb-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44cbb-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44cbb-136">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="44cbb-137">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="44cbb-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="44cbb-138">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="44cbb-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="44cbb-139">Metadati</span><span class="sxs-lookup"><span data-stu-id="44cbb-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="44cbb-140">Associazioni</span><span class="sxs-lookup"><span data-stu-id="44cbb-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="44cbb-141">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="44cbb-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="44cbb-142">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="44cbb-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="44cbb-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="44cbb-143">\<binding></span></span>](bindings.md)
