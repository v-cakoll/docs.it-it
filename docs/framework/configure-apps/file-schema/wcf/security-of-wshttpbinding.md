---
title: '&lt;security&gt; di &lt;wsHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 30f44ad6ce7219ddd874108e62111ff947d7aa0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a><span data-ttu-id="03a7c-102">&lt;security&gt; di &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="03a7c-102">&lt;security&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="03a7c-103">Rappresenta le funzionalità di sicurezza di [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="03a7c-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="03a7c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="03a7c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="03a7c-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="03a7c-105">\<bindings></span></span>  
<span data-ttu-id="03a7c-106">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="03a7c-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="03a7c-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="03a7c-107">\<binding></span></span>  
<span data-ttu-id="03a7c-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="03a7c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a7c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03a7c-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03a7c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="03a7c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="03a7c-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="03a7c-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03a7c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="03a7c-112">Attributes</span></span>  
  
|<span data-ttu-id="03a7c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="03a7c-113">Attribute</span></span>|<span data-ttu-id="03a7c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03a7c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03a7c-115">modalità</span><span class="sxs-lookup"><span data-stu-id="03a7c-115">mode</span></span>|<span data-ttu-id="03a7c-116">-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="03a7c-116">-   Optional.</span></span> <span data-ttu-id="03a7c-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="03a7c-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="03a7c-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="03a7c-118">The default is `Message`.</span></span><br /><span data-ttu-id="03a7c-119">-L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="03a7c-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="03a7c-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="03a7c-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="03a7c-121">Valore</span><span class="sxs-lookup"><span data-stu-id="03a7c-121">Value</span></span>|<span data-ttu-id="03a7c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03a7c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="03a7c-123">None</span><span class="sxs-lookup"><span data-stu-id="03a7c-123">None</span></span>|<span data-ttu-id="03a7c-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="03a7c-124">Security is disabled.</span></span>|  
|<span data-ttu-id="03a7c-125">Trasporto</span><span class="sxs-lookup"><span data-stu-id="03a7c-125">Transport</span></span>|<span data-ttu-id="03a7c-126">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="03a7c-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="03a7c-127">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="03a7c-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="03a7c-128">Il messaggio è interamente protetto usando HTTPS e viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="03a7c-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="03a7c-129">L'autenticazione client è controllata tramite l'attributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="03a7c-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="03a7c-130">del [ \<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="03a7c-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="03a7c-131">Messaggio</span><span class="sxs-lookup"><span data-stu-id="03a7c-131">Message</span></span>|<span data-ttu-id="03a7c-132">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="03a7c-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="03a7c-133">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="03a7c-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="03a7c-134">Questa modalità offre varie funzionalità, ad esempio la disponibilità o meno delle credenziali del servizio per il client fuori banda, la suite di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà Security.Message.</span><span class="sxs-lookup"><span data-stu-id="03a7c-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="03a7c-135">L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="03a7c-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="03a7c-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="03a7c-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="03a7c-137">In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="03a7c-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="03a7c-138">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="03a7c-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03a7c-139">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="03a7c-139">Child Elements</span></span>  
  
|<span data-ttu-id="03a7c-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="03a7c-140">Element</span></span>|<span data-ttu-id="03a7c-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03a7c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03a7c-142">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="03a7c-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="03a7c-143">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="03a7c-143">Defines the transport security settings.</span></span> <span data-ttu-id="03a7c-144">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="03a7c-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="03a7c-145">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="03a7c-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="03a7c-146">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="03a7c-146">Defines the security settings for the message.</span></span> <span data-ttu-id="03a7c-147">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="03a7c-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03a7c-148">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="03a7c-148">Parent Elements</span></span>  
  
|<span data-ttu-id="03a7c-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="03a7c-149">Element</span></span>|<span data-ttu-id="03a7c-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03a7c-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03a7c-151">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="03a7c-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="03a7c-152">Associazione protetta per applicazioni di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="03a7c-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03a7c-153">Note</span><span class="sxs-lookup"><span data-stu-id="03a7c-153">Remarks</span></span>  
 <span data-ttu-id="03a7c-154">La classe WSHttpBinding è progettata per essere interoperabile con i servizi che implementano le specifiche WS-*.</span><span class="sxs-lookup"><span data-stu-id="03a7c-154">The WSHttpBinding class is designed for interoperation with services that implement WS-* specifications.</span></span> <span data-ttu-id="03a7c-155">La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.</span><span class="sxs-lookup"><span data-stu-id="03a7c-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a7c-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03a7c-156">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 [<span data-ttu-id="03a7c-157">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="03a7c-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="03a7c-158">Associazioni</span><span class="sxs-lookup"><span data-stu-id="03a7c-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="03a7c-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="03a7c-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="03a7c-160">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="03a7c-160">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="03a7c-161">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="03a7c-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
