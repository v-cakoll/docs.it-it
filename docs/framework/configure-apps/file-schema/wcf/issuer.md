---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160823"
---
# <a name="issuer"></a><span data-ttu-id="74d16-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="74d16-101">\<issuer></span></span>
<span data-ttu-id="74d16-102">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="74d16-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="74d16-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="74d16-103">\<system.serviceModel></span></span>  
<span data-ttu-id="74d16-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="74d16-104">\<bindings></span></span>  
<span data-ttu-id="74d16-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="74d16-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="74d16-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="74d16-106">\<binding></span></span>  
<span data-ttu-id="74d16-107">\<security></span><span class="sxs-lookup"><span data-stu-id="74d16-107">\<security></span></span>  
<span data-ttu-id="74d16-108">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="74d16-108">\<message></span></span>  
<span data-ttu-id="74d16-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="74d16-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d16-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74d16-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74d16-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="74d16-111">Attributes and Elements</span></span>  
 <span data-ttu-id="74d16-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="74d16-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74d16-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="74d16-113">Attributes</span></span>  
  
|<span data-ttu-id="74d16-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="74d16-114">Attribute</span></span>|<span data-ttu-id="74d16-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74d16-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74d16-116">indirizzo</span><span class="sxs-lookup"><span data-stu-id="74d16-116">address</span></span>|<span data-ttu-id="74d16-117">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="74d16-117">Required string.</span></span> <span data-ttu-id="74d16-118">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="74d16-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74d16-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="74d16-119">Child Elements</span></span>  
  
|<span data-ttu-id="74d16-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="74d16-120">Element</span></span>|<span data-ttu-id="74d16-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74d16-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74d16-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="74d16-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="74d16-123">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="74d16-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="74d16-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="74d16-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="74d16-125">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="74d16-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74d16-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="74d16-126">Parent Elements</span></span>  
  
|<span data-ttu-id="74d16-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="74d16-127">Element</span></span>|<span data-ttu-id="74d16-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74d16-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74d16-129">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="74d16-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="74d16-130">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="74d16-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74d16-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d16-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="74d16-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="74d16-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="74d16-133">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="74d16-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="74d16-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="74d16-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="74d16-135">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="74d16-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="74d16-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="74d16-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="74d16-137">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="74d16-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
