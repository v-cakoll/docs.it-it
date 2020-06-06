---
title: <security> di <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: ea029444cee331a235c7a2fc140b4321d7530063
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736322"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="6c1af-102">\<security> di \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6c1af-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="6c1af-103">Definisce le impostazioni di sicurezza dell'oggetto [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6c1af-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="6c1af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c1af-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c1af-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6c1af-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6c1af-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6c1af-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c1af-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6c1af-107">Attributes</span></span>  
  
|<span data-ttu-id="6c1af-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="6c1af-108">Attribute</span></span>|<span data-ttu-id="6c1af-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c1af-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c1af-110">Mode</span><span class="sxs-lookup"><span data-stu-id="6c1af-110">Mode</span></span>|<span data-ttu-id="6c1af-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6c1af-111">Optional.</span></span> <span data-ttu-id="6c1af-112">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="6c1af-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="6c1af-113">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="6c1af-113">The default value is `Message`.</span></span> <span data-ttu-id="6c1af-114">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6c1af-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="6c1af-115">Attributo Mode</span><span class="sxs-lookup"><span data-stu-id="6c1af-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="6c1af-116">Valore</span><span class="sxs-lookup"><span data-stu-id="6c1af-116">Value</span></span>|<span data-ttu-id="6c1af-117">Description</span><span class="sxs-lookup"><span data-stu-id="6c1af-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c1af-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="6c1af-118">None</span></span>|<span data-ttu-id="6c1af-119">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6c1af-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="6c1af-120">Message</span><span class="sxs-lookup"><span data-stu-id="6c1af-120">Message</span></span>|<span data-ttu-id="6c1af-121">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="6c1af-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="6c1af-122">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="6c1af-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="6c1af-123">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="6c1af-123">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="6c1af-124">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6c1af-124">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="6c1af-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="6c1af-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="6c1af-126">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6c1af-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="6c1af-127">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="6c1af-127">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="6c1af-128">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6c1af-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c1af-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6c1af-129">Child Elements</span></span>  
  
|<span data-ttu-id="6c1af-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c1af-130">Element</span></span>|<span data-ttu-id="6c1af-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c1af-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="6c1af-132">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="6c1af-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="6c1af-133">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="6c1af-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c1af-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6c1af-134">Parent Elements</span></span>  
  
|<span data-ttu-id="6c1af-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c1af-135">Element</span></span>|<span data-ttu-id="6c1af-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c1af-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="6c1af-137">Definisce tutte le funzionalità di associazione di [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6c1af-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c1af-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6c1af-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="6c1af-139">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="6c1af-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="6c1af-140">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="6c1af-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6c1af-141">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="6c1af-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="6c1af-142">Binding</span><span class="sxs-lookup"><span data-stu-id="6c1af-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6c1af-143">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6c1af-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6c1af-144">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="6c1af-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
