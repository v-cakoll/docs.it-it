---
title: <issuer> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 690ab14ea33ba9bef29788b2eb35f86ed945ce2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113542"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="0e1f7-102">\<autorità di certificazione > di \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="0e1f7-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="0e1f7-103">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0e1f7-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="0e1f7-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0e1f7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0e1f7-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="0e1f7-105">\<bindings></span></span>  
<span data-ttu-id="0e1f7-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0e1f7-106">\<customBinding></span></span>  
<span data-ttu-id="0e1f7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0e1f7-107">\<binding></span></span>  
<span data-ttu-id="0e1f7-108">\<security></span><span class="sxs-lookup"><span data-stu-id="0e1f7-108">\<security></span></span>  
<span data-ttu-id="0e1f7-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="0e1f7-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="0e1f7-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="0e1f7-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e1f7-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e1f7-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e1f7-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e1f7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0e1f7-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e1f7-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e1f7-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e1f7-114">Attributes</span></span>  
  
|<span data-ttu-id="0e1f7-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="0e1f7-115">Attribute</span></span>|<span data-ttu-id="0e1f7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e1f7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e1f7-117">indirizzo</span><span class="sxs-lookup"><span data-stu-id="0e1f7-117">address</span></span>|<span data-ttu-id="0e1f7-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="0e1f7-118">Required string.</span></span> <span data-ttu-id="0e1f7-119">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="0e1f7-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e1f7-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e1f7-120">Child Elements</span></span>  
  
|<span data-ttu-id="0e1f7-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e1f7-121">Element</span></span>|<span data-ttu-id="0e1f7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e1f7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e1f7-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="0e1f7-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="0e1f7-124">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="0e1f7-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="0e1f7-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="0e1f7-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0e1f7-126">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="0e1f7-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e1f7-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e1f7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0e1f7-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e1f7-128">Element</span></span>|<span data-ttu-id="0e1f7-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e1f7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e1f7-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="0e1f7-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="0e1f7-131">Specifica il token corrente emesso.</span><span class="sxs-lookup"><span data-stu-id="0e1f7-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e1f7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e1f7-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0e1f7-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="0e1f7-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0e1f7-134">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="0e1f7-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0e1f7-135">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="0e1f7-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="0e1f7-136">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="0e1f7-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0e1f7-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="0e1f7-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0e1f7-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="0e1f7-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0e1f7-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="0e1f7-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0e1f7-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0e1f7-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="0e1f7-141">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="0e1f7-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="0e1f7-142">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="0e1f7-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
