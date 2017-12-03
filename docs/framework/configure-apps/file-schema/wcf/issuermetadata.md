---
title: '&lt;issuerMetadata&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d2a4669c86142a66500407edbdda44e9dec81a0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="e59df-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="e59df-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="e59df-103">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e59df-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e59df-104">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="e59df-104">\<bindings></span></span>  
<span data-ttu-id="e59df-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e59df-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="e59df-106">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="e59df-106">\<binding></span></span>  
<span data-ttu-id="e59df-107">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="e59df-107">\<security></span></span>  
<span data-ttu-id="e59df-108">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="e59df-108">\<message></span></span>  
<span data-ttu-id="e59df-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="e59df-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e59df-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e59df-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e59df-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e59df-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e59df-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e59df-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e59df-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e59df-113">Attributes</span></span>  
  
|<span data-ttu-id="e59df-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="e59df-114">Attribute</span></span>|<span data-ttu-id="e59df-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e59df-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e59df-116">address</span><span class="sxs-lookup"><span data-stu-id="e59df-116">address</span></span>|<span data-ttu-id="e59df-117">Attributo `string` obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e59df-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="e59df-118">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e59df-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="e59df-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="e59df-119">The address must be an absolute URI.</span></span> <span data-ttu-id="e59df-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e59df-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e59df-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e59df-121">Child Elements</span></span>  
  
|<span data-ttu-id="e59df-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="e59df-122">Element</span></span>|<span data-ttu-id="e59df-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e59df-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e59df-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="e59df-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="e59df-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="e59df-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="e59df-126">\<identità ></span><span class="sxs-lookup"><span data-stu-id="e59df-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e59df-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="e59df-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e59df-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e59df-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e59df-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="e59df-129">Element</span></span>|<span data-ttu-id="e59df-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e59df-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e59df-131">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="e59df-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="e59df-132">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e59df-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e59df-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e59df-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="e59df-134">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="e59df-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="e59df-135">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="e59df-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="e59df-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e59df-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="e59df-137">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="e59df-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
