---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913513"
---
# <a name="issuermetadata"></a><span data-ttu-id="d18af-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="d18af-101">\<issuerMetadata></span></span>
<span data-ttu-id="d18af-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d18af-102">\<system.serviceModel></span></span>  
<span data-ttu-id="d18af-103">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="d18af-103">\<bindings></span></span>  
<span data-ttu-id="d18af-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d18af-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="d18af-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="d18af-105">\<binding></span></span>  
<span data-ttu-id="d18af-106">\<security></span><span class="sxs-lookup"><span data-stu-id="d18af-106">\<security></span></span>  
<span data-ttu-id="d18af-107">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="d18af-107">\<message></span></span>  
<span data-ttu-id="d18af-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="d18af-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d18af-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d18af-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d18af-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d18af-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d18af-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d18af-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d18af-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d18af-112">Attributes</span></span>  
  
|<span data-ttu-id="d18af-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d18af-113">Attribute</span></span>|<span data-ttu-id="d18af-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d18af-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d18af-115">Address</span><span class="sxs-lookup"><span data-stu-id="d18af-115">address</span></span>|<span data-ttu-id="d18af-116">Attributo `string` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d18af-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="d18af-117">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d18af-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="d18af-118">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="d18af-118">The address must be an absolute URI.</span></span> <span data-ttu-id="d18af-119">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="d18af-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d18af-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d18af-120">Child Elements</span></span>  
  
|<span data-ttu-id="d18af-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d18af-121">Element</span></span>|<span data-ttu-id="d18af-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d18af-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d18af-123">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="d18af-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="d18af-124">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d18af-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="d18af-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="d18af-125">\<identity></span></span>](identity.md)|<span data-ttu-id="d18af-126">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="d18af-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d18af-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d18af-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d18af-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d18af-128">Element</span></span>|<span data-ttu-id="d18af-129">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d18af-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d18af-130">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="d18af-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="d18af-131">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [ \<elemento wsFederationHttpBinding >](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d18af-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d18af-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d18af-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="d18af-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="d18af-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d18af-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="d18af-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d18af-135">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d18af-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d18af-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="d18af-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
