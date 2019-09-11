---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854794"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="8110d-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="8110d-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="8110d-102">Questo elemento di configurazione definisce un endpoint standard con un'associazione di [ \<> WebHttpBinding](webhttpbinding.md) fissa che aggiunge automaticamente il [ \<comportamento di > WebHttp](webhttp.md) .</span><span class="sxs-lookup"><span data-stu-id="8110d-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="8110d-103">Usare questo endpoint per la scrittura di un servizio REST.</span><span class="sxs-lookup"><span data-stu-id="8110d-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="8110d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8110d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8110d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8110d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8110d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="8110d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="8110d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> webHttpEndpoint**</span><span class="sxs-lookup"><span data-stu-id="8110d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8110d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8110d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8110d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8110d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8110d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8110d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8110d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8110d-111">Attributes</span></span>  
  
|<span data-ttu-id="8110d-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8110d-112">Attribute</span></span>|<span data-ttu-id="8110d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8110d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8110d-114">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="8110d-114">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="8110d-115">Valore booleano che indica se la selezione automatica del formato è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8110d-115">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="8110d-116">Quando la selezione automatica del formato è abilitata, l'infrastruttura analizza l'intestazione `Accept` del messaggio di richiesta e determina il formato appropriato per la risposta.</span><span class="sxs-lookup"><span data-stu-id="8110d-116">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="8110d-117">Se l'intestazione `Accept` non specifica un formato adatto per la risposta, l'infrastruttura usa il `Content-Type` del messaggio di richiesta o il formato della risposta predefinito dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="8110d-117">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="8110d-118">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="8110d-118">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="8110d-119">Attributo che specifica il formato predefinito per la risposta in uscita.</span><span class="sxs-lookup"><span data-stu-id="8110d-119">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="8110d-120">L'attributo è di tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="8110d-120">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="8110d-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="8110d-121">helpEnabled</span></span>|<span data-ttu-id="8110d-122">Valore booleano che indica se la Guida HTTP è abilitata per l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8110d-122">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="8110d-123">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8110d-123">webEndpointType</span></span>|<span data-ttu-id="8110d-124">Stringa che specifica il tipo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8110d-124">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8110d-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8110d-125">Child Elements</span></span>  
 <span data-ttu-id="8110d-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8110d-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8110d-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8110d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8110d-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="8110d-128">Element</span></span>|<span data-ttu-id="8110d-129">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8110d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8110d-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8110d-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="8110d-131">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="8110d-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8110d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8110d-132">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
