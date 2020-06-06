---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 41f5b19f5067d9ac7faa2c7329dd07dd9d48e9b3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430869"
---
# \<mexNamedPipeBinding>
<span data-ttu-id="032bb-101">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite named pipe.</span><span class="sxs-lookup"><span data-stu-id="032bb-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="032bb-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="032bb-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="032bb-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="032bb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="032bb-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="032bb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="032bb-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="032bb-105">Attributes</span></span>  
  
|<span data-ttu-id="032bb-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="032bb-106">Attribute</span></span>|<span data-ttu-id="032bb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="032bb-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="032bb-108">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="032bb-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="032bb-109">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="032bb-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="032bb-110">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="032bb-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="032bb-111">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="032bb-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="032bb-112">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="032bb-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="032bb-113">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="032bb-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="032bb-114">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="032bb-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="032bb-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="032bb-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="032bb-116">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="032bb-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="032bb-117">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="032bb-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="032bb-118">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="032bb-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="032bb-119">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="032bb-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="032bb-120">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="032bb-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="032bb-121">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="032bb-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="032bb-122">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="032bb-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="032bb-123">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="032bb-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="032bb-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="032bb-124">Child Elements</span></span>  
 <span data-ttu-id="032bb-125">No.</span><span class="sxs-lookup"><span data-stu-id="032bb-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="032bb-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="032bb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="032bb-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="032bb-127">Element</span></span>|<span data-ttu-id="032bb-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="032bb-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="032bb-129">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="032bb-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="032bb-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="032bb-130">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="032bb-131">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="032bb-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="032bb-132">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="032bb-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="032bb-133">Metadati</span><span class="sxs-lookup"><span data-stu-id="032bb-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="032bb-134">Binding</span><span class="sxs-lookup"><span data-stu-id="032bb-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="032bb-135">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="032bb-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="032bb-136">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="032bb-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
