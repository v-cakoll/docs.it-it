---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 6a197f7aa29645a08a581bcee103eb94c0e20179
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147018"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="c133c-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="c133c-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="c133c-103">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="c133c-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="c133c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c133c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c133c-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="c133c-105">\<bindings></span></span>  
<span data-ttu-id="c133c-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="c133c-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="c133c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c133c-107">\<binding></span></span>  
<span data-ttu-id="c133c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c133c-108">\<security></span></span>  
<span data-ttu-id="c133c-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="c133c-109">\<message></span></span>  
<span data-ttu-id="c133c-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="c133c-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c133c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c133c-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c133c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c133c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c133c-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c133c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c133c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="c133c-114">Attributes</span></span>  
  
|<span data-ttu-id="c133c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="c133c-115">Attribute</span></span>|<span data-ttu-id="c133c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c133c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c133c-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="c133c-117">xmlElement</span></span>|<span data-ttu-id="c133c-118">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="c133c-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c133c-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c133c-119">Child Elements</span></span>  
 <span data-ttu-id="c133c-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c133c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c133c-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c133c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c133c-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c133c-122">Element</span></span>|<span data-ttu-id="c133c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c133c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c133c-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="c133c-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="c133c-125">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="c133c-125">A collection of token request parameters.</span></span> <span data-ttu-id="c133c-126">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c133c-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c133c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c133c-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="c133c-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c133c-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c133c-129">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c133c-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c133c-130">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c133c-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="c133c-131">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c133c-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c133c-132">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c133c-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
