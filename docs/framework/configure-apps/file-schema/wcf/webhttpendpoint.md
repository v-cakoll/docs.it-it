---
title: '&lt;webHttpEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: ee14ce23370675782f4c25385c1786fdce11eba0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151969"
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="1943b-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="1943b-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="1943b-103">Questo elemento di configurazione definisce un endpoint standard con fisse [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) automaticamente l'associazione che aggiunge il [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="1943b-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="1943b-104">Usare questo endpoint per la scrittura di un servizio REST.</span><span class="sxs-lookup"><span data-stu-id="1943b-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="1943b-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1943b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1943b-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="1943b-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1943b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1943b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1943b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1943b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1943b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1943b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1943b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1943b-110">Attributes</span></span>  
  
|<span data-ttu-id="1943b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1943b-111">Attribute</span></span>|<span data-ttu-id="1943b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1943b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1943b-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="1943b-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="1943b-114">Valore booleano che indica se la selezione automatica del formato è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1943b-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="1943b-115">Quando la selezione automatica del formato è abilitata, l'infrastruttura analizza l'intestazione `Accept` del messaggio di richiesta e determina il formato appropriato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="1943b-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="1943b-116">Se l'intestazione `Accept` non specifica un formato adatto per la risposta, l'infrastruttura usa il `Content-Type` del messaggio di richiesta o il formato della risposta predefinito dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="1943b-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="1943b-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="1943b-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="1943b-118">Attributo che specifica il formato predefinito per la risposta in uscita.</span><span class="sxs-lookup"><span data-stu-id="1943b-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="1943b-119">L'attributo è di tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="1943b-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="1943b-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="1943b-120">helpEnabled</span></span>|<span data-ttu-id="1943b-121">Valore booleano che indica se la Guida HTTP è abilitata per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1943b-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="1943b-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="1943b-122">webEndpointType</span></span>|<span data-ttu-id="1943b-123">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1943b-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1943b-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1943b-124">Child Elements</span></span>  
 <span data-ttu-id="1943b-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1943b-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1943b-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1943b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="1943b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="1943b-127">Element</span></span>|<span data-ttu-id="1943b-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1943b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1943b-129">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="1943b-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="1943b-130">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="1943b-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1943b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1943b-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
