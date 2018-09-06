---
title: Elemento &lt;message&gt; di &lt;wsFederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 820ee7015a51ecc5510889516faef20292cfbc07
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871264"
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="dc4e1-102">Elemento &lt;message&gt; di &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="dc4e1-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="dc4e1-103">Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dc4e1-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="dc4e1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dc4e1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc4e1-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="dc4e1-105">\<bindings></span></span>  
<span data-ttu-id="dc4e1-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="dc4e1-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="dc4e1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="dc4e1-107">\<binding></span></span>  
<span data-ttu-id="dc4e1-108">\<security></span><span class="sxs-lookup"><span data-stu-id="dc4e1-108">\<security></span></span>  
<span data-ttu-id="dc4e1-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="dc4e1-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc4e1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc4e1-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
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
                        </issuer>  
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
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc4e1-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dc4e1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dc4e1-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc4e1-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="dc4e1-113">Attributes</span></span>  
  
|<span data-ttu-id="dc4e1-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="dc4e1-114">Attribute</span></span>|<span data-ttu-id="dc4e1-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc4e1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc4e1-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="dc4e1-116">algorithmSuite</span></span>|<span data-ttu-id="dc4e1-117">Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="dc4e1-118">Vedere la tabella "Attributo algorithmSuite" per i valori validi di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="dc4e1-119">Il valore predefinito è `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="dc4e1-120">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="dc4e1-121">Questi algoritmi sono associati a quelli specificati nelle specifiche del linguaggio dei criteri di sicurezza (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="dc4e1-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="dc4e1-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="dc4e1-122">issuedKeyType</span></span>|<span data-ttu-id="dc4e1-123">Specifica il tipo di chiave da emettere.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="dc4e1-124">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="dc4e1-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dc4e1-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="dc4e1-125">-   SymmetricKey</span></span><br /><span data-ttu-id="dc4e1-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="dc4e1-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="dc4e1-127">Il valore predefinito è `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="dc4e1-128">L'attributo è di tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="dc4e1-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="dc4e1-129">issuedTokenType</span></span>|<span data-ttu-id="dc4e1-130">Stringa che contiene un URI che specifica il tipo di token da emettere.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="dc4e1-131">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-131">The default is `null`.</span></span>|  
|<span data-ttu-id="dc4e1-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="dc4e1-132">negotiateServiceCredential</span></span>|<span data-ttu-id="dc4e1-133">Valore booleano che specifica se la credenziale del servizio deve essere scambiata come parte della negoziazione o se è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="dc4e1-134">L'impostazione predefinita è `true`, a indicare che la credenziale del servizio viene negoziata.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="dc4e1-135">Attributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="dc4e1-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="dc4e1-136">Valore</span><span class="sxs-lookup"><span data-stu-id="dc4e1-136">Value</span></span>|<span data-ttu-id="dc4e1-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc4e1-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dc4e1-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="dc4e1-138">Basic128</span></span>|<span data-ttu-id="dc4e1-139">Usa crittografia Basic128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="dc4e1-140">Basic192</span></span>|<span data-ttu-id="dc4e1-141">Usa crittografia Basic192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="dc4e1-142">Basic256</span></span>|<span data-ttu-id="dc4e1-143">Usa crittografia Basic256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-144">Basic256Rsa15</span></span>|<span data-ttu-id="dc4e1-145">Usa Basic256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-146">Basic192Rsa15</span></span>|<span data-ttu-id="dc4e1-147">Usa Basic256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="dc4e1-148">TripleDes</span></span>|<span data-ttu-id="dc4e1-149">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-150">Basic128Rsa15</span></span>|<span data-ttu-id="dc4e1-151">Usa Basic128 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-152">TripleDesRsa15</span></span>|<span data-ttu-id="dc4e1-153">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="dc4e1-154">Basic128Sha256</span></span>|<span data-ttu-id="dc4e1-155">Usa Basic128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="dc4e1-156">Basic192Sha256</span></span>|<span data-ttu-id="dc4e1-157">Usa Basic192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="dc4e1-158">Basic256Sha256</span></span>|<span data-ttu-id="dc4e1-159">Usa Basic256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="dc4e1-160">TripleDesSha256</span></span>|<span data-ttu-id="dc4e1-161">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="dc4e1-163">Usa Basic128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="dc4e1-165">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="dc4e1-167">Usa Basic256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dc4e1-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dc4e1-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="dc4e1-169">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc4e1-170">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dc4e1-170">Child Elements</span></span>  
  
|<span data-ttu-id="dc4e1-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc4e1-171">Element</span></span>|<span data-ttu-id="dc4e1-172">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc4e1-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc4e1-173">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="dc4e1-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="dc4e1-174">Specifica una raccolta di tipi di attestazione per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="dc4e1-175">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="dc4e1-176">issuer</span><span class="sxs-lookup"><span data-stu-id="dc4e1-176">issuer</span></span>|<span data-ttu-id="dc4e1-177">Specifica un endpoint che emette un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="dc4e1-178">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="dc4e1-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="dc4e1-179">issuerMetadata</span></span>|<span data-ttu-id="dc4e1-180">Specifica l'indirizzo dell'endpoint dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="dc4e1-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="dc4e1-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="dc4e1-182">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-182">A collection of token request parameters.</span></span> <span data-ttu-id="dc4e1-183">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc4e1-184">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dc4e1-184">Parent Elements</span></span>  
  
|<span data-ttu-id="dc4e1-185">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc4e1-185">Element</span></span>|<span data-ttu-id="dc4e1-186">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc4e1-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc4e1-187">\<security></span><span class="sxs-lookup"><span data-stu-id="dc4e1-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="dc4e1-188">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="dc4e1-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc4e1-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc4e1-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="dc4e1-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="dc4e1-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="dc4e1-191">Associazioni</span><span class="sxs-lookup"><span data-stu-id="dc4e1-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="dc4e1-192">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="dc4e1-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="dc4e1-193">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="dc4e1-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="dc4e1-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="dc4e1-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
