---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 0dffad6a17720dd0506acbcd60efe4aafe24ed28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761676"
---
# <a name="issuermetadata"></a><span data-ttu-id="d2a18-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="d2a18-101">\<issuerMetadata></span></span>
<span data-ttu-id="d2a18-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d2a18-102">\<system.serviceModel></span></span>  
<span data-ttu-id="d2a18-103">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="d2a18-103">\<bindings></span></span>  
<span data-ttu-id="d2a18-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d2a18-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="d2a18-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="d2a18-105">\<binding></span></span>  
<span data-ttu-id="d2a18-106">\<security></span><span class="sxs-lookup"><span data-stu-id="d2a18-106">\<security></span></span>  
<span data-ttu-id="d2a18-107">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="d2a18-107">\<message></span></span>  
<span data-ttu-id="d2a18-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="d2a18-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2a18-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2a18-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2a18-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d2a18-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2a18-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d2a18-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2a18-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d2a18-112">Attributes</span></span>  
  
|<span data-ttu-id="d2a18-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d2a18-113">Attribute</span></span>|<span data-ttu-id="d2a18-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2a18-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2a18-115">indirizzo</span><span class="sxs-lookup"><span data-stu-id="d2a18-115">address</span></span>|<span data-ttu-id="d2a18-116">Attributo `string` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d2a18-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="d2a18-117">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d2a18-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="d2a18-118">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="d2a18-118">The address must be an absolute URI.</span></span> <span data-ttu-id="d2a18-119">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="d2a18-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2a18-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d2a18-120">Child Elements</span></span>  
  
|<span data-ttu-id="d2a18-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2a18-121">Element</span></span>|<span data-ttu-id="d2a18-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2a18-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2a18-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="d2a18-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="d2a18-124">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d2a18-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="d2a18-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="d2a18-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="d2a18-126">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="d2a18-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2a18-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d2a18-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d2a18-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2a18-128">Element</span></span>|<span data-ttu-id="d2a18-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2a18-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2a18-130">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="d2a18-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="d2a18-131">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d2a18-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2a18-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2a18-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="d2a18-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="d2a18-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d2a18-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="d2a18-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d2a18-135">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d2a18-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d2a18-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="d2a18-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
