---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 08fda249b526961ff711f439cf729a18e15b412b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929367"
---
# <a name="issuer"></a><span data-ttu-id="c23c0-101">\<> autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="c23c0-101">\<issuer></span></span>
<span data-ttu-id="c23c0-102">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c23c0-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="c23c0-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c23c0-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c23c0-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="c23c0-104">\<bindings></span></span>  
<span data-ttu-id="c23c0-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="c23c0-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="c23c0-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c23c0-106">\<binding></span></span>  
<span data-ttu-id="c23c0-107">\<security></span><span class="sxs-lookup"><span data-stu-id="c23c0-107">\<security></span></span>  
<span data-ttu-id="c23c0-108">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="c23c0-108">\<message></span></span>  
<span data-ttu-id="c23c0-109">\<> autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="c23c0-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c23c0-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c23c0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c23c0-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c23c0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c23c0-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c23c0-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c23c0-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c23c0-113">Attributes</span></span>  
  
|<span data-ttu-id="c23c0-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="c23c0-114">Attribute</span></span>|<span data-ttu-id="c23c0-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c23c0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c23c0-116">Address</span><span class="sxs-lookup"><span data-stu-id="c23c0-116">address</span></span>|<span data-ttu-id="c23c0-117">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="c23c0-117">Required string.</span></span> <span data-ttu-id="c23c0-118">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="c23c0-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c23c0-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c23c0-119">Child Elements</span></span>  
  
|<span data-ttu-id="c23c0-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c23c0-120">Element</span></span>|<span data-ttu-id="c23c0-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c23c0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c23c0-122">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="c23c0-122">\<headers></span></span>](headers-element.md)|<span data-ttu-id="c23c0-123">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="c23c0-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="c23c0-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="c23c0-124">\<identity></span></span>](identity.md)|<span data-ttu-id="c23c0-125">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="c23c0-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c23c0-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c23c0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c23c0-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c23c0-127">Element</span></span>|<span data-ttu-id="c23c0-128">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c23c0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c23c0-129">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="c23c0-129">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="c23c0-130">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [ \<elemento wsFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c23c0-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c23c0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c23c0-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="c23c0-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c23c0-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c23c0-133">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c23c0-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c23c0-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c23c0-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c23c0-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c23c0-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c23c0-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c23c0-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c23c0-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c23c0-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
