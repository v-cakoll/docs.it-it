---
title: '&lt;security&gt; di &lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
author: BrucePerlerMS
ms.openlocfilehash: 2e7ec6b73ec56aa679040e8d3ee50843c9286183
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847776"
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="774db-102">&lt;security&gt; di &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="774db-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="774db-103">Definisce le impostazioni di sicurezza del [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="774db-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="774db-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="774db-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="774db-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="774db-105">\<bindings></span></span>  
<span data-ttu-id="774db-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="774db-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="774db-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="774db-107">\<binding></span></span>  
<span data-ttu-id="774db-108">\<security></span><span class="sxs-lookup"><span data-stu-id="774db-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="774db-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="774db-109">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
    <binding >  
       <security mode="None/Message/TransportWithMessageCredential">  
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
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="774db-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="774db-110">Attributes and Elements</span></span>  
 <span data-ttu-id="774db-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="774db-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="774db-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="774db-112">Attributes</span></span>  
  
|<span data-ttu-id="774db-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="774db-113">Attribute</span></span>|<span data-ttu-id="774db-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="774db-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="774db-115">Modalità</span><span class="sxs-lookup"><span data-stu-id="774db-115">Mode</span></span>|<span data-ttu-id="774db-116">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="774db-116">Optional.</span></span> <span data-ttu-id="774db-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="774db-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="774db-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="774db-118">The default value is `Message`.</span></span> <span data-ttu-id="774db-119">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="774db-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="774db-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="774db-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="774db-121">Valore</span><span class="sxs-lookup"><span data-stu-id="774db-121">Value</span></span>|<span data-ttu-id="774db-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="774db-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="774db-123">None</span><span class="sxs-lookup"><span data-stu-id="774db-123">None</span></span>|<span data-ttu-id="774db-124">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="774db-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="774db-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="774db-125">Message</span></span>|<span data-ttu-id="774db-126">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="774db-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="774db-127">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="774db-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="774db-128">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="774db-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="774db-129">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="774db-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="774db-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="774db-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="774db-131">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="774db-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="774db-132">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="774db-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="774db-133">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="774db-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="774db-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="774db-134">Child Elements</span></span>  
  
|<span data-ttu-id="774db-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="774db-135">Element</span></span>|<span data-ttu-id="774db-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="774db-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="774db-137">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="774db-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="774db-138">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="774db-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="774db-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="774db-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="774db-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="774db-140">Parent Elements</span></span>  
  
|<span data-ttu-id="774db-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="774db-141">Element</span></span>|<span data-ttu-id="774db-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="774db-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="774db-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="774db-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="774db-144">Definisce tutte le funzionalità di associazione del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="774db-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="774db-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="774db-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="774db-146">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="774db-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="774db-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="774db-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="774db-148">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="774db-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="774db-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="774db-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="774db-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="774db-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="774db-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="774db-151">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="774db-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="774db-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
