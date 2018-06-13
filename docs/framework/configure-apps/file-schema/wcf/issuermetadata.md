---
title: '&lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 5f6b8d2f861c4d64a3b81407de4ce13b42d9b864
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752933"
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="36fbb-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="36fbb-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="36fbb-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="36fbb-103">\<system.serviceModel></span></span>  
<span data-ttu-id="36fbb-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="36fbb-104">\<bindings></span></span>  
<span data-ttu-id="36fbb-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="36fbb-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="36fbb-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="36fbb-106">\<binding></span></span>  
<span data-ttu-id="36fbb-107">\<security></span><span class="sxs-lookup"><span data-stu-id="36fbb-107">\<security></span></span>  
<span data-ttu-id="36fbb-108">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="36fbb-108">\<message></span></span>  
<span data-ttu-id="36fbb-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="36fbb-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36fbb-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36fbb-110">Syntax</span></span>  
  
```xml  
<issuerMetadata address=String" >  
   <headers>  
      <add name="String"  
                 namespace="String" />  
   </headers>  
   <identity>  
           <certificate encodedValue="String"/>  
      <certificateReference findValue="String"   
         isChainIncluded="Boolean"  
         storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
         storeLocation="LocalMachine/CurrentUser"  
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuerMetadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36fbb-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="36fbb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="36fbb-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="36fbb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36fbb-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="36fbb-113">Attributes</span></span>  
  
|<span data-ttu-id="36fbb-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="36fbb-114">Attribute</span></span>|<span data-ttu-id="36fbb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36fbb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36fbb-116">address</span><span class="sxs-lookup"><span data-stu-id="36fbb-116">address</span></span>|<span data-ttu-id="36fbb-117">Attributo `string` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="36fbb-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="36fbb-118">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="36fbb-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="36fbb-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="36fbb-119">The address must be an absolute URI.</span></span> <span data-ttu-id="36fbb-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="36fbb-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36fbb-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="36fbb-121">Child Elements</span></span>  
  
|<span data-ttu-id="36fbb-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="36fbb-122">Element</span></span>|<span data-ttu-id="36fbb-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36fbb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36fbb-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="36fbb-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="36fbb-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="36fbb-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="36fbb-126">\<identità ></span><span class="sxs-lookup"><span data-stu-id="36fbb-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="36fbb-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="36fbb-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36fbb-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="36fbb-128">Parent Elements</span></span>  
  
|<span data-ttu-id="36fbb-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="36fbb-129">Element</span></span>|<span data-ttu-id="36fbb-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36fbb-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36fbb-131">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="36fbb-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="36fbb-132">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="36fbb-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36fbb-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36fbb-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="36fbb-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="36fbb-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="36fbb-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="36fbb-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="36fbb-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="36fbb-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="36fbb-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="36fbb-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
