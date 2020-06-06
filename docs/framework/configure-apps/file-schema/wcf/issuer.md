---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397908"
---
# \<issuer>
<span data-ttu-id="f2de3-101">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f2de3-101">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="f2de3-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2de3-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2de3-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f2de3-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f2de3-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f2de3-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2de3-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="f2de3-105">Attributes</span></span>  
  
|<span data-ttu-id="f2de3-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="f2de3-106">Attribute</span></span>|<span data-ttu-id="f2de3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2de3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2de3-108">address</span><span class="sxs-lookup"><span data-stu-id="f2de3-108">address</span></span>|<span data-ttu-id="f2de3-109">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="f2de3-109">Required string.</span></span> <span data-ttu-id="f2de3-110">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="f2de3-110">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2de3-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f2de3-111">Child Elements</span></span>  
  
|<span data-ttu-id="f2de3-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2de3-112">Element</span></span>|<span data-ttu-id="f2de3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2de3-113">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="f2de3-114">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="f2de3-114">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="f2de3-115">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="f2de3-115">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2de3-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f2de3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f2de3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2de3-117">Element</span></span>|<span data-ttu-id="f2de3-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2de3-118">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="f2de3-119">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f2de3-119">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2de3-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f2de3-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="f2de3-121">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="f2de3-121">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f2de3-122">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="f2de3-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f2de3-123">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="f2de3-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f2de3-124">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="f2de3-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f2de3-125">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="f2de3-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f2de3-126">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="f2de3-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
