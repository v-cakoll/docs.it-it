---
title: Elemento &lt;security&gt; di &lt;ws2007FederationHttpBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 27fedcd8ae7501f484de0aa2f21af8c701990285
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="cde63-102">Elemento &lt;security&gt; di &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="cde63-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="cde63-103">Definisce le impostazioni di sicurezza di [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="cde63-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="cde63-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cde63-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cde63-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="cde63-105">\<bindings></span></span>  
<span data-ttu-id="cde63-106">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cde63-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="cde63-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="cde63-107">\<binding></span></span>  
<span data-ttu-id="cde63-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="cde63-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cde63-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cde63-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cde63-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cde63-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cde63-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cde63-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cde63-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cde63-112">Attributes</span></span>  
  
|<span data-ttu-id="cde63-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="cde63-113">Attribute</span></span>|<span data-ttu-id="cde63-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cde63-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="cde63-115">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cde63-115">Optional.</span></span> <span data-ttu-id="cde63-116">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="cde63-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="cde63-117">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="cde63-117">The default value is `Message`.</span></span> <span data-ttu-id="cde63-118">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cde63-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="cde63-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="cde63-119">mode Attribute</span></span>  
  
|<span data-ttu-id="cde63-120">Valore</span><span class="sxs-lookup"><span data-stu-id="cde63-120">Value</span></span>|<span data-ttu-id="cde63-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cde63-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cde63-122">None</span><span class="sxs-lookup"><span data-stu-id="cde63-122">None</span></span>|<span data-ttu-id="cde63-123">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="cde63-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="cde63-124">Messaggio</span><span class="sxs-lookup"><span data-stu-id="cde63-124">Message</span></span>|<span data-ttu-id="cde63-125">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="cde63-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="cde63-126">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="cde63-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="cde63-127">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="cde63-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="cde63-128">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cde63-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="cde63-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="cde63-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="cde63-130">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cde63-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="cde63-131">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="cde63-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="cde63-132">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cde63-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cde63-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cde63-133">Child Elements</span></span>  
  
|<span data-ttu-id="cde63-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="cde63-134">Element</span></span>|<span data-ttu-id="cde63-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cde63-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cde63-136">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="cde63-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="cde63-137">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="cde63-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="cde63-138">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="cde63-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cde63-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cde63-139">Parent Elements</span></span>  
  
|<span data-ttu-id="cde63-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="cde63-140">Element</span></span>|<span data-ttu-id="cde63-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cde63-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cde63-142">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="cde63-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cde63-143">Definisce tutte le funzionalità di associazione di [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cde63-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cde63-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cde63-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="cde63-145">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cde63-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="cde63-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="cde63-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="cde63-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="cde63-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="cde63-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="cde63-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cde63-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="cde63-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="cde63-150">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="cde63-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="cde63-151">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="cde63-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
