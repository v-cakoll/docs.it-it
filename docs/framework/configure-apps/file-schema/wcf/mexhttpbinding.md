---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8d5b9378bf7769754586d0b13f742659aee18f03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430916"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="d6f2b-101">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d6f2b-101">\<mexHttpBinding></span></span>
<span data-ttu-id="d6f2b-102">Specifica le impostazioni per un'associazione usata per lo scambio di messaggi WS-MetadataExchange (WS-MEX) tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
<span data-ttu-id="d6f2b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6f2b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d6f2b-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d6f2b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d6f2b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<></span><span class="sxs-lookup"><span data-stu-id="d6f2b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d6f2b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpBinding** ></span><span class="sxs-lookup"><span data-stu-id="d6f2b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f2b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6f2b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6f2b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6f2b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d6f2b-109">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6f2b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6f2b-110">Attributes</span></span>  
  
|<span data-ttu-id="d6f2b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d6f2b-111">Attribute</span></span>|<span data-ttu-id="d6f2b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6f2b-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d6f2b-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d6f2b-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d6f2b-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d6f2b-116">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d6f2b-117">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d6f2b-118">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d6f2b-119">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d6f2b-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d6f2b-120">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d6f2b-121">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d6f2b-122">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d6f2b-123">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d6f2b-124">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d6f2b-125">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d6f2b-126">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d6f2b-127">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d6f2b-128">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6f2b-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6f2b-129">Child Elements</span></span>  
 <span data-ttu-id="d6f2b-130">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d6f2b-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6f2b-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6f2b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="d6f2b-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6f2b-132">Element</span></span>|<span data-ttu-id="d6f2b-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6f2b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6f2b-134">associazioni di \<></span><span class="sxs-lookup"><span data-stu-id="d6f2b-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="d6f2b-135">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6f2b-136">Note</span><span class="sxs-lookup"><span data-stu-id="d6f2b-136">Remarks</span></span>  
 <span data-ttu-id="d6f2b-137">Questa associazione è fondamentalmente un'associazione `WSHttpBinding` con sicurezza disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-137">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="d6f2b-138">Supporta la maggior parte delle richieste di metadati.</span><span class="sxs-lookup"><span data-stu-id="d6f2b-138">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f2b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6f2b-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="d6f2b-140">Procedura: Pubblicare metadati per un servizio usando un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d6f2b-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d6f2b-141">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="d6f2b-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="d6f2b-142">Metadati</span><span class="sxs-lookup"><span data-stu-id="d6f2b-142">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="d6f2b-143">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d6f2b-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d6f2b-144">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d6f2b-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d6f2b-145">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d6f2b-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d6f2b-146">Binding \<></span><span class="sxs-lookup"><span data-stu-id="d6f2b-146">\<binding></span></span>](bindings.md)
