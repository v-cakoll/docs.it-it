---
title: <issuer> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 77ed9534ce872e805a6a6ea2c21a38710e6bc0fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925257"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="945cf-102">\<> autorità emittente di \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="945cf-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="945cf-103">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="945cf-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="945cf-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="945cf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="945cf-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="945cf-105">\<bindings></span></span>  
<span data-ttu-id="945cf-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="945cf-106">\<customBinding></span></span>  
<span data-ttu-id="945cf-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="945cf-107">\<binding></span></span>  
<span data-ttu-id="945cf-108">\<security></span><span class="sxs-lookup"><span data-stu-id="945cf-108">\<security></span></span>  
<span data-ttu-id="945cf-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="945cf-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="945cf-110">\<> autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="945cf-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="945cf-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="945cf-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="945cf-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="945cf-112">Attributes and Elements</span></span>  
 <span data-ttu-id="945cf-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="945cf-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="945cf-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="945cf-114">Attributes</span></span>  
  
|<span data-ttu-id="945cf-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="945cf-115">Attribute</span></span>|<span data-ttu-id="945cf-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="945cf-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="945cf-117">Address</span><span class="sxs-lookup"><span data-stu-id="945cf-117">address</span></span>|<span data-ttu-id="945cf-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="945cf-118">Required string.</span></span> <span data-ttu-id="945cf-119">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="945cf-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="945cf-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="945cf-120">Child Elements</span></span>  
  
|<span data-ttu-id="945cf-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="945cf-121">Element</span></span>|<span data-ttu-id="945cf-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="945cf-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="945cf-123">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="945cf-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="945cf-124">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="945cf-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="945cf-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="945cf-125">\<identity></span></span>](identity.md)|<span data-ttu-id="945cf-126">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="945cf-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="945cf-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="945cf-127">Parent Elements</span></span>  
  
|<span data-ttu-id="945cf-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="945cf-128">Element</span></span>|<span data-ttu-id="945cf-129">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="945cf-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="945cf-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="945cf-130">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="945cf-131">Specifica il token corrente emesso.</span><span class="sxs-lookup"><span data-stu-id="945cf-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="945cf-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="945cf-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="945cf-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="945cf-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="945cf-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="945cf-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="945cf-135">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="945cf-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="945cf-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="945cf-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="945cf-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="945cf-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="945cf-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="945cf-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="945cf-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="945cf-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="945cf-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="945cf-140">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="945cf-141">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="945cf-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="945cf-142">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="945cf-142">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
