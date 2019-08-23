---
title: <message>elemento di<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: 4340727026cb151f2efe813dfa005c1c5a1908be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931629"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="89396-102">\<messaggio > elemento di \<WS2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="89396-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="89396-103">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [ \<elemento > WS2007FederationHttpBinding](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="89396-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="89396-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="89396-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="89396-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="89396-105">\<bindings></span></span>  
<span data-ttu-id="89396-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="89396-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="89396-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="89396-107">\<binding></span></span>  
<span data-ttu-id="89396-108">\<security></span><span class="sxs-lookup"><span data-stu-id="89396-108">\<security></span></span>  
<span data-ttu-id="89396-109">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="89396-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89396-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89396-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89396-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89396-111">Attributes and Elements</span></span>  
 <span data-ttu-id="89396-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89396-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89396-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="89396-113">Attributes</span></span>  
  
|<span data-ttu-id="89396-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="89396-114">Attribute</span></span>|<span data-ttu-id="89396-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="89396-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="89396-116">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="89396-116">Optional.</span></span> <span data-ttu-id="89396-117">Imposta la crittografia del messaggio, la firma e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="89396-118">Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="89396-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="89396-119">Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="89396-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="89396-120">Nella tabella che segue sono elencati i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="89396-120">See the following table for possible values.</span></span> <span data-ttu-id="89396-121">Il valore predefinito è Basic256.</span><span class="sxs-lookup"><span data-stu-id="89396-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="89396-122">Specifica il tipo di chiave da emettere.</span><span class="sxs-lookup"><span data-stu-id="89396-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="89396-123">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="89396-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="89396-124">-Dipero</span><span class="sxs-lookup"><span data-stu-id="89396-124">-   SymmetricKey</span></span><br /><span data-ttu-id="89396-125">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="89396-125">-   PublicKey</span></span><br /><span data-ttu-id="89396-126">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="89396-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="89396-127">L'impostazione predefinita è SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="89396-127">The default is SymmetricKey.</span></span> <span data-ttu-id="89396-128">L'attributo è di tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="89396-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="89396-129">URI che specifica il tipo di token da emettere.</span><span class="sxs-lookup"><span data-stu-id="89396-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="89396-130">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="89396-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="89396-131">Valore che specifica se la credenziale del servizio deve essere scambiata come parte della negoziazione o se è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="89396-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="89396-132">L'impostazione predefinita è `true`, a indicare che la credenziale del servizio viene negoziata.</span><span class="sxs-lookup"><span data-stu-id="89396-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="89396-133">Attributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="89396-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="89396-134">Value</span><span class="sxs-lookup"><span data-stu-id="89396-134">Value</span></span>|<span data-ttu-id="89396-135">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="89396-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89396-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="89396-136">Basic128</span></span>|<span data-ttu-id="89396-137">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="89396-138">Basic192</span></span>|<span data-ttu-id="89396-139">Usa crittografia Aes192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="89396-140">Basic256</span></span>|<span data-ttu-id="89396-141">Usa crittografia Aes256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="89396-142">Basic256Rsa15</span></span>|<span data-ttu-id="89396-143">Usa Aes256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="89396-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="89396-144">Basic192Rsa15</span></span>|<span data-ttu-id="89396-145">Usa Aes192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="89396-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="89396-146">TripleDes</span></span>|<span data-ttu-id="89396-147">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="89396-148">Basic128Rsa15</span></span>|<span data-ttu-id="89396-149">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="89396-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="89396-150">TripleDesRsa15</span></span>|<span data-ttu-id="89396-151">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="89396-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="89396-152">Basic128Sha256</span></span>|<span data-ttu-id="89396-153">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="89396-154">Basic192Sha256</span></span>|<span data-ttu-id="89396-155">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="89396-156">Basic256Sha256</span></span>|<span data-ttu-id="89396-157">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="89396-158">TripleDesSha256</span></span>|<span data-ttu-id="89396-159">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="89396-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="89396-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="89396-161">Usa Aes128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="89396-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="89396-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="89396-163">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="89396-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="89396-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="89396-165">Usa Aes256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="89396-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="89396-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="89396-167">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="89396-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89396-168">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89396-168">Child Elements</span></span>  
  
|<span data-ttu-id="89396-169">Elemento</span><span class="sxs-lookup"><span data-stu-id="89396-169">Element</span></span>|<span data-ttu-id="89396-170">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89396-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89396-171">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="89396-171">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="89396-172">Specifica una raccolta di tipi di attestazione per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="89396-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="89396-173">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="89396-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="89396-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="89396-174">\<issuer></span></span>](issuer.md)|<span data-ttu-id="89396-175">Specifica un endpoint che emette un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="89396-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="89396-176">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="89396-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="89396-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="89396-177">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="89396-178">Specifica l'indirizzo dell'endpoint dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="89396-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="89396-179">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="89396-179">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="89396-180">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="89396-180">A collection of token request parameters.</span></span> <span data-ttu-id="89396-181">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="89396-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89396-182">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89396-182">Parent Elements</span></span>  
  
|<span data-ttu-id="89396-183">Elemento</span><span class="sxs-lookup"><span data-stu-id="89396-183">Element</span></span>|<span data-ttu-id="89396-184">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="89396-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89396-185">\<security></span><span class="sxs-lookup"><span data-stu-id="89396-185">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="89396-186">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="89396-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89396-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89396-187">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="89396-188">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="89396-188">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="89396-189">Associazioni</span><span class="sxs-lookup"><span data-stu-id="89396-189">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="89396-190">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="89396-190">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="89396-191">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="89396-191">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="89396-192">\<binding></span><span class="sxs-lookup"><span data-stu-id="89396-192">\<binding></span></span>](../../../misc/binding.md)
