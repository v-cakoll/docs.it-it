---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230499"
---
# <a name="xmlelement"></a><span data-ttu-id="c47fa-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="c47fa-101">\<xmlElement></span></span>
<span data-ttu-id="c47fa-102">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="c47fa-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="c47fa-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c47fa-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c47fa-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="c47fa-104">\<bindings></span></span>  
<span data-ttu-id="c47fa-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="c47fa-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="c47fa-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c47fa-106">\<binding></span></span>  
<span data-ttu-id="c47fa-107">\<security></span><span class="sxs-lookup"><span data-stu-id="c47fa-107">\<security></span></span>  
<span data-ttu-id="c47fa-108">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="c47fa-108">\<message></span></span>  
<span data-ttu-id="c47fa-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="c47fa-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c47fa-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c47fa-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c47fa-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c47fa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c47fa-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c47fa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c47fa-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c47fa-113">Attributes</span></span>  
  
|<span data-ttu-id="c47fa-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="c47fa-114">Attribute</span></span>|<span data-ttu-id="c47fa-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c47fa-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c47fa-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="c47fa-116">xmlElement</span></span>|<span data-ttu-id="c47fa-117">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="c47fa-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c47fa-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c47fa-118">Child Elements</span></span>  
 <span data-ttu-id="c47fa-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c47fa-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c47fa-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c47fa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c47fa-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c47fa-121">Element</span></span>|<span data-ttu-id="c47fa-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c47fa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c47fa-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="c47fa-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="c47fa-124">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="c47fa-124">A collection of token request parameters.</span></span> <span data-ttu-id="c47fa-125">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c47fa-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c47fa-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c47fa-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="c47fa-127">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c47fa-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c47fa-128">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="c47fa-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c47fa-129">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c47fa-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c47fa-130">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="c47fa-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c47fa-131">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c47fa-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
