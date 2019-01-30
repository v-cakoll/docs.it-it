---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 54f52b1496ada2573949f98e1397b3b7736078d3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254509"
---
# <a name="issuer"></a><span data-ttu-id="185aa-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="185aa-101">\<issuer></span></span>
<span data-ttu-id="185aa-102">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="185aa-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="185aa-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="185aa-103">\<system.serviceModel></span></span>  
<span data-ttu-id="185aa-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="185aa-104">\<bindings></span></span>  
<span data-ttu-id="185aa-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="185aa-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="185aa-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="185aa-106">\<binding></span></span>  
<span data-ttu-id="185aa-107">\<security></span><span class="sxs-lookup"><span data-stu-id="185aa-107">\<security></span></span>  
<span data-ttu-id="185aa-108">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="185aa-108">\<message></span></span>  
<span data-ttu-id="185aa-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="185aa-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="185aa-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="185aa-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="185aa-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="185aa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="185aa-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="185aa-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="185aa-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="185aa-113">Attributes</span></span>  
  
|<span data-ttu-id="185aa-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="185aa-114">Attribute</span></span>|<span data-ttu-id="185aa-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="185aa-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="185aa-116">address</span><span class="sxs-lookup"><span data-stu-id="185aa-116">address</span></span>|<span data-ttu-id="185aa-117">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="185aa-117">Required string.</span></span> <span data-ttu-id="185aa-118">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="185aa-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="185aa-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="185aa-119">Child Elements</span></span>  
  
|<span data-ttu-id="185aa-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="185aa-120">Element</span></span>|<span data-ttu-id="185aa-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="185aa-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="185aa-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="185aa-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="185aa-123">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="185aa-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="185aa-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="185aa-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="185aa-125">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="185aa-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="185aa-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="185aa-126">Parent Elements</span></span>  
  
|<span data-ttu-id="185aa-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="185aa-127">Element</span></span>|<span data-ttu-id="185aa-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="185aa-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="185aa-129">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="185aa-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="185aa-130">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="185aa-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="185aa-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="185aa-131">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="185aa-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="185aa-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="185aa-133">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="185aa-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="185aa-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="185aa-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="185aa-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="185aa-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="185aa-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="185aa-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="185aa-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="185aa-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
