---
title: '&lt;intestazioni&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d5e0a56055df588e9e42c4e1855c352c3f0d1b2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltheadersgt"></a><span data-ttu-id="42f8e-102">&lt;intestazioni&gt;</span><span class="sxs-lookup"><span data-stu-id="42f8e-102">&lt;headers&gt;</span></span>
<span data-ttu-id="42f8e-103">Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base.</span><span class="sxs-lookup"><span data-stu-id="42f8e-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="42f8e-104">Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari.</span><span class="sxs-lookup"><span data-stu-id="42f8e-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="42f8e-105">Questo elemento di configurazione può essere usato per definire tali intestazioni di indirizzo personalizzate.</span><span class="sxs-lookup"><span data-stu-id="42f8e-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="42f8e-106">Le voci nella raccolta di intestazioni dell'endpoint sono elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="42f8e-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="42f8e-107">Ogni elemento deve essere in formato XML corretto.</span><span class="sxs-lookup"><span data-stu-id="42f8e-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="42f8e-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="42f8e-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="42f8e-109">\<client ></span><span class="sxs-lookup"><span data-stu-id="42f8e-109">\<client></span></span>  
<span data-ttu-id="42f8e-110">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="42f8e-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f8e-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42f8e-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42f8e-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="42f8e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="42f8e-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="42f8e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42f8e-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="42f8e-114">Attributes</span></span>  
 <span data-ttu-id="42f8e-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="42f8e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="42f8e-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="42f8e-116">Child Elements</span></span>  
  
|<span data-ttu-id="42f8e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="42f8e-117">Element</span></span>|<span data-ttu-id="42f8e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42f8e-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42f8e-119">Region</span><span class="sxs-lookup"><span data-stu-id="42f8e-119">Region</span></span>||  
|<span data-ttu-id="42f8e-120">Membro</span><span class="sxs-lookup"><span data-stu-id="42f8e-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="42f8e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="42f8e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="42f8e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="42f8e-122">Element</span></span>|<span data-ttu-id="42f8e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42f8e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42f8e-124">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="42f8e-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="42f8e-125">Configura differenti tipi di endpoint.</span><span class="sxs-lookup"><span data-stu-id="42f8e-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42f8e-126">Note</span><span class="sxs-lookup"><span data-stu-id="42f8e-126">Remarks</span></span>  
 <span data-ttu-id="42f8e-127">Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="42f8e-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="42f8e-128">Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.</span><span class="sxs-lookup"><span data-stu-id="42f8e-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f8e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42f8e-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="42f8e-130">Endpoint: Indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="42f8e-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
