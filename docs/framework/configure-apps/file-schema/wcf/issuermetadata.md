---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397890"
---
# <a name="issuermetadata"></a><span data-ttu-id="2f420-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="2f420-101">\<issuerMetadata></span></span>

<span data-ttu-id="2f420-102">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f420-102">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f420-103">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f420-103">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2f420-104">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2f420-104">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2f420-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f420-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2f420-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="2f420-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2f420-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f420-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2f420-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> messaggi**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f420-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2f420-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerMetadata**</span><span class="sxs-lookup"><span data-stu-id="2f420-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f420-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f420-110">Syntax</span></span>  
  
```xml  
<issuerMetadata address="String">
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
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f420-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2f420-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2f420-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2f420-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f420-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f420-113">Attributes</span></span>  
  
|<span data-ttu-id="2f420-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2f420-114">Attribute</span></span>|<span data-ttu-id="2f420-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2f420-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f420-116">Address</span><span class="sxs-lookup"><span data-stu-id="2f420-116">address</span></span>|<span data-ttu-id="2f420-117">Attributo `string` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f420-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="2f420-118">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2f420-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="2f420-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="2f420-119">The address must be an absolute URI.</span></span> <span data-ttu-id="2f420-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="2f420-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f420-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2f420-121">Child Elements</span></span>  
  
|<span data-ttu-id="2f420-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f420-122">Element</span></span>|<span data-ttu-id="2f420-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f420-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f420-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="2f420-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="2f420-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="2f420-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="2f420-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="2f420-126">\<identity></span></span>](identity.md)|<span data-ttu-id="2f420-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="2f420-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f420-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2f420-128">Parent Elements</span></span>  
  
|<span data-ttu-id="2f420-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f420-129">Element</span></span>|<span data-ttu-id="2f420-130">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2f420-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f420-131">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="2f420-131">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="2f420-132">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [ \<elemento wsFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2f420-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f420-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f420-133">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="2f420-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="2f420-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2f420-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="2f420-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2f420-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="2f420-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2f420-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="2f420-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
