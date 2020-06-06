---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74430335"
---
# \<mexHttpsBinding>
<span data-ttu-id="3ac30-101">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3ac30-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="3ac30-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ac30-102">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ac30-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3ac30-103">Attributes and Elements</span></span>  
 <span data-ttu-id="3ac30-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3ac30-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ac30-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="3ac30-105">Attributes</span></span>  
  
|<span data-ttu-id="3ac30-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="3ac30-106">Attribute</span></span>|<span data-ttu-id="3ac30-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ac30-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="3ac30-108">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="3ac30-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3ac30-109">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3ac30-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3ac30-110">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3ac30-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="3ac30-111">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="3ac30-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3ac30-112">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="3ac30-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3ac30-113">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="3ac30-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3ac30-114">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ac30-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="3ac30-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="3ac30-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3ac30-116">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3ac30-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3ac30-117">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3ac30-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="3ac30-118">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="3ac30-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3ac30-119">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3ac30-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3ac30-120">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3ac30-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="3ac30-121">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="3ac30-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3ac30-122">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3ac30-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3ac30-123">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3ac30-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ac30-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3ac30-124">Child Elements</span></span>  
 <span data-ttu-id="3ac30-125">No.</span><span class="sxs-lookup"><span data-stu-id="3ac30-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ac30-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3ac30-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3ac30-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ac30-127">Element</span></span>|<span data-ttu-id="3ac30-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ac30-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="3ac30-129">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3ac30-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ac30-130">Commenti</span><span class="sxs-lookup"><span data-stu-id="3ac30-130">Remarks</span></span>  
 <span data-ttu-id="3ac30-131">Questa associazione fondamentalmente un'associazione `WSHttpBinding` che supporta la sicurezza a livello di trasporto mediante certificati.</span><span class="sxs-lookup"><span data-stu-id="3ac30-131">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="3ac30-132">Per altre informazioni sulla configurazione e sull'uso di un endpoint di metadati di questo tipo, vedere [procedura: configurare un'associazione WS-Metadata Exchange personalizzata](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [procedura: recuperare metadati su un'associazione non MEX](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)e l' [endpoint dei metadati protetti personalizzati](../../../wcf/samples/custom-secure-metadata-endpoint.md)di esempio.</span><span class="sxs-lookup"><span data-stu-id="3ac30-132">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac30-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3ac30-133">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="3ac30-134">Procedura: pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3ac30-134">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="3ac30-135">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3ac30-135">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="3ac30-136">Procedura: configurare un'associazione WS-Metadata Exchange personalizzata</span><span class="sxs-lookup"><span data-stu-id="3ac30-136">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="3ac30-137">Procedura: recuperare metadati attraverso un'associazione non MEX</span><span class="sxs-lookup"><span data-stu-id="3ac30-137">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="3ac30-138">Endpoint di metadati protetto personalizzato</span><span class="sxs-lookup"><span data-stu-id="3ac30-138">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="3ac30-139">Metadati</span><span class="sxs-lookup"><span data-stu-id="3ac30-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="3ac30-140">Binding</span><span class="sxs-lookup"><span data-stu-id="3ac30-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3ac30-141">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="3ac30-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3ac30-142">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="3ac30-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
