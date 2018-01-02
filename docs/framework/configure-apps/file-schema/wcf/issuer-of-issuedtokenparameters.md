---
title: '&lt;issuer&gt; di &lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b31214f5552283c40cdc93e6e72a374bbfef9997
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="1861c-102">&lt;issuer&gt; di &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="1861c-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="1861c-103">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1861c-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="1861c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1861c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1861c-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="1861c-105">\<bindings></span></span>  
<span data-ttu-id="1861c-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1861c-106">\<customBinding></span></span>  
<span data-ttu-id="1861c-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="1861c-107">\<binding></span></span>  
<span data-ttu-id="1861c-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="1861c-108">\<security></span></span>  
<span data-ttu-id="1861c-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="1861c-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="1861c-110">\<autorità di certificazione ></span><span class="sxs-lookup"><span data-stu-id="1861c-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1861c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1861c-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1861c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1861c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1861c-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1861c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1861c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="1861c-114">Attributes</span></span>  
  
|<span data-ttu-id="1861c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="1861c-115">Attribute</span></span>|<span data-ttu-id="1861c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1861c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1861c-117">address</span><span class="sxs-lookup"><span data-stu-id="1861c-117">address</span></span>|<span data-ttu-id="1861c-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1861c-118">Required string.</span></span> <span data-ttu-id="1861c-119">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="1861c-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1861c-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1861c-120">Child Elements</span></span>  
  
|<span data-ttu-id="1861c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1861c-121">Element</span></span>|<span data-ttu-id="1861c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1861c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1861c-123">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="1861c-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="1861c-124">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="1861c-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="1861c-125">\<identità ></span><span class="sxs-lookup"><span data-stu-id="1861c-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="1861c-126">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="1861c-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1861c-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1861c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1861c-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1861c-128">Element</span></span>|<span data-ttu-id="1861c-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1861c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1861c-130">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="1861c-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="1861c-131">Specifica il token corrente emesso.</span><span class="sxs-lookup"><span data-stu-id="1861c-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1861c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1861c-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="1861c-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="1861c-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="1861c-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="1861c-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="1861c-135">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1861c-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="1861c-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="1861c-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="1861c-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1861c-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1861c-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1861c-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1861c-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1861c-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1861c-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1861c-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="1861c-141">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1861c-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="1861c-142">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1861c-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
