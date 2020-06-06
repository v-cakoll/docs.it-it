---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8d0ae2a1848eaf28c2e408542b8209cf968de4c1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430298"
---
# \<mexTcpBinding>
<span data-ttu-id="ff943-101">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite TCP.</span><span class="sxs-lookup"><span data-stu-id="ff943-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="ff943-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff943-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff943-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ff943-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ff943-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ff943-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff943-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="ff943-105">Attributes</span></span>  
  
|<span data-ttu-id="ff943-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="ff943-106">Attribute</span></span>|<span data-ttu-id="ff943-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff943-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ff943-108">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="ff943-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ff943-109">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ff943-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ff943-110">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ff943-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="ff943-111">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="ff943-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="ff943-112">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="ff943-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ff943-113">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="ff943-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ff943-114">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ff943-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ff943-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="ff943-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ff943-116">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ff943-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ff943-117">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ff943-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ff943-118">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="ff943-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ff943-119">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ff943-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ff943-120">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ff943-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ff943-121">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="ff943-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ff943-122">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ff943-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ff943-123">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ff943-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff943-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ff943-124">Child Elements</span></span>  
 <span data-ttu-id="ff943-125">No.</span><span class="sxs-lookup"><span data-stu-id="ff943-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff943-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ff943-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ff943-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff943-127">Element</span></span>|<span data-ttu-id="ff943-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff943-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="ff943-129">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ff943-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff943-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ff943-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="ff943-131">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ff943-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="ff943-132">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="ff943-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="ff943-133">Metadati</span><span class="sxs-lookup"><span data-stu-id="ff943-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="ff943-134">Binding</span><span class="sxs-lookup"><span data-stu-id="ff943-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ff943-135">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="ff943-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ff943-136">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="ff943-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
