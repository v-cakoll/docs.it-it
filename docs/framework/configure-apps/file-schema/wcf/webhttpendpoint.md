---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854794"
---
# \<webHttpEndpoint>
<span data-ttu-id="1ec99-101">Questo elemento di configurazione definisce un endpoint standard con un' [\<webHttpBinding>](webhttpbinding.md) associazione fissa che aggiunge automaticamente il [\<webHttp>](webhttp.md) comportamento.</span><span class="sxs-lookup"><span data-stu-id="1ec99-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="1ec99-102">Usare questo endpoint per la scrittura di un servizio REST.</span><span class="sxs-lookup"><span data-stu-id="1ec99-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="1ec99-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ec99-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ec99-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1ec99-104">Attributes and Elements</span></span>  
 <span data-ttu-id="1ec99-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1ec99-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ec99-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ec99-106">Attributes</span></span>  
  
|<span data-ttu-id="1ec99-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="1ec99-107">Attribute</span></span>|<span data-ttu-id="1ec99-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ec99-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ec99-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="1ec99-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="1ec99-110">Valore booleano che indica se la selezione automatica del formato è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1ec99-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="1ec99-111">Quando la selezione automatica del formato è abilitata, l'infrastruttura analizza l'intestazione `Accept` del messaggio di richiesta e determina il formato appropriato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="1ec99-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="1ec99-112">Se l'intestazione `Accept` non specifica un formato adatto per la risposta, l'infrastruttura usa il `Content-Type` del messaggio di richiesta o il formato della risposta predefinito dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="1ec99-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="1ec99-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="1ec99-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="1ec99-114">Attributo che specifica il formato predefinito per la risposta in uscita.</span><span class="sxs-lookup"><span data-stu-id="1ec99-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="1ec99-115">L'attributo è di tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="1ec99-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="1ec99-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="1ec99-116">helpEnabled</span></span>|<span data-ttu-id="1ec99-117">Valore booleano che indica se la Guida HTTP è abilitata per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ec99-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="1ec99-118">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="1ec99-118">webEndpointType</span></span>|<span data-ttu-id="1ec99-119">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ec99-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ec99-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ec99-120">Child Elements</span></span>  
 <span data-ttu-id="1ec99-121">No.</span><span class="sxs-lookup"><span data-stu-id="1ec99-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ec99-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1ec99-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1ec99-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ec99-123">Element</span></span>|<span data-ttu-id="1ec99-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ec99-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="1ec99-125">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="1ec99-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ec99-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ec99-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
