---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 00644d248e6fb85d7cf712620e6ac74405e6b0c3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399157"
---
# <a name="webhttp"></a><span data-ttu-id="d4097-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="d4097-101">\<webHttp></span></span>
<span data-ttu-id="d4097-102">Questo elemento specifica il comportamento <xref:System.ServiceModel.Description.WebHttpBehavior> in un endpoint tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="d4097-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="d4097-103">Questo comportamento, se usato insieme [ \<a WebHttpBinding >](webhttpbinding.md) associazione standard, Abilita il modello di programmazione Web per un servizio di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d4097-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="d4097-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4097-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4097-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d4097-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d4097-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d4097-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d4097-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d4097-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="d4097-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d4097-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="d4097-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> WebHttp**</span><span class="sxs-lookup"><span data-stu-id="d4097-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4097-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4097-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4097-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d4097-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d4097-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d4097-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4097-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="d4097-113">Attributes</span></span>  
  
|<span data-ttu-id="d4097-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="d4097-114">Attribute</span></span>|<span data-ttu-id="d4097-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d4097-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4097-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="d4097-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="d4097-117">Quando questa proprietà è impostata su `true`, l'infrastruttura di WCF determina il formato migliore da usare.</span><span class="sxs-lookup"><span data-stu-id="d4097-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="d4097-118">La selezione automatica del formato è disabilitata per impostazione predefinita per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d4097-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="d4097-119">La selezione automatica del formato automatica può essere abilitata a livello di codice o tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="d4097-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="d4097-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="d4097-120">defaultBodyStyle</span></span>|<span data-ttu-id="d4097-121">Specifica lo stile predefinito del corpo dei messaggi restituiti.</span><span class="sxs-lookup"><span data-stu-id="d4097-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="d4097-122">Per ulteriori informazioni, vedere <xref:System.ServiceModel.Web.WebMessageBodyStyle> e [formattazione http Web WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="d4097-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="d4097-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="d4097-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="d4097-124">Specifica il formato del messaggio di risposta in uscita predefinito per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="d4097-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="d4097-125">Per ulteriori informazioni, vedere la pagina relativa alla [formattazione http Web WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="d4097-125">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="d4097-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="d4097-126">faultExceptionEnabled</span></span>|<span data-ttu-id="d4097-127">Ottiene o imposta il flag che specifica se viene generata un'eccezione FaultException quando si verifica un errore interno del server (Codice di stato HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="d4097-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="d4097-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="d4097-128">helpEnabled</span></span>|<span data-ttu-id="d4097-129">Ottiene o imposta un valore che determina se la pagina della Guida è abilitata.</span><span class="sxs-lookup"><span data-stu-id="d4097-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4097-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d4097-130">Child Elements</span></span>  
 <span data-ttu-id="d4097-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d4097-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4097-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d4097-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d4097-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4097-133">Element</span></span>|<span data-ttu-id="d4097-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4097-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4097-135">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d4097-135">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d4097-136">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d4097-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4097-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4097-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="d4097-138">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="d4097-138">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="d4097-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d4097-139">\<webHttpBinding></span></span>](webhttpbinding.md)
