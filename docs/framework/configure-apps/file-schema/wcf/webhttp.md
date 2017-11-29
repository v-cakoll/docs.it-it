---
title: '&lt;webHttp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c51c8ac43549994752999db08dbb92d43bc7a86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="8e247-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="8e247-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="8e247-103">Questo elemento specifica il comportamento <xref:System.ServiceModel.Description.WebHttpBehavior> in un endpoint tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8e247-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="8e247-104">Questo comportamento, quando viene usato in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, consente il modello di programmazione Web per un [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] servizio.</span><span class="sxs-lookup"><span data-stu-id="8e247-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>  
  
 <span data-ttu-id="8e247-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8e247-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e247-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="8e247-106">\<behaviors></span></span>  
<span data-ttu-id="8e247-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8e247-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="8e247-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="8e247-108">\<behavior></span></span>  
<span data-ttu-id="8e247-109">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="8e247-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e247-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e247-110">Syntax</span></span>  
  
```xml  
<webHttp />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e247-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8e247-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8e247-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8e247-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e247-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8e247-113">Attributes</span></span>  
  
|<span data-ttu-id="8e247-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="8e247-114">Attribute</span></span>|<span data-ttu-id="8e247-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e247-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e247-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="8e247-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="8e247-117">Quando questa proprietà è impostata su `true`, l'infrastruttura di WCF determina il formato migliore da usare.</span><span class="sxs-lookup"><span data-stu-id="8e247-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="8e247-118">La selezione automatica del formato è disabilitata per impostazione predefinita per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8e247-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="8e247-119">La selezione automatica del formato automatica può essere abilitata a livello di codice o tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8e247-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="8e247-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="8e247-120">defaultBodyStyle</span></span>|<span data-ttu-id="8e247-121">Specifica lo stile predefinito del corpo dei messaggi restituiti.</span><span class="sxs-lookup"><span data-stu-id="8e247-121">Specifies the default body style of returned messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="8e247-122"><xref:System.ServiceModel.Web.WebMessageBodyStyle> e [HTTP Web WCF formattazione](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="8e247-122"> <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="8e247-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="8e247-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="8e247-124">Specifica il formato del messaggio di risposta in uscita predefinito per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8e247-124">Specifies the default outgoing response format for messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="8e247-125">[HTTP Web WCF formattazione](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="8e247-125"> [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="8e247-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="8e247-126">faultExceptionEnabled</span></span>|<span data-ttu-id="8e247-127">Ottiene o imposta il flag che specifica se viene generata un'eccezione FaultException quando si verifica un errore del server interno (codice di stato HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="8e247-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="8e247-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="8e247-128">helpEnabled</span></span>|<span data-ttu-id="8e247-129">Ottiene o imposta un valore che determina se la pagina della Guida è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8e247-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e247-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8e247-130">Child Elements</span></span>  
 <span data-ttu-id="8e247-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8e247-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e247-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8e247-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8e247-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e247-133">Element</span></span>|<span data-ttu-id="8e247-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e247-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e247-135">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="8e247-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8e247-136">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8e247-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e247-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e247-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="8e247-138">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="8e247-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="8e247-139">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8e247-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
