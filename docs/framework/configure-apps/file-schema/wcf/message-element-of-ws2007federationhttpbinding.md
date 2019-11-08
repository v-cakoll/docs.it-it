---
title: elemento <message> di <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738993"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="33359-102">\<messaggio > elemento di \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="33359-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="33359-103">Definisce le impostazioni per la sicurezza a livello di messaggio per l'elemento [\<> WS2007FederationHttpBinding](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="33359-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="33359-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33359-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33359-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="33359-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33359-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="33359-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="33359-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**WS2007FederationHttpBinding**](ws2007federationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="33359-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="33359-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="33359-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="33359-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-element-of-ws2007federationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="33359-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="33359-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**messaggio** ></span><span class="sxs-lookup"><span data-stu-id="33359-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33359-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33359-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33359-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33359-112">Attributes and Elements</span></span>  
 <span data-ttu-id="33359-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33359-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33359-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="33359-114">Attributes</span></span>  
  
|<span data-ttu-id="33359-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="33359-115">Attribute</span></span>|<span data-ttu-id="33359-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33359-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="33359-117">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="33359-117">Optional.</span></span> <span data-ttu-id="33359-118">Imposta la crittografia del messaggio, la firma e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="33359-119">Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="33359-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="33359-120">Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="33359-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="33359-121">Nella tabella che segue sono elencati i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="33359-121">See the following table for possible values.</span></span> <span data-ttu-id="33359-122">Il valore predefinito è Basic256.</span><span class="sxs-lookup"><span data-stu-id="33359-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="33359-123">Specifica il tipo di chiave da emettere.</span><span class="sxs-lookup"><span data-stu-id="33359-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="33359-124">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="33359-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="33359-125">-Dipero</span><span class="sxs-lookup"><span data-stu-id="33359-125">-   SymmetricKey</span></span><br /><span data-ttu-id="33359-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="33359-126">-   PublicKey</span></span><br /><span data-ttu-id="33359-127">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="33359-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="33359-128">L'impostazione predefinita è SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="33359-128">The default is SymmetricKey.</span></span> <span data-ttu-id="33359-129">L'attributo è di tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="33359-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="33359-130">URI che specifica il tipo di token da emettere.</span><span class="sxs-lookup"><span data-stu-id="33359-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="33359-131">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="33359-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="33359-132">Valore che specifica se la credenziale del servizio deve essere scambiata come parte della negoziazione o se è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="33359-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="33359-133">L'impostazione predefinita è `true`, a indicare che la credenziale del servizio viene negoziata.</span><span class="sxs-lookup"><span data-stu-id="33359-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="33359-134">Attributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="33359-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="33359-135">Value</span><span class="sxs-lookup"><span data-stu-id="33359-135">Value</span></span>|<span data-ttu-id="33359-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33359-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33359-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="33359-137">Basic128</span></span>|<span data-ttu-id="33359-138">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="33359-139">Basic192</span></span>|<span data-ttu-id="33359-140">Usa crittografia Aes192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="33359-141">Basic256</span></span>|<span data-ttu-id="33359-142">Usa crittografia Aes256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33359-143">Basic256Rsa15</span></span>|<span data-ttu-id="33359-144">Usa Aes256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33359-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="33359-145">Basic192Rsa15</span></span>|<span data-ttu-id="33359-146">Usa Aes192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33359-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="33359-147">TripleDes</span></span>|<span data-ttu-id="33359-148">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="33359-149">Basic128Rsa15</span></span>|<span data-ttu-id="33359-150">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33359-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="33359-151">TripleDesRsa15</span></span>|<span data-ttu-id="33359-152">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33359-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="33359-153">Basic128Sha256</span></span>|<span data-ttu-id="33359-154">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="33359-155">Basic192Sha256</span></span>|<span data-ttu-id="33359-156">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="33359-157">Basic256Sha256</span></span>|<span data-ttu-id="33359-158">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="33359-159">TripleDesSha256</span></span>|<span data-ttu-id="33359-160">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33359-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33359-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="33359-162">Usa Aes128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33359-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33359-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="33359-164">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33359-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33359-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="33359-166">Usa Aes256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33359-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33359-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="33359-168">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33359-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33359-169">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33359-169">Child Elements</span></span>  
  
|<span data-ttu-id="33359-170">Elemento</span><span class="sxs-lookup"><span data-stu-id="33359-170">Element</span></span>|<span data-ttu-id="33359-171">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33359-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33359-172">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="33359-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="33359-173">Specifica una raccolta di tipi di attestazione per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="33359-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="33359-174">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="33359-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="33359-175">\<autorità emittente ></span><span class="sxs-lookup"><span data-stu-id="33359-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="33359-176">Specifica un endpoint che emette un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="33359-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="33359-177">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="33359-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="33359-178">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="33359-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="33359-179">Specifica l'indirizzo dell'endpoint dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="33359-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="33359-180">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="33359-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="33359-181">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="33359-181">A collection of token request parameters.</span></span> <span data-ttu-id="33359-182">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="33359-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33359-183">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33359-183">Parent Elements</span></span>  
  
|<span data-ttu-id="33359-184">Elemento</span><span class="sxs-lookup"><span data-stu-id="33359-184">Element</span></span>|<span data-ttu-id="33359-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33359-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33359-186">\<security ></span><span class="sxs-lookup"><span data-stu-id="33359-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="33359-187">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="33359-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33359-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33359-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="33359-189">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="33359-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="33359-190">Associazioni</span><span class="sxs-lookup"><span data-stu-id="33359-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="33359-191">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="33359-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="33359-192">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="33359-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="33359-193">\<binding ></span><span class="sxs-lookup"><span data-stu-id="33359-193">\<binding></span></span>](bindings.md)
