---
title: '&lt;webHttpEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: b69ace451e90c824cdf8b911d596fdd158eb3f73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491719"
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="d9635-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="d9635-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="d9635-103">Questo elemento di configurazione definisce un endpoint standard con fisse [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) automaticamente l'associazione che aggiunge il [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="d9635-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="d9635-104">Usare questo endpoint per la scrittura di un servizio REST.</span><span class="sxs-lookup"><span data-stu-id="d9635-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="d9635-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d9635-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9635-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d9635-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9635-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9635-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9635-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d9635-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d9635-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d9635-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9635-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d9635-110">Attributes</span></span>  
  
|<span data-ttu-id="d9635-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d9635-111">Attribute</span></span>|<span data-ttu-id="d9635-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9635-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9635-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="d9635-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="d9635-114">Valore booleano che indica se la selezione automatica del formato è abilitata.</span><span class="sxs-lookup"><span data-stu-id="d9635-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="d9635-115">Quando la selezione automatica del formato è abilitata, l'infrastruttura analizza l'intestazione `Accept` del messaggio di richiesta e determina il formato appropriato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="d9635-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="d9635-116">Se l'intestazione `Accept` non specifica un formato adatto per la risposta, l'infrastruttura usa il `Content-Type` del messaggio di richiesta o il formato della risposta predefinito dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d9635-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="d9635-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="d9635-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="d9635-118">Attributo che specifica il formato predefinito per la risposta in uscita.</span><span class="sxs-lookup"><span data-stu-id="d9635-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="d9635-119">L'attributo è di tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="d9635-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="d9635-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="d9635-120">helpEnabled</span></span>|<span data-ttu-id="d9635-121">Valore booleano che indica se la Guida HTTP è abilitata per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d9635-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="d9635-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="d9635-122">webEndpointType</span></span>|<span data-ttu-id="d9635-123">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d9635-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9635-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d9635-124">Child Elements</span></span>  
 <span data-ttu-id="d9635-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d9635-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9635-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d9635-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d9635-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9635-127">Element</span></span>|<span data-ttu-id="d9635-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9635-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9635-129">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d9635-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="d9635-130">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="d9635-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9635-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9635-131">See also</span></span>
- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
