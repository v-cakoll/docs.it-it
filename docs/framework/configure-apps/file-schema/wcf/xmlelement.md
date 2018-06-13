---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 70ff9b93bcd59331c5fa5e66bb51dc4cd1e043ff
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767648"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="eb173-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="eb173-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="eb173-103">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="eb173-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="eb173-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb173-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb173-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="eb173-105">\<bindings></span></span>  
<span data-ttu-id="eb173-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="eb173-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="eb173-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="eb173-107">\<binding></span></span>  
<span data-ttu-id="eb173-108">\<security></span><span class="sxs-lookup"><span data-stu-id="eb173-108">\<security></span></span>  
<span data-ttu-id="eb173-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="eb173-109">\<message></span></span>  
<span data-ttu-id="eb173-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="eb173-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb173-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb173-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb173-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eb173-112">Attributes and Elements</span></span>  
 <span data-ttu-id="eb173-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eb173-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb173-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="eb173-114">Attributes</span></span>  
  
|<span data-ttu-id="eb173-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="eb173-115">Attribute</span></span>|<span data-ttu-id="eb173-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb173-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb173-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="eb173-117">xmlElement</span></span>|<span data-ttu-id="eb173-118">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="eb173-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb173-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eb173-119">Child Elements</span></span>  
 <span data-ttu-id="eb173-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eb173-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb173-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eb173-121">Parent Elements</span></span>  
  
|<span data-ttu-id="eb173-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb173-122">Element</span></span>|<span data-ttu-id="eb173-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb173-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb173-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="eb173-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="eb173-125">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="eb173-125">A collection of token request parameters.</span></span> <span data-ttu-id="eb173-126">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="eb173-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb173-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb173-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="eb173-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="eb173-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="eb173-129">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="eb173-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="eb173-130">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="eb173-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="eb173-131">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="eb173-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="eb173-132">Associazioni</span><span class="sxs-lookup"><span data-stu-id="eb173-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
