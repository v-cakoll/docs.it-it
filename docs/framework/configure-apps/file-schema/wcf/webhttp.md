---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 00644d248e6fb85d7cf712620e6ac74405e6b0c3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399157"
---
# \<webHttp>
<span data-ttu-id="a6474-101">Questo elemento specifica il comportamento <xref:System.ServiceModel.Description.WebHttpBehavior> in un endpoint tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a6474-101">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="a6474-102">Questo comportamento, se utilizzato in combinazione con l' [\<webHttpBinding>](webhttpbinding.md) associazione standard, Abilita il modello di programmazione Web per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a6474-102">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a><span data-ttu-id="a6474-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6474-103">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6474-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a6474-104">Attributes and Elements</span></span>  
 <span data-ttu-id="a6474-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a6474-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6474-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="a6474-106">Attributes</span></span>  
  
|<span data-ttu-id="a6474-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="a6474-107">Attribute</span></span>|<span data-ttu-id="a6474-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6474-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6474-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="a6474-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="a6474-110">Quando questa proprietà è impostata su `true`, l'infrastruttura di WCF determina il formato migliore da usare.</span><span class="sxs-lookup"><span data-stu-id="a6474-110">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="a6474-111">La selezione automatica del formato è disabilitata per impostazione predefinita per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a6474-111">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="a6474-112">La selezione automatica del formato automatica può essere abilitata a livello di codice o tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a6474-112">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="a6474-113">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="a6474-113">defaultBodyStyle</span></span>|<span data-ttu-id="a6474-114">Specifica lo stile predefinito del corpo dei messaggi restituiti.</span><span class="sxs-lookup"><span data-stu-id="a6474-114">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="a6474-115">Per ulteriori informazioni, vedere <xref:System.ServiceModel.Web.WebMessageBodyStyle> e [formattazione http Web WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="a6474-115">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="a6474-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="a6474-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="a6474-117">Specifica il formato del messaggio di risposta in uscita predefinito per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a6474-117">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="a6474-118">Per ulteriori informazioni, vedere la pagina relativa alla [formattazione http Web WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="a6474-118">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="a6474-119">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="a6474-119">faultExceptionEnabled</span></span>|<span data-ttu-id="a6474-120">Ottiene o imposta il flag che specifica se viene generata un'eccezione FaultException quando si verifica un errore del server interno (codice di stato HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="a6474-120">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="a6474-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="a6474-121">helpEnabled</span></span>|<span data-ttu-id="a6474-122">Ottiene o imposta un valore che determina se la pagina della Guida è abilitata.</span><span class="sxs-lookup"><span data-stu-id="a6474-122">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6474-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a6474-123">Child Elements</span></span>  
 <span data-ttu-id="a6474-124">No.</span><span class="sxs-lookup"><span data-stu-id="a6474-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6474-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a6474-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a6474-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6474-126">Element</span></span>|<span data-ttu-id="a6474-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6474-127">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a6474-128">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a6474-128">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6474-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a6474-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="a6474-130">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="a6474-130">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
