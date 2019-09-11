---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855178"
---
# <a name="headers"></a><span data-ttu-id="ce94e-101">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="ce94e-101">\<headers></span></span>
<span data-ttu-id="ce94e-102">Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base.</span><span class="sxs-lookup"><span data-stu-id="ce94e-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="ce94e-103">Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari.</span><span class="sxs-lookup"><span data-stu-id="ce94e-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="ce94e-104">Questo elemento di configurazione può essere usato per definire tali intestazioni di indirizzo personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ce94e-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="ce94e-105">Le voci nella raccolta di intestazioni dell'endpoint sono elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ce94e-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="ce94e-106">Ogni elemento deve essere in formato XML corretto.</span><span class="sxs-lookup"><span data-stu-id="ce94e-106">Each element has to be well-formed XML.</span></span>  
  
<span data-ttu-id="ce94e-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce94e-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce94e-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ce94e-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ce94e-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> client**](client.md)</span><span class="sxs-lookup"><span data-stu-id="ce94e-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ce94e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpoint**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="ce94e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="ce94e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<intestazioni >**</span><span class="sxs-lookup"><span data-stu-id="ce94e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce94e-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce94e-112">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce94e-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ce94e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ce94e-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ce94e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce94e-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="ce94e-115">Attributes</span></span>  
 <span data-ttu-id="ce94e-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ce94e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce94e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ce94e-117">Child Elements</span></span>  
 <span data-ttu-id="ce94e-118">Elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ce94e-118">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce94e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ce94e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ce94e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce94e-120">Element</span></span>|<span data-ttu-id="ce94e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce94e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce94e-122">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="ce94e-122">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="ce94e-123">Configura differenti tipi di endpoint.</span><span class="sxs-lookup"><span data-stu-id="ce94e-123">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce94e-124">Note</span><span class="sxs-lookup"><span data-stu-id="ce94e-124">Remarks</span></span>  
 <span data-ttu-id="ce94e-125">Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ce94e-125">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="ce94e-126">Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.</span><span class="sxs-lookup"><span data-stu-id="ce94e-126">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce94e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce94e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="ce94e-128">Endpoint Indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="ce94e-128">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
