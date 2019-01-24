---
title: '&lt;xmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 40703bdf62e8c69ac7e09a0d715e2a2f99408680
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612281"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="878c0-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="878c0-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="878c0-103">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="878c0-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="878c0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="878c0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="878c0-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="878c0-105">\<bindings></span></span>  
<span data-ttu-id="878c0-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="878c0-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="878c0-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="878c0-107">\<binding></span></span>  
<span data-ttu-id="878c0-108">\<security></span><span class="sxs-lookup"><span data-stu-id="878c0-108">\<security></span></span>  
<span data-ttu-id="878c0-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="878c0-109">\<message></span></span>  
<span data-ttu-id="878c0-110">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="878c0-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="878c0-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="878c0-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="878c0-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="878c0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="878c0-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="878c0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="878c0-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="878c0-114">Attributes</span></span>  
  
|<span data-ttu-id="878c0-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="878c0-115">Attribute</span></span>|<span data-ttu-id="878c0-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="878c0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="878c0-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="878c0-117">xmlElement</span></span>|<span data-ttu-id="878c0-118">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="878c0-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="878c0-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="878c0-119">Child Elements</span></span>  
 <span data-ttu-id="878c0-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="878c0-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="878c0-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="878c0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="878c0-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="878c0-122">Element</span></span>|<span data-ttu-id="878c0-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="878c0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="878c0-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="878c0-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="878c0-125">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="878c0-125">A collection of token request parameters.</span></span> <span data-ttu-id="878c0-126">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="878c0-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="878c0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="878c0-127">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="878c0-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="878c0-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="878c0-129">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="878c0-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="878c0-130">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="878c0-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="878c0-131">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="878c0-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="878c0-132">Associazioni</span><span class="sxs-lookup"><span data-stu-id="878c0-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
