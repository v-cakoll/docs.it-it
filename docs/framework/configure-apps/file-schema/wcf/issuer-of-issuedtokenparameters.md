---
title: <issuer> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397937"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="cfdfe-102">\<> autorità emittente di \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="cfdfe-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="cfdfe-103">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfdfe-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="cfdfe-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfdfe-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cfdfe-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cfdfe-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cfdfe-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="cfdfe-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="cfdfe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="cfdfe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="cfdfe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="cfdfe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cfdfe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="cfdfe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="cfdfe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenParameters**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="cfdfe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="cfdfe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="cfdfe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfdfe-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfdfe-112">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfdfe-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cfdfe-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cfdfe-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cfdfe-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfdfe-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="cfdfe-115">Attributes</span></span>  
  
|<span data-ttu-id="cfdfe-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="cfdfe-116">Attribute</span></span>|<span data-ttu-id="cfdfe-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfdfe-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfdfe-118">Address</span><span class="sxs-lookup"><span data-stu-id="cfdfe-118">address</span></span>|<span data-ttu-id="cfdfe-119">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="cfdfe-119">Required string.</span></span> <span data-ttu-id="cfdfe-120">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="cfdfe-120">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfdfe-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cfdfe-121">Child Elements</span></span>  
  
|<span data-ttu-id="cfdfe-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfdfe-122">Element</span></span>|<span data-ttu-id="cfdfe-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfdfe-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfdfe-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="cfdfe-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="cfdfe-125">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="cfdfe-125">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="cfdfe-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="cfdfe-126">\<identity></span></span>](identity.md)|<span data-ttu-id="cfdfe-127">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="cfdfe-127">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfdfe-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cfdfe-128">Parent Elements</span></span>  
  
|<span data-ttu-id="cfdfe-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfdfe-129">Element</span></span>|<span data-ttu-id="cfdfe-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfdfe-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfdfe-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="cfdfe-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="cfdfe-132">Specifica il token corrente emesso.</span><span class="sxs-lookup"><span data-stu-id="cfdfe-132">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfdfe-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfdfe-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="cfdfe-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="cfdfe-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="cfdfe-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="cfdfe-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="cfdfe-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cfdfe-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="cfdfe-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="cfdfe-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="cfdfe-138">Associazioni</span><span class="sxs-lookup"><span data-stu-id="cfdfe-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cfdfe-139">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="cfdfe-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cfdfe-140">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cfdfe-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="cfdfe-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cfdfe-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="cfdfe-142">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cfdfe-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="cfdfe-143">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="cfdfe-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
