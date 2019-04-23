---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 6fb31fca6ac38f6cb92ef087cc277a4d5066521c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182455"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="3fec6-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="3fec6-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="3fec6-102">Questo elemento di configurazione definisce un endpoint standard con fisse [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) automaticamente l'associazione che aggiunge il [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="3fec6-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="3fec6-103">Usare questo endpoint per la scrittura di un servizio REST.</span><span class="sxs-lookup"><span data-stu-id="3fec6-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="3fec6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3fec6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3fec6-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3fec6-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fec6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fec6-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fec6-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3fec6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3fec6-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3fec6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fec6-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="3fec6-109">Attributes</span></span>  
  
|<span data-ttu-id="3fec6-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="3fec6-110">Attribute</span></span>|<span data-ttu-id="3fec6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fec6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fec6-112">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="3fec6-112">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="3fec6-113">Valore booleano che indica se la selezione automatica del formato è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3fec6-113">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="3fec6-114">Quando la selezione automatica del formato è abilitata, l'infrastruttura analizza l'intestazione `Accept` del messaggio di richiesta e determina il formato appropriato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="3fec6-114">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="3fec6-115">Se l'intestazione `Accept` non specifica un formato adatto per la risposta, l'infrastruttura usa il `Content-Type` del messaggio di richiesta o il formato della risposta predefinito dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="3fec6-115">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="3fec6-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="3fec6-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="3fec6-117">Attributo che specifica il formato predefinito per la risposta in uscita.</span><span class="sxs-lookup"><span data-stu-id="3fec6-117">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="3fec6-118">L'attributo è di tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="3fec6-118">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="3fec6-119">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="3fec6-119">helpEnabled</span></span>|<span data-ttu-id="3fec6-120">Valore booleano che indica se la Guida HTTP è abilitata per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="3fec6-120">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="3fec6-121">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="3fec6-121">webEndpointType</span></span>|<span data-ttu-id="3fec6-122">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="3fec6-122">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fec6-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3fec6-123">Child Elements</span></span>  
 <span data-ttu-id="3fec6-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3fec6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fec6-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3fec6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="3fec6-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="3fec6-126">Element</span></span>|<span data-ttu-id="3fec6-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fec6-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fec6-128">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3fec6-128">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3fec6-129">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="3fec6-129">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fec6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fec6-130">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
