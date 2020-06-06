---
title: <message>elemento di<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738993"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="d4d4c-102">\<message>elemento di\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d4d4c-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="d4d4c-103">Definisce le impostazioni per la sicurezza a livello di messaggio per l' [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="d4d4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4d4c-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4d4c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d4d4c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d4d4c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4d4c-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="d4d4c-107">Attributes</span></span>  
  
|<span data-ttu-id="d4d4c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="d4d4c-108">Attribute</span></span>|<span data-ttu-id="d4d4c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4d4c-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="d4d4c-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-110">Optional.</span></span> <span data-ttu-id="d4d4c-111">Imposta la crittografia del messaggio, la firma e gli algoritmi di incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="d4d4c-112">Gli algoritmi e le dimensioni della chiave sono determinati dalla classe <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="d4d4c-113">Questi algoritmi sono associati a quelli indicati nella specifica Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="d4d4c-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="d4d4c-114">Nella tabella che segue sono elencati i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-114">See the following table for possible values.</span></span> <span data-ttu-id="d4d4c-115">Il valore predefinito è Basic256.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="d4d4c-116">Specifica il tipo di chiave da emettere.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="d4d4c-117">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4d4c-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d4d4c-118">-Dipero</span><span class="sxs-lookup"><span data-stu-id="d4d4c-118">-   SymmetricKey</span></span><br /><span data-ttu-id="d4d4c-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="d4d4c-119">-   PublicKey</span></span><br /><span data-ttu-id="d4d4c-120">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="d4d4c-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="d4d4c-121">L'impostazione predefinita è SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-121">The default is SymmetricKey.</span></span> <span data-ttu-id="d4d4c-122">L'attributo è di tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="d4d4c-123">URI che specifica il tipo di token da emettere.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="d4d4c-124">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="d4d4c-125">Valore che specifica se la credenziale del servizio deve essere scambiata come parte della negoziazione o se è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="d4d4c-126">L'impostazione predefinita è `true`, a indicare che la credenziale del servizio viene negoziata.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="d4d4c-127">Attributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="d4d4c-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="d4d4c-128">Valore</span><span class="sxs-lookup"><span data-stu-id="d4d4c-128">Value</span></span>|<span data-ttu-id="d4d4c-129">Description</span><span class="sxs-lookup"><span data-stu-id="d4d4c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d4d4c-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="d4d4c-130">Basic128</span></span>|<span data-ttu-id="d4d4c-131">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="d4d4c-132">Basic192</span></span>|<span data-ttu-id="d4d4c-133">Usa crittografia Aes192, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="d4d4c-134">Basic256</span></span>|<span data-ttu-id="d4d4c-135">Usa crittografia Aes256, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-136">Basic256Rsa15</span></span>|<span data-ttu-id="d4d4c-137">Usa Aes256 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-138">Basic192Rsa15</span></span>|<span data-ttu-id="d4d4c-139">Usa Aes192 per la crittografia del messaggio, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="d4d4c-140">TripleDes</span></span>|<span data-ttu-id="d4d4c-141">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-142">Basic128Rsa15</span></span>|<span data-ttu-id="d4d4c-143">Usa crittografia Aes128, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-144">TripleDesRsa15</span></span>|<span data-ttu-id="d4d4c-145">Usa crittografia TripleDes, Sha1 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="d4d4c-146">Basic128Sha256</span></span>|<span data-ttu-id="d4d4c-147">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="d4d4c-148">Basic192Sha256</span></span>|<span data-ttu-id="d4d4c-149">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="d4d4c-150">Basic256Sha256</span></span>|<span data-ttu-id="d4d4c-151">Usa crittografia Aes256, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="d4d4c-152">TripleDesSha256</span></span>|<span data-ttu-id="d4d4c-153">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa-oaep-mgf1p per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="d4d4c-155">Usa Aes128 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="d4d4c-157">Usa Aes192 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="d4d4c-159">Usa Aes256 per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d4d4c-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d4d4c-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="d4d4c-161">Usa TripleDes per la crittografia del messaggio, Sha256 per il digest del messaggio e Rsa15 per l'incapsulamento della chiave.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4d4c-162">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d4d4c-162">Child Elements</span></span>  
  
|<span data-ttu-id="d4d4c-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4d4c-163">Element</span></span>|<span data-ttu-id="d4d4c-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4d4c-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="d4d4c-165">Specifica una raccolta di tipi di attestazione per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="d4d4c-166">Ciascun elemento è di tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="d4d4c-167">Specifica un endpoint che emette un token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="d4d4c-168">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="d4d4c-169">Specifica l'indirizzo dell'endpoint dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="d4d4c-170">Raccolta di parametri della richiesta di token.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-170">A collection of token request parameters.</span></span> <span data-ttu-id="d4d4c-171">Ciascun parametro è un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4d4c-172">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d4d4c-172">Parent Elements</span></span>  
  
|<span data-ttu-id="d4d4c-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4d4c-173">Element</span></span>|<span data-ttu-id="d4d4c-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4d4c-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="d4d4c-175">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="d4d4c-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4d4c-176">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d4d4c-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="d4d4c-177">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="d4d4c-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d4d4c-178">Binding</span><span class="sxs-lookup"><span data-stu-id="d4d4c-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d4d4c-179">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d4d4c-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d4d4c-180">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d4d4c-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
