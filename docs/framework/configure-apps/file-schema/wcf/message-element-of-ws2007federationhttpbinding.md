---
title: <message> elemento di <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: f05bd90bd2e4c7e1fd606518d9e5cb8d4e5ad974
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767572"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="5c9a8-102">\<messaggio > dell'elemento \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="5c9a8-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="5c9a8-103">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="5c9a8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5c9a8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c9a8-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="5c9a8-105">\<bindings></span></span>  
<span data-ttu-id="5c9a8-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5c9a8-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="5c9a8-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5c9a8-107">\<binding></span></span>  
<span data-ttu-id="5c9a8-108">\<security></span><span class="sxs-lookup"><span data-stu-id="5c9a8-108">\<security></span></span>  
<span data-ttu-id="5c9a8-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="5c9a8-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c9a8-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c9a8-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
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
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c9a8-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5c9a8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5c9a8-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c9a8-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="5c9a8-113">Attributes</span></span>  
  
|<span data-ttu-id="5c9a8-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="5c9a8-114">Attribute</span></span>|<span data-ttu-id="5c9a8-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c9a8-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="5c9a8-116">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-116">Optional.</span></span> <span data-ttu-id="5c9a8-117">Imposta la crittografia del messaggio, la firma e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="5c9a8-118">Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="5c9a8-119">Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="5c9a8-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="5c9a8-120">Nella tabella che segue sono elencati i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-120">See the following table for possible values.</span></span> <span data-ttu-id="5c9a8-121">Il valore predefinito è Basic256.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="5c9a8-122">Specifica il tipo di chiave da emettere.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="5c9a8-123">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="5c9a8-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5c9a8-124">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="5c9a8-124">-   SymmetricKey</span></span><br /><span data-ttu-id="5c9a8-125">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="5c9a8-125">-   PublicKey</span></span><br /><span data-ttu-id="5c9a8-126">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="5c9a8-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="5c9a8-127">L'impostazione predefinita è SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-127">The default is SymmetricKey.</span></span> <span data-ttu-id="5c9a8-128">L'attributo è di tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="5c9a8-129">URI che specifica il tipo di token da emettere.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="5c9a8-130">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="5c9a8-131">Valore che specifica se la credenziale del servizio deve essere scambiata come parte della negoziazione o se è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="5c9a8-132">L'impostazione predefinita è `true`, a indicare che la credenziale del servizio viene negoziata.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="5c9a8-133">Attributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="5c9a8-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="5c9a8-134">Value</span><span class="sxs-lookup"><span data-stu-id="5c9a8-134">Value</span></span>|<span data-ttu-id="5c9a8-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c9a8-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c9a8-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="5c9a8-136">Basic128</span></span>|<span data-ttu-id="5c9a8-137">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="5c9a8-138">Basic192</span></span>|<span data-ttu-id="5c9a8-139">Usa crittografia Aes192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="5c9a8-140">Basic256</span></span>|<span data-ttu-id="5c9a8-141">Usa crittografia Aes256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-142">Basic256Rsa15</span></span>|<span data-ttu-id="5c9a8-143">Usa Aes256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-144">Basic192Rsa15</span></span>|<span data-ttu-id="5c9a8-145">Usa Aes192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="5c9a8-146">TripleDes</span></span>|<span data-ttu-id="5c9a8-147">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-148">Basic128Rsa15</span></span>|<span data-ttu-id="5c9a8-149">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-150">TripleDesRsa15</span></span>|<span data-ttu-id="5c9a8-151">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="5c9a8-152">Basic128Sha256</span></span>|<span data-ttu-id="5c9a8-153">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="5c9a8-154">Basic192Sha256</span></span>|<span data-ttu-id="5c9a8-155">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="5c9a8-156">Basic256Sha256</span></span>|<span data-ttu-id="5c9a8-157">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="5c9a8-158">TripleDesSha256</span></span>|<span data-ttu-id="5c9a8-159">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="5c9a8-161">Usa Aes128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="5c9a8-163">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="5c9a8-165">Usa Aes256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5c9a8-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5c9a8-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="5c9a8-167">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c9a8-168">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5c9a8-168">Child Elements</span></span>  
  
|<span data-ttu-id="5c9a8-169">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c9a8-169">Element</span></span>|<span data-ttu-id="5c9a8-170">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c9a8-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c9a8-171">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="5c9a8-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="5c9a8-172">Specifica una raccolta di tipi di attestazione per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="5c9a8-173">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="5c9a8-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="5c9a8-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="5c9a8-175">Specifica un endpoint che emette un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="5c9a8-176">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="5c9a8-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="5c9a8-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="5c9a8-178">Specifica l'indirizzo dell'endpoint dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="5c9a8-179">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="5c9a8-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="5c9a8-180">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-180">A collection of token request parameters.</span></span> <span data-ttu-id="5c9a8-181">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c9a8-182">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5c9a8-182">Parent Elements</span></span>  
  
|<span data-ttu-id="5c9a8-183">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c9a8-183">Element</span></span>|<span data-ttu-id="5c9a8-184">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c9a8-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c9a8-185">\<security></span><span class="sxs-lookup"><span data-stu-id="5c9a8-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="5c9a8-186">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="5c9a8-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c9a8-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c9a8-187">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="5c9a8-188">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="5c9a8-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5c9a8-189">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5c9a8-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5c9a8-190">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="5c9a8-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5c9a8-191">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="5c9a8-191">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5c9a8-192">\<binding></span><span class="sxs-lookup"><span data-stu-id="5c9a8-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
