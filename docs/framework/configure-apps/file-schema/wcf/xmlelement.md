---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698460"
---
# <a name="xmlelement"></a><span data-ttu-id="3f527-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="3f527-101">\<xmlElement></span></span>
<span data-ttu-id="3f527-102">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="3f527-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="3f527-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3f527-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3f527-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="3f527-104">\<bindings></span></span>  
<span data-ttu-id="3f527-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="3f527-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="3f527-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="3f527-106">\<binding></span></span>  
<span data-ttu-id="3f527-107">\<security></span><span class="sxs-lookup"><span data-stu-id="3f527-107">\<security></span></span>  
<span data-ttu-id="3f527-108">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="3f527-108">\<message></span></span>  
<span data-ttu-id="3f527-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="3f527-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f527-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f527-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f527-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3f527-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3f527-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3f527-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f527-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="3f527-113">Attributes</span></span>  
  
|<span data-ttu-id="3f527-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="3f527-114">Attribute</span></span>|<span data-ttu-id="3f527-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f527-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f527-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="3f527-116">xmlElement</span></span>|<span data-ttu-id="3f527-117">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="3f527-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f527-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3f527-118">Child Elements</span></span>  
 <span data-ttu-id="3f527-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3f527-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f527-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3f527-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3f527-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f527-121">Element</span></span>|<span data-ttu-id="3f527-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f527-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f527-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="3f527-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="3f527-124">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="3f527-124">A collection of token request parameters.</span></span> <span data-ttu-id="3f527-125">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="3f527-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f527-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f527-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="3f527-127">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="3f527-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3f527-128">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="3f527-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3f527-129">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="3f527-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="3f527-130">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="3f527-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3f527-131">Associazioni</span><span class="sxs-lookup"><span data-stu-id="3f527-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
