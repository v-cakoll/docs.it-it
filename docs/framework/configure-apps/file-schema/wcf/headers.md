---
title: '&lt;Intestazioni&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 84b9a9437d4b0dfae72a6e625b21f2b830eb28d8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147863"
---
# <a name="ltheadersgt"></a><span data-ttu-id="ad3c7-102">&lt;Intestazioni&gt;</span><span class="sxs-lookup"><span data-stu-id="ad3c7-102">&lt;headers&gt;</span></span>
<span data-ttu-id="ad3c7-103">Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="ad3c7-104">Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="ad3c7-105">Questo elemento di configurazione può essere usato per definire tali intestazioni di indirizzo personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="ad3c7-106">Le voci nella raccolta di intestazioni dell'endpoint sono elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="ad3c7-107">Ogni elemento deve essere in formato XML corretto.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="ad3c7-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ad3c7-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="ad3c7-109">\<client></span><span class="sxs-lookup"><span data-stu-id="ad3c7-109">\<client></span></span>  
<span data-ttu-id="ad3c7-110">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="ad3c7-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad3c7-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad3c7-111">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad3c7-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ad3c7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ad3c7-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad3c7-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="ad3c7-114">Attributes</span></span>  
 <span data-ttu-id="ad3c7-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad3c7-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ad3c7-116">Child Elements</span></span>  
  
|<span data-ttu-id="ad3c7-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad3c7-117">Element</span></span>|<span data-ttu-id="ad3c7-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad3c7-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad3c7-119">Region</span><span class="sxs-lookup"><span data-stu-id="ad3c7-119">Region</span></span>||  
|<span data-ttu-id="ad3c7-120">Member</span><span class="sxs-lookup"><span data-stu-id="ad3c7-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="ad3c7-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ad3c7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ad3c7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ad3c7-122">Element</span></span>|<span data-ttu-id="ad3c7-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad3c7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad3c7-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="ad3c7-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="ad3c7-125">Configura differenti tipi di endpoint.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad3c7-126">Note</span><span class="sxs-lookup"><span data-stu-id="ad3c7-126">Remarks</span></span>  
 <span data-ttu-id="ad3c7-127">Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="ad3c7-128">Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.</span><span class="sxs-lookup"><span data-stu-id="ad3c7-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3c7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad3c7-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="ad3c7-130">Endpoint: Gli indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="ad3c7-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
