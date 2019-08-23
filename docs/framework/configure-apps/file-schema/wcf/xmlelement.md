---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: cc178dcc3684ab338282acc369e0ab5c789c15e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941429"
---
# <a name="xmlelement"></a><span data-ttu-id="00b48-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="00b48-101">\<xmlElement></span></span>
<span data-ttu-id="00b48-102">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="00b48-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="00b48-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="00b48-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="00b48-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="00b48-104">\<bindings></span></span>  
<span data-ttu-id="00b48-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="00b48-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="00b48-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="00b48-106">\<binding></span></span>  
<span data-ttu-id="00b48-107">\<security></span><span class="sxs-lookup"><span data-stu-id="00b48-107">\<security></span></span>  
<span data-ttu-id="00b48-108">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="00b48-108">\<message></span></span>  
<span data-ttu-id="00b48-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="00b48-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00b48-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00b48-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00b48-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="00b48-111">Attributes and Elements</span></span>  
 <span data-ttu-id="00b48-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="00b48-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00b48-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="00b48-113">Attributes</span></span>  
  
|<span data-ttu-id="00b48-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="00b48-114">Attribute</span></span>|<span data-ttu-id="00b48-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00b48-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00b48-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="00b48-116">xmlElement</span></span>|<span data-ttu-id="00b48-117">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="00b48-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00b48-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="00b48-118">Child Elements</span></span>  
 <span data-ttu-id="00b48-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="00b48-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00b48-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="00b48-120">Parent Elements</span></span>  
  
|<span data-ttu-id="00b48-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="00b48-121">Element</span></span>|<span data-ttu-id="00b48-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00b48-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00b48-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="00b48-123">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="00b48-124">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="00b48-124">A collection of token request parameters.</span></span> <span data-ttu-id="00b48-125">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="00b48-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00b48-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00b48-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="00b48-127">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="00b48-127">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="00b48-128">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="00b48-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="00b48-129">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="00b48-129">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="00b48-130">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="00b48-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="00b48-131">Associazioni</span><span class="sxs-lookup"><span data-stu-id="00b48-131">Bindings</span></span>](../../../wcf/bindings.md)
