---
title: '&lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 22e30e0962ec8d2eb0f7e52f4db143fba9bbf703
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491558"
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="943b2-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="943b2-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="943b2-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="943b2-103">\<system.serviceModel></span></span>  
<span data-ttu-id="943b2-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="943b2-104">\<bindings></span></span>  
<span data-ttu-id="943b2-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="943b2-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="943b2-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="943b2-106">\<binding></span></span>  
<span data-ttu-id="943b2-107">\<security></span><span class="sxs-lookup"><span data-stu-id="943b2-107">\<security></span></span>  
<span data-ttu-id="943b2-108">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="943b2-108">\<message></span></span>  
<span data-ttu-id="943b2-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="943b2-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943b2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="943b2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="943b2-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="943b2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="943b2-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="943b2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="943b2-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="943b2-113">Attributes</span></span>  
  
|<span data-ttu-id="943b2-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="943b2-114">Attribute</span></span>|<span data-ttu-id="943b2-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="943b2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="943b2-116">address</span><span class="sxs-lookup"><span data-stu-id="943b2-116">address</span></span>|<span data-ttu-id="943b2-117">Attributo `string` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="943b2-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="943b2-118">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="943b2-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="943b2-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="943b2-119">The address must be an absolute URI.</span></span> <span data-ttu-id="943b2-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="943b2-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="943b2-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="943b2-121">Child Elements</span></span>  
  
|<span data-ttu-id="943b2-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="943b2-122">Element</span></span>|<span data-ttu-id="943b2-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="943b2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="943b2-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="943b2-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="943b2-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="943b2-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="943b2-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="943b2-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="943b2-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="943b2-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="943b2-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="943b2-128">Parent Elements</span></span>  
  
|<span data-ttu-id="943b2-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="943b2-129">Element</span></span>|<span data-ttu-id="943b2-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="943b2-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="943b2-131">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="943b2-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="943b2-132">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="943b2-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="943b2-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="943b2-133">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="943b2-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="943b2-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="943b2-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="943b2-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="943b2-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="943b2-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="943b2-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="943b2-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
