---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8d5b9378bf7769754586d0b13f742659aee18f03
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430916"
---
# \<mexHttpBinding>
<span data-ttu-id="945e7-101">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="945e7-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="945e7-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="945e7-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="945e7-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="945e7-103">Attributes and Elements</span></span>  
 <span data-ttu-id="945e7-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="945e7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="945e7-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="945e7-105">Attributes</span></span>  
  
|<span data-ttu-id="945e7-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="945e7-106">Attribute</span></span>|<span data-ttu-id="945e7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="945e7-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="945e7-108">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="945e7-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="945e7-109">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="945e7-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="945e7-110">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="945e7-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="945e7-111">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="945e7-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="945e7-112">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="945e7-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="945e7-113">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="945e7-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="945e7-114">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="945e7-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="945e7-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="945e7-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="945e7-116">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="945e7-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="945e7-117">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="945e7-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="945e7-118">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="945e7-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="945e7-119">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="945e7-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="945e7-120">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="945e7-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="945e7-121">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="945e7-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="945e7-122">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="945e7-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="945e7-123">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="945e7-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="945e7-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="945e7-124">Child Elements</span></span>  
 <span data-ttu-id="945e7-125">No.</span><span class="sxs-lookup"><span data-stu-id="945e7-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="945e7-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="945e7-126">Parent Elements</span></span>  
  
|<span data-ttu-id="945e7-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="945e7-127">Element</span></span>|<span data-ttu-id="945e7-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="945e7-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="945e7-129">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="945e7-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="945e7-130">Commenti</span><span class="sxs-lookup"><span data-stu-id="945e7-130">Remarks</span></span>  
 <span data-ttu-id="945e7-131">Questa associazione è fondamentalmente un'associazione `WSHttpBinding` con sicurezza disabilitata.</span><span class="sxs-lookup"><span data-stu-id="945e7-131">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="945e7-132">Supporta la maggior parte delle richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="945e7-132">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945e7-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="945e7-133">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="945e7-134">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="945e7-134">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="945e7-135">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="945e7-135">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="945e7-136">Metadati</span><span class="sxs-lookup"><span data-stu-id="945e7-136">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="945e7-137">Binding</span><span class="sxs-lookup"><span data-stu-id="945e7-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="945e7-138">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="945e7-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="945e7-139">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="945e7-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
