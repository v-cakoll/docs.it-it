---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: ca6d401109d14ce11dcd40c393cd079170e4d20d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259869"
---
# <a name="webhttp"></a><span data-ttu-id="56c74-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="56c74-101">\<webHttp></span></span>
<span data-ttu-id="56c74-102">Questo elemento specifica il comportamento <xref:System.ServiceModel.Description.WebHttpBehavior> in un endpoint tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="56c74-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="56c74-103">Questo comportamento, quando viene usato in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, attiva il modello di programmazione Web per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="56c74-103">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="56c74-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="56c74-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="56c74-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="56c74-105">\<behaviors></span></span>  
<span data-ttu-id="56c74-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="56c74-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="56c74-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="56c74-107">\<behavior></span></span>  
<span data-ttu-id="56c74-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="56c74-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56c74-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56c74-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56c74-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="56c74-110">Attributes and Elements</span></span>  
 <span data-ttu-id="56c74-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="56c74-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56c74-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="56c74-112">Attributes</span></span>  
  
|<span data-ttu-id="56c74-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="56c74-113">Attribute</span></span>|<span data-ttu-id="56c74-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56c74-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56c74-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="56c74-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="56c74-116">Quando questa proprietà è impostata su `true`, l'infrastruttura di WCF determina il formato migliore da usare.</span><span class="sxs-lookup"><span data-stu-id="56c74-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="56c74-117">La selezione automatica del formato è disabilitata per impostazione predefinita per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="56c74-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="56c74-118">La selezione automatica del formato automatica può essere abilitata a livello di codice o tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="56c74-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="56c74-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="56c74-119">defaultBodyStyle</span></span>|<span data-ttu-id="56c74-120">Specifica lo stile predefinito del corpo dei messaggi restituiti.</span><span class="sxs-lookup"><span data-stu-id="56c74-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="56c74-121">Per altre informazioni, vedere <xref:System.ServiceModel.Web.WebMessageBodyStyle> e [formattazione HTTP Web WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="56c74-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="56c74-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="56c74-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="56c74-123">Specifica il formato del messaggio di risposta in uscita predefinito per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="56c74-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="56c74-124">Per altre informazioni, vedere [formattazione HTTP Web WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="56c74-124">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="56c74-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="56c74-125">faultExceptionEnabled</span></span>|<span data-ttu-id="56c74-126">Ottiene o imposta il flag che specifica se viene generata un'eccezione FaultException quando si verifica un errore interno del server (Codice di stato HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="56c74-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="56c74-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="56c74-127">helpEnabled</span></span>|<span data-ttu-id="56c74-128">Ottiene o imposta un valore che determina se la pagina della Guida è abilitata.</span><span class="sxs-lookup"><span data-stu-id="56c74-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56c74-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="56c74-129">Child Elements</span></span>  
 <span data-ttu-id="56c74-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="56c74-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56c74-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="56c74-131">Parent Elements</span></span>  
  
|<span data-ttu-id="56c74-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="56c74-132">Element</span></span>|<span data-ttu-id="56c74-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56c74-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56c74-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="56c74-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="56c74-135">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="56c74-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56c74-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56c74-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="56c74-137">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="56c74-137">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="56c74-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="56c74-138">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
