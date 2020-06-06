---
title: <message>elemento di<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738991"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="1d677-102">\<message>elemento di\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1d677-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="1d677-103">Definisce le impostazioni per la sicurezza a livello di messaggio per l'oggetto [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1d677-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="1d677-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d677-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d677-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1d677-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1d677-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1d677-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d677-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1d677-107">Attributes</span></span>  
  
|<span data-ttu-id="1d677-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="1d677-108">Attribute</span></span>|<span data-ttu-id="1d677-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d677-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d677-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="1d677-110">algorithmSuite</span></span>|<span data-ttu-id="1d677-111">Imposta la crittografia dei messaggi e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="1d677-112">Vedere la tabella "Attributo algorithmSuite" per i valori validi di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="1d677-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="1d677-113">Il valore predefinito è `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="1d677-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="1d677-114">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="1d677-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="1d677-115">Questi algoritmi sono associati a quelli indicati nella specifica Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="1d677-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="1d677-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="1d677-116">issuedKeyType</span></span>|<span data-ttu-id="1d677-117">Specifica il tipo di chiave da emettere.</span><span class="sxs-lookup"><span data-stu-id="1d677-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="1d677-118">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d677-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1d677-119">-Dipero</span><span class="sxs-lookup"><span data-stu-id="1d677-119">-   SymmetricKey</span></span><br /><span data-ttu-id="1d677-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="1d677-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="1d677-121">Il valore predefinito è `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="1d677-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="1d677-122">L'attributo è di tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="1d677-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="1d677-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="1d677-123">issuedTokenType</span></span>|<span data-ttu-id="1d677-124">Stringa che contiene un URI che specifica il tipo di token da emettere.</span><span class="sxs-lookup"><span data-stu-id="1d677-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="1d677-125">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="1d677-125">The default is `null`.</span></span>|  
|<span data-ttu-id="1d677-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="1d677-126">negotiateServiceCredential</span></span>|<span data-ttu-id="1d677-127">Valore booleano che specifica se la credenziale del servizio deve essere scambiata come parte della negoziazione o se è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="1d677-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="1d677-128">L'impostazione predefinita è `true`, a indicare che la credenziale del servizio viene negoziata.</span><span class="sxs-lookup"><span data-stu-id="1d677-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="1d677-129">Attributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="1d677-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="1d677-130">Valore</span><span class="sxs-lookup"><span data-stu-id="1d677-130">Value</span></span>|<span data-ttu-id="1d677-131">Description</span><span class="sxs-lookup"><span data-stu-id="1d677-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1d677-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="1d677-132">Basic128</span></span>|<span data-ttu-id="1d677-133">Usa crittografia Basic128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="1d677-134">Basic192</span></span>|<span data-ttu-id="1d677-135">Usa crittografia Basic192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="1d677-136">Basic256</span></span>|<span data-ttu-id="1d677-137">Usa crittografia Basic256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-138">Basic256Rsa15</span></span>|<span data-ttu-id="1d677-139">Usa Basic256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="1d677-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-140">Basic192Rsa15</span></span>|<span data-ttu-id="1d677-141">Usa Basic192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="1d677-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="1d677-142">TripleDes</span></span>|<span data-ttu-id="1d677-143">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-144">Basic128Rsa15</span></span>|<span data-ttu-id="1d677-145">Usa Basic128 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="1d677-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-146">TripleDesRsa15</span></span>|<span data-ttu-id="1d677-147">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="1d677-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="1d677-148">Basic128Sha256</span></span>|<span data-ttu-id="1d677-149">Usa Basic128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="1d677-150">Basic192Sha256</span></span>|<span data-ttu-id="1d677-151">Usa Basic192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="1d677-152">Basic256Sha256</span></span>|<span data-ttu-id="1d677-153">Usa Basic256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="1d677-154">TripleDesSha256</span></span>|<span data-ttu-id="1d677-155">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="1d677-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="1d677-157">Usa Basic128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="1d677-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="1d677-159">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="1d677-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="1d677-161">Usa Basic256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="1d677-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="1d677-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="1d677-163">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="1d677-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d677-164">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1d677-164">Child Elements</span></span>  
  
|<span data-ttu-id="1d677-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d677-165">Element</span></span>|<span data-ttu-id="1d677-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d677-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="1d677-167">Specifica una raccolta di tipi di attestazione per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="1d677-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="1d677-168">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="1d677-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="1d677-169">autorità di certificazione</span><span class="sxs-lookup"><span data-stu-id="1d677-169">issuer</span></span>|<span data-ttu-id="1d677-170">Specifica un endpoint che emette un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1d677-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="1d677-171">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="1d677-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="1d677-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="1d677-172">issuerMetadata</span></span>|<span data-ttu-id="1d677-173">Specifica l'indirizzo dell'endpoint dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="1d677-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="1d677-174">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="1d677-174">A collection of token request parameters.</span></span> <span data-ttu-id="1d677-175">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="1d677-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d677-176">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1d677-176">Parent Elements</span></span>  
  
|<span data-ttu-id="1d677-177">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d677-177">Element</span></span>|<span data-ttu-id="1d677-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d677-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="1d677-179">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="1d677-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d677-180">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1d677-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="1d677-181">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="1d677-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1d677-182">Binding</span><span class="sxs-lookup"><span data-stu-id="1d677-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1d677-183">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1d677-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1d677-184">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="1d677-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
