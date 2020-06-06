---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855178"
---
# \<headers>
<span data-ttu-id="7fd3e-101">Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-101">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="7fd3e-102">Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-102">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="7fd3e-103">Questo elemento di configurazione può essere usato per definire tali intestazioni di indirizzo personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-103">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="7fd3e-104">Le voci nella raccolta di intestazioni dell'endpoint sono elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-104">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="7fd3e-105">Ogni elemento deve essere in formato XML corretto.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-105">Each element has to be well-formed XML.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**  
  
## <a name="syntax"></a><span data-ttu-id="7fd3e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fd3e-106">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fd3e-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7fd3e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7fd3e-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fd3e-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="7fd3e-109">Attributes</span></span>  
 <span data-ttu-id="7fd3e-110">No.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7fd3e-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7fd3e-111">Child Elements</span></span>  
 <span data-ttu-id="7fd3e-112">Elementi XML definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-112">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7fd3e-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7fd3e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="7fd3e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fd3e-114">Element</span></span>|<span data-ttu-id="7fd3e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fd3e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="7fd3e-116">Configura differenti tipi di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-116">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fd3e-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="7fd3e-117">Remarks</span></span>  
 <span data-ttu-id="7fd3e-118">Le intestazioni facoltative forniscono informazioni di indirizzamento più dettagliate che consentono di identificare o interagire con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-118">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="7fd3e-119">Ad esempio, le intestazioni possono indicare come elaborare un messaggio in ingresso, dove l'endpoint deve inviare un messaggio di risposta o quale istanza di un servizio usare per elaborare un messaggio in ingresso di un particolare utente, quando sono disponibili più istanze.</span><span class="sxs-lookup"><span data-stu-id="7fd3e-119">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd3e-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7fd3e-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="7fd3e-121">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="7fd3e-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
