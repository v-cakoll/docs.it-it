---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430335"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="a9705-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="a9705-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="a9705-102">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9705-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="a9705-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a9705-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a9705-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a9705-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a9705-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a9705-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a9705-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpsBinding>**</span><span class="sxs-lookup"><span data-stu-id="a9705-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9705-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9705-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9705-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a9705-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9705-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a9705-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9705-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="a9705-110">Attributes</span></span>  
  
|<span data-ttu-id="a9705-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="a9705-111">Attribute</span></span>|<span data-ttu-id="a9705-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9705-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a9705-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="a9705-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a9705-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a9705-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a9705-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a9705-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="a9705-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="a9705-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a9705-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="a9705-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a9705-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="a9705-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a9705-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a9705-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a9705-120">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="a9705-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a9705-121">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a9705-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a9705-122">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a9705-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a9705-123">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="a9705-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a9705-124">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a9705-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a9705-125">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a9705-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a9705-126">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="a9705-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a9705-127">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a9705-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a9705-128">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a9705-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9705-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a9705-129">Child Elements</span></span>  
 <span data-ttu-id="a9705-130">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="a9705-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9705-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a9705-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a9705-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9705-132">Element</span></span>|<span data-ttu-id="a9705-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9705-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9705-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a9705-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="a9705-135">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a9705-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9705-136">Note</span><span class="sxs-lookup"><span data-stu-id="a9705-136">Remarks</span></span>  
 <span data-ttu-id="a9705-137">Questa associazione fondamentalmente un'associazione `WSHttpBinding` che supporta la sicurezza a livello di trasporto mediante certificati.</span><span class="sxs-lookup"><span data-stu-id="a9705-137">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="a9705-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="a9705-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9705-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9705-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="a9705-140">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a9705-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="a9705-141">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="a9705-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="a9705-142">Procedura: Configurare un'associazione WS-Metadata Exchange personalizzata</span><span class="sxs-lookup"><span data-stu-id="a9705-142">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="a9705-143">Procedura: Recuperare metadati attraverso un'associazione non MEX</span><span class="sxs-lookup"><span data-stu-id="a9705-143">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="a9705-144">Endpoint di metadati protetto personalizzato</span><span class="sxs-lookup"><span data-stu-id="a9705-144">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="a9705-145">Metadati</span><span class="sxs-lookup"><span data-stu-id="a9705-145">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="a9705-146">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a9705-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a9705-147">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="a9705-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a9705-148">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="a9705-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a9705-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="a9705-149">\<binding></span></span>](bindings.md)
