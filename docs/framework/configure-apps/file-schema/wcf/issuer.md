---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397908"
---
# <a name="issuer"></a><span data-ttu-id="8bde7-101">\<> autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="8bde7-101">\<issuer></span></span>
<span data-ttu-id="8bde7-102">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8bde7-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="8bde7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8bde7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8bde7-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8bde7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8bde7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8bde7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8bde7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8bde7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8bde7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="8bde7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8bde7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8bde7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8bde7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> messaggi**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8bde7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8bde7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="8bde7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bde7-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8bde7-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bde7-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8bde7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8bde7-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8bde7-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bde7-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="8bde7-114">Attributes</span></span>  
  
|<span data-ttu-id="8bde7-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="8bde7-115">Attribute</span></span>|<span data-ttu-id="8bde7-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8bde7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bde7-117">Address</span><span class="sxs-lookup"><span data-stu-id="8bde7-117">address</span></span>|<span data-ttu-id="8bde7-118">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="8bde7-118">Required string.</span></span> <span data-ttu-id="8bde7-119">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="8bde7-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bde7-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8bde7-120">Child Elements</span></span>  
  
|<span data-ttu-id="8bde7-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bde7-121">Element</span></span>|<span data-ttu-id="8bde7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8bde7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bde7-123">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="8bde7-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="8bde7-124">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="8bde7-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="8bde7-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="8bde7-125">\<identity></span></span>](identity.md)|<span data-ttu-id="8bde7-126">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="8bde7-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bde7-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8bde7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8bde7-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bde7-128">Element</span></span>|<span data-ttu-id="8bde7-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8bde7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bde7-130">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="8bde7-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="8bde7-131">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [ \<elemento wsFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8bde7-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bde7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bde7-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="8bde7-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="8bde7-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8bde7-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="8bde7-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8bde7-135">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="8bde7-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8bde7-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="8bde7-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8bde7-137">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8bde7-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="8bde7-138">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="8bde7-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
