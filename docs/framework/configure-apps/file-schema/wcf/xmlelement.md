---
title: '&lt;xmlElement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 702b5ea1331aa0ac284d62809367a90e200a8ba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="a073c-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="a073c-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="a073c-103">Specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="a073c-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="a073c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a073c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a073c-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="a073c-105">\<bindings></span></span>  
<span data-ttu-id="a073c-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="a073c-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="a073c-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="a073c-107">\<binding></span></span>  
<span data-ttu-id="a073c-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="a073c-108">\<security></span></span>  
<span data-ttu-id="a073c-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="a073c-109">\<message></span></span>  
<span data-ttu-id="a073c-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="a073c-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a073c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a073c-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a073c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a073c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a073c-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a073c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a073c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="a073c-114">Attributes</span></span>  
  
|<span data-ttu-id="a073c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="a073c-115">Attribute</span></span>|<span data-ttu-id="a073c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a073c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a073c-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="a073c-117">xmlElement</span></span>|<span data-ttu-id="a073c-118">Stringa che specifica un elemento XML inviato nel corpo del messaggio al servizio token di sicurezza per la richiesta di un token.</span><span class="sxs-lookup"><span data-stu-id="a073c-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a073c-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a073c-119">Child Elements</span></span>  
 <span data-ttu-id="a073c-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a073c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a073c-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a073c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a073c-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a073c-122">Element</span></span>|<span data-ttu-id="a073c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a073c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a073c-124">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="a073c-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="a073c-125">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="a073c-125">A collection of token request parameters.</span></span> <span data-ttu-id="a073c-126">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a073c-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a073c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a073c-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="a073c-128">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="a073c-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a073c-129">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="a073c-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a073c-130">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a073c-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="a073c-131">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="a073c-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a073c-132">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a073c-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
