---
title: '&lt;webHttp&gt;'
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 9ba54dc1744751efe4efad04f829cccce1244e0d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145676"
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="8771c-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="8771c-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="8771c-103">Questo elemento specifica il comportamento <xref:System.ServiceModel.Description.WebHttpBehavior> in un endpoint tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8771c-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="8771c-104">Questo comportamento, quando viene usato in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, attiva il modello di programmazione Web per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8771c-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="8771c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8771c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8771c-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="8771c-106">\<behaviors></span></span>  
<span data-ttu-id="8771c-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8771c-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="8771c-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="8771c-108">\<behavior></span></span>  
<span data-ttu-id="8771c-109">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="8771c-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8771c-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8771c-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8771c-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8771c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8771c-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8771c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8771c-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8771c-113">Attributes</span></span>  
  
|<span data-ttu-id="8771c-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="8771c-114">Attribute</span></span>|<span data-ttu-id="8771c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8771c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8771c-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="8771c-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="8771c-117">Quando questa proprietà è impostata su `true`, l'infrastruttura di WCF determina il formato migliore da usare.</span><span class="sxs-lookup"><span data-stu-id="8771c-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="8771c-118">La selezione automatica del formato è disabilitata per impostazione predefinita per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8771c-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="8771c-119">La selezione automatica del formato automatica può essere abilitata a livello di codice o tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8771c-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="8771c-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="8771c-120">defaultBodyStyle</span></span>|<span data-ttu-id="8771c-121">Specifica lo stile predefinito del corpo dei messaggi restituiti.</span><span class="sxs-lookup"><span data-stu-id="8771c-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="8771c-122">Per altre informazioni, vedere <xref:System.ServiceModel.Web.WebMessageBodyStyle> e [formattazione HTTP Web WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="8771c-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="8771c-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="8771c-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="8771c-124">Specifica il formato del messaggio di risposta in uscita predefinito per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8771c-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="8771c-125">Per altre informazioni, vedere [formattazione HTTP Web WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="8771c-125">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="8771c-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="8771c-126">faultExceptionEnabled</span></span>|<span data-ttu-id="8771c-127">Ottiene o imposta il flag che specifica se viene generata un'eccezione FaultException quando si verifica un errore interno del server (Codice di stato HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="8771c-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="8771c-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="8771c-128">helpEnabled</span></span>|<span data-ttu-id="8771c-129">Ottiene o imposta un valore che determina se la pagina della Guida è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8771c-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8771c-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8771c-130">Child Elements</span></span>  
 <span data-ttu-id="8771c-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8771c-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8771c-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8771c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8771c-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="8771c-133">Element</span></span>|<span data-ttu-id="8771c-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8771c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8771c-135">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8771c-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8771c-136">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8771c-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8771c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8771c-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="8771c-138">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="8771c-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="8771c-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8771c-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
