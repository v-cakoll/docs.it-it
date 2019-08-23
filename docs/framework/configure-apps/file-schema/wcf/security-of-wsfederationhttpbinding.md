---
title: <security> di <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 875ce7d548d59f32465da817e9e956217f346f60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936528"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="39658-102">\<> di sicurezza \<di WSFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="39658-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="39658-103">Definisce le impostazioni di sicurezza del [ \<> WSFederationHttpBinding](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="39658-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="39658-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="39658-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="39658-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="39658-105">\<bindings></span></span>  
<span data-ttu-id="39658-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="39658-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="39658-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="39658-107">\<binding></span></span>  
<span data-ttu-id="39658-108">\<security></span><span class="sxs-lookup"><span data-stu-id="39658-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39658-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39658-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39658-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39658-110">Attributes and Elements</span></span>  
 <span data-ttu-id="39658-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39658-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39658-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="39658-112">Attributes</span></span>  
  
|<span data-ttu-id="39658-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="39658-113">Attribute</span></span>|<span data-ttu-id="39658-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39658-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39658-115">Modalità</span><span class="sxs-lookup"><span data-stu-id="39658-115">Mode</span></span>|<span data-ttu-id="39658-116">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="39658-116">Optional.</span></span> <span data-ttu-id="39658-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="39658-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="39658-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="39658-118">The default value is `Message`.</span></span> <span data-ttu-id="39658-119">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="39658-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="39658-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="39658-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="39658-121">Value</span><span class="sxs-lookup"><span data-stu-id="39658-121">Value</span></span>|<span data-ttu-id="39658-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39658-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39658-123">Nessuna</span><span class="sxs-lookup"><span data-stu-id="39658-123">None</span></span>|<span data-ttu-id="39658-124">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="39658-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="39658-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="39658-125">Message</span></span>|<span data-ttu-id="39658-126">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="39658-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="39658-127">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="39658-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="39658-128">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="39658-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="39658-129">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="39658-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="39658-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="39658-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="39658-131">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="39658-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="39658-132">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="39658-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="39658-133">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="39658-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39658-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39658-134">Child Elements</span></span>  
  
|<span data-ttu-id="39658-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="39658-135">Element</span></span>|<span data-ttu-id="39658-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39658-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39658-137">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="39658-137">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="39658-138">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="39658-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="39658-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="39658-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39658-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39658-140">Parent Elements</span></span>  
  
|<span data-ttu-id="39658-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="39658-141">Element</span></span>|<span data-ttu-id="39658-142">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="39658-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39658-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="39658-143">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="39658-144">Definisce tutte le funzionalità di associazione del [ \<> WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="39658-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39658-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39658-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="39658-146">Procedura: Creare un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="39658-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="39658-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="39658-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="39658-148">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="39658-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="39658-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="39658-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="39658-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="39658-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="39658-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="39658-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="39658-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="39658-152">\<binding></span></span>](../../../misc/binding.md)
