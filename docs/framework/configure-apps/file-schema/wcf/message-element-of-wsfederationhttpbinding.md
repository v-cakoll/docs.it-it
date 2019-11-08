---
title: elemento <message> di <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738991"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="33b8e-102">messaggio \<> elemento di \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="33b8e-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="33b8e-103">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [> WSFederationHttpBinding del\<](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="33b8e-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="33b8e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33b8e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33b8e-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="33b8e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33b8e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="33b8e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="33b8e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="33b8e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="33b8e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="33b8e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="33b8e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-of-wsfederationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="33b8e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="33b8e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**messaggio** ></span><span class="sxs-lookup"><span data-stu-id="33b8e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b8e-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33b8e-111">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33b8e-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33b8e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="33b8e-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33b8e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33b8e-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="33b8e-114">Attributes</span></span>  
  
|<span data-ttu-id="33b8e-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="33b8e-115">Attribute</span></span>|<span data-ttu-id="33b8e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b8e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33b8e-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="33b8e-117">algorithmSuite</span></span>|<span data-ttu-id="33b8e-118">Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="33b8e-119">Vedere la tabella "Attributo algorithmSuite" per i valori validi di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="33b8e-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="33b8e-120">Il valore predefinito è `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="33b8e-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="33b8e-121">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="33b8e-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="33b8e-122">Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="33b8e-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="33b8e-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="33b8e-123">issuedKeyType</span></span>|<span data-ttu-id="33b8e-124">Specifica il tipo di chiave da emettere.</span><span class="sxs-lookup"><span data-stu-id="33b8e-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="33b8e-125">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="33b8e-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="33b8e-126">-Dipero</span><span class="sxs-lookup"><span data-stu-id="33b8e-126">-   SymmetricKey</span></span><br /><span data-ttu-id="33b8e-127">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="33b8e-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="33b8e-128">Il valore predefinito è `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="33b8e-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="33b8e-129">L'attributo è di tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="33b8e-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="33b8e-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="33b8e-130">issuedTokenType</span></span>|<span data-ttu-id="33b8e-131">Stringa che contiene un URI che specifica il tipo di token da emettere.</span><span class="sxs-lookup"><span data-stu-id="33b8e-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="33b8e-132">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="33b8e-132">The default is `null`.</span></span>|  
|<span data-ttu-id="33b8e-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="33b8e-133">negotiateServiceCredential</span></span>|<span data-ttu-id="33b8e-134">Valore booleano che specifica se la credenziale del servizio deve essere scambiata come parte della negoziazione o se è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="33b8e-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="33b8e-135">L'impostazione predefinita è `true`, a indicare che la credenziale del servizio viene negoziata.</span><span class="sxs-lookup"><span data-stu-id="33b8e-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="33b8e-136">Attributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="33b8e-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="33b8e-137">Value</span><span class="sxs-lookup"><span data-stu-id="33b8e-137">Value</span></span>|<span data-ttu-id="33b8e-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b8e-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b8e-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="33b8e-139">Basic128</span></span>|<span data-ttu-id="33b8e-140">Usa crittografia Basic128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="33b8e-141">Basic192</span></span>|<span data-ttu-id="33b8e-142">Usa crittografia Basic192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="33b8e-143">Basic256</span></span>|<span data-ttu-id="33b8e-144">Usa crittografia Basic256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-145">Basic256Rsa15</span></span>|<span data-ttu-id="33b8e-146">Usa Basic256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-147">Basic192Rsa15</span></span>|<span data-ttu-id="33b8e-148">Usa Basic192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="33b8e-149">TripleDes</span></span>|<span data-ttu-id="33b8e-150">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-151">Basic128Rsa15</span></span>|<span data-ttu-id="33b8e-152">Usa Basic128 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-153">TripleDesRsa15</span></span>|<span data-ttu-id="33b8e-154">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="33b8e-155">Basic128Sha256</span></span>|<span data-ttu-id="33b8e-156">Usa Basic128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="33b8e-157">Basic192Sha256</span></span>|<span data-ttu-id="33b8e-158">Usa Basic192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="33b8e-159">Basic256Sha256</span></span>|<span data-ttu-id="33b8e-160">Usa Basic256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="33b8e-161">TripleDesSha256</span></span>|<span data-ttu-id="33b8e-162">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="33b8e-164">Usa Basic128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="33b8e-166">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="33b8e-168">Usa Basic256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="33b8e-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="33b8e-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="33b8e-170">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="33b8e-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33b8e-171">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33b8e-171">Child Elements</span></span>  
  
|<span data-ttu-id="33b8e-172">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b8e-172">Element</span></span>|<span data-ttu-id="33b8e-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b8e-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33b8e-174">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="33b8e-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="33b8e-175">Specifica una raccolta di tipi di attestazione per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="33b8e-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="33b8e-176">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="33b8e-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="33b8e-177">issuer</span><span class="sxs-lookup"><span data-stu-id="33b8e-177">issuer</span></span>|<span data-ttu-id="33b8e-178">Specifica un endpoint che emette un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="33b8e-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="33b8e-179">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="33b8e-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="33b8e-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="33b8e-180">issuerMetadata</span></span>|<span data-ttu-id="33b8e-181">Specifica l'indirizzo dell'endpoint dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="33b8e-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="33b8e-182">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="33b8e-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="33b8e-183">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="33b8e-183">A collection of token request parameters.</span></span> <span data-ttu-id="33b8e-184">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="33b8e-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33b8e-185">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33b8e-185">Parent Elements</span></span>  
  
|<span data-ttu-id="33b8e-186">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b8e-186">Element</span></span>|<span data-ttu-id="33b8e-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b8e-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33b8e-188">\<security ></span><span class="sxs-lookup"><span data-stu-id="33b8e-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="33b8e-189">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="33b8e-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33b8e-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33b8e-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="33b8e-191">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="33b8e-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="33b8e-192">Associazioni</span><span class="sxs-lookup"><span data-stu-id="33b8e-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="33b8e-193">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="33b8e-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="33b8e-194">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="33b8e-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="33b8e-195">\<binding ></span><span class="sxs-lookup"><span data-stu-id="33b8e-195">\<binding></span></span>](bindings.md)
