---
title: Elemento &lt;security&gt; di &lt;ws2007FederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
author: BrucePerlerMS
ms.openlocfilehash: 6451d4c3cdcf649ae959012826eb433732d87c54
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172654"
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="401bc-102">Elemento &lt;security&gt; di &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="401bc-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="401bc-103">Definisce le impostazioni di sicurezza del [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="401bc-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="401bc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="401bc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="401bc-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="401bc-105">\<bindings></span></span>  
<span data-ttu-id="401bc-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="401bc-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="401bc-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="401bc-107">\<binding></span></span>  
<span data-ttu-id="401bc-108">\<security></span><span class="sxs-lookup"><span data-stu-id="401bc-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401bc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="401bc-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
    <binding >  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                defaultProtectionLevel="none/sign/EncryptAndSign"   
                issuedTokenType="string"   
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="401bc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="401bc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="401bc-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="401bc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="401bc-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="401bc-112">Attributes</span></span>  
  
|<span data-ttu-id="401bc-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="401bc-113">Attribute</span></span>|<span data-ttu-id="401bc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="401bc-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="401bc-115">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="401bc-115">Optional.</span></span> <span data-ttu-id="401bc-116">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="401bc-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="401bc-117">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="401bc-117">The default value is `Message`.</span></span> <span data-ttu-id="401bc-118">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="401bc-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="401bc-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="401bc-119">mode Attribute</span></span>  
  
|<span data-ttu-id="401bc-120">Valore</span><span class="sxs-lookup"><span data-stu-id="401bc-120">Value</span></span>|<span data-ttu-id="401bc-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="401bc-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="401bc-122">None</span><span class="sxs-lookup"><span data-stu-id="401bc-122">None</span></span>|<span data-ttu-id="401bc-123">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="401bc-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="401bc-124">Messaggio</span><span class="sxs-lookup"><span data-stu-id="401bc-124">Message</span></span>|<span data-ttu-id="401bc-125">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="401bc-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="401bc-126">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="401bc-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="401bc-127">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="401bc-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="401bc-128">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="401bc-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="401bc-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="401bc-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="401bc-130">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="401bc-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="401bc-131">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="401bc-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="401bc-132">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="401bc-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="401bc-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="401bc-133">Child Elements</span></span>  
  
|<span data-ttu-id="401bc-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="401bc-134">Element</span></span>|<span data-ttu-id="401bc-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="401bc-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="401bc-136">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="401bc-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="401bc-137">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="401bc-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="401bc-138">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="401bc-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="401bc-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="401bc-139">Parent Elements</span></span>  
  
|<span data-ttu-id="401bc-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="401bc-140">Element</span></span>|<span data-ttu-id="401bc-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="401bc-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="401bc-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="401bc-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="401bc-143">Definisce tutte le funzionalità di associazione del [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="401bc-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="401bc-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="401bc-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="401bc-145">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="401bc-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="401bc-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="401bc-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="401bc-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="401bc-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="401bc-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="401bc-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="401bc-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="401bc-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="401bc-150">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="401bc-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="401bc-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="401bc-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
