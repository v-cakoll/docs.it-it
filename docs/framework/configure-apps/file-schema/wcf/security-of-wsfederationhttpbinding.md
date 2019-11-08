---
title: <security> di <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: ea029444cee331a235c7a2fc140b4321d7530063
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736322"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="58b63-102">\<> di sicurezza di \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="58b63-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="58b63-103">Definisce le impostazioni di sicurezza del [> wsFederationHttpBinding\<](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="58b63-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="58b63-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58b63-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58b63-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="58b63-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="58b63-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="58b63-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="58b63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="58b63-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="58b63-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="58b63-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="58b63-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="58b63-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b63-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58b63-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
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
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
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
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58b63-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58b63-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58b63-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58b63-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58b63-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="58b63-113">Attributes</span></span>  
  
|<span data-ttu-id="58b63-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="58b63-114">Attribute</span></span>|<span data-ttu-id="58b63-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58b63-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58b63-116">Modalità</span><span class="sxs-lookup"><span data-stu-id="58b63-116">Mode</span></span>|<span data-ttu-id="58b63-117">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58b63-117">Optional.</span></span> <span data-ttu-id="58b63-118">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="58b63-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="58b63-119">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="58b63-119">The default value is `Message`.</span></span> <span data-ttu-id="58b63-120">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="58b63-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="58b63-121">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="58b63-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="58b63-122">Value</span><span class="sxs-lookup"><span data-stu-id="58b63-122">Value</span></span>|<span data-ttu-id="58b63-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58b63-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="58b63-124">Nessuno</span><span class="sxs-lookup"><span data-stu-id="58b63-124">None</span></span>|<span data-ttu-id="58b63-125">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="58b63-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="58b63-126">Messaggio</span><span class="sxs-lookup"><span data-stu-id="58b63-126">Message</span></span>|<span data-ttu-id="58b63-127">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="58b63-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="58b63-128">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="58b63-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="58b63-129">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="58b63-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="58b63-130">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="58b63-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="58b63-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="58b63-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="58b63-132">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="58b63-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="58b63-133">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="58b63-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="58b63-134">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="58b63-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58b63-135">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58b63-135">Child Elements</span></span>  
  
|<span data-ttu-id="58b63-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="58b63-136">Element</span></span>|<span data-ttu-id="58b63-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58b63-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b63-138">\<message ></span><span class="sxs-lookup"><span data-stu-id="58b63-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="58b63-139">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="58b63-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="58b63-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="58b63-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58b63-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58b63-141">Parent Elements</span></span>  
  
|<span data-ttu-id="58b63-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="58b63-142">Element</span></span>|<span data-ttu-id="58b63-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58b63-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b63-144">\<binding ></span><span class="sxs-lookup"><span data-stu-id="58b63-144">\<binding></span></span>](bindings.md)|<span data-ttu-id="58b63-145">Definisce tutte le funzionalità di associazione della [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="58b63-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58b63-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58b63-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="58b63-147">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="58b63-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="58b63-148">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="58b63-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="58b63-149">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="58b63-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="58b63-150">Associazioni</span><span class="sxs-lookup"><span data-stu-id="58b63-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="58b63-151">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="58b63-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="58b63-152">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="58b63-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="58b63-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="58b63-153">\<binding></span></span>](bindings.md)
