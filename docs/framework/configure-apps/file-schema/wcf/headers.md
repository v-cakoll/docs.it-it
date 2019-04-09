---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 660497012dd057e4ecf95524833e2573fe03a8b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224558"
---
# <a name="headers"></a><span data-ttu-id="8885b-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="8885b-101">\<headers></span></span>
<span data-ttu-id="8885b-102">Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base.</span><span class="sxs-lookup"><span data-stu-id="8885b-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="8885b-103">Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari.</span><span class="sxs-lookup"><span data-stu-id="8885b-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="8885b-104">Questo elemento di configurazione può essere usato per definire tali intestazioni di indirizzo personalizzate.</span><span class="sxs-lookup"><span data-stu-id="8885b-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="8885b-105">Le voci nella raccolta di intestazioni dell'endpoint sono elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8885b-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="8885b-106">Ogni elemento deve essere in formato XML corretto.</span><span class="sxs-lookup"><span data-stu-id="8885b-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="8885b-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8885b-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="8885b-108">\<client></span><span class="sxs-lookup"><span data-stu-id="8885b-108">\<client></span></span>  
<span data-ttu-id="8885b-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="8885b-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8885b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8885b-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8885b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8885b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8885b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8885b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8885b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8885b-113">Attributes</span></span>  
 <span data-ttu-id="8885b-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8885b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8885b-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8885b-115">Child Elements</span></span>  
 <span data-ttu-id="8885b-116">Elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8885b-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8885b-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8885b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8885b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8885b-118">Element</span></span>|<span data-ttu-id="8885b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8885b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8885b-120">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="8885b-120">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="8885b-121">Configura differenti tipi di endpoint.</span><span class="sxs-lookup"><span data-stu-id="8885b-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8885b-122">Note</span><span class="sxs-lookup"><span data-stu-id="8885b-122">Remarks</span></span>  
 <span data-ttu-id="8885b-123">Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8885b-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="8885b-124">Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.</span><span class="sxs-lookup"><span data-stu-id="8885b-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8885b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8885b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="8885b-126">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="8885b-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
