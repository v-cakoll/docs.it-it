---
title: '&lt;issuer&gt;'
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 8313d7e361356e5159d1f2d531a6dd34ae7ff4d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612177"
---
# <a name="ltissuergt"></a><span data-ttu-id="4d39f-102">&lt;issuer&gt;</span><span class="sxs-lookup"><span data-stu-id="4d39f-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="4d39f-103">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d39f-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="4d39f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4d39f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4d39f-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="4d39f-105">\<bindings></span></span>  
<span data-ttu-id="4d39f-106">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4d39f-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="4d39f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4d39f-107">\<binding></span></span>  
<span data-ttu-id="4d39f-108">\<security></span><span class="sxs-lookup"><span data-stu-id="4d39f-108">\<security></span></span>  
<span data-ttu-id="4d39f-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="4d39f-109">\<message></span></span>  
<span data-ttu-id="4d39f-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="4d39f-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d39f-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d39f-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d39f-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d39f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4d39f-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d39f-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d39f-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d39f-114">Attributes</span></span>  
  
|<span data-ttu-id="4d39f-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d39f-115">Attribute</span></span>|<span data-ttu-id="4d39f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d39f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d39f-117">address</span><span class="sxs-lookup"><span data-stu-id="4d39f-117">address</span></span>|<span data-ttu-id="4d39f-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4d39f-118">Required string.</span></span> <span data-ttu-id="4d39f-119">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="4d39f-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d39f-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d39f-120">Child Elements</span></span>  
  
|<span data-ttu-id="4d39f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d39f-121">Element</span></span>|<span data-ttu-id="4d39f-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d39f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d39f-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="4d39f-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="4d39f-124">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="4d39f-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="4d39f-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="4d39f-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="4d39f-126">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="4d39f-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d39f-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d39f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4d39f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d39f-128">Element</span></span>|<span data-ttu-id="4d39f-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d39f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d39f-130">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="4d39f-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="4d39f-131">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="4d39f-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d39f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d39f-132">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="4d39f-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="4d39f-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4d39f-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="4d39f-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="4d39f-135">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="4d39f-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4d39f-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="4d39f-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="4d39f-137">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4d39f-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="4d39f-138">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="4d39f-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
