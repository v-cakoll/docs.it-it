---
title: <security> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: e627a63221d0013c89495d7ff81e02047a03df89
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936514"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="b6a18-102">\<> di sicurezza \<di WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b6a18-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="b6a18-103">Rappresenta le funzionalità di sicurezza di [ \<WSHttpBinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b6a18-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="b6a18-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b6a18-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b6a18-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="b6a18-105">\<bindings></span></span>  
<span data-ttu-id="b6a18-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b6a18-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="b6a18-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b6a18-107">\<binding></span></span>  
<span data-ttu-id="b6a18-108">\<security></span><span class="sxs-lookup"><span data-stu-id="b6a18-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6a18-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6a18-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6a18-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6a18-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b6a18-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6a18-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6a18-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6a18-112">Attributes</span></span>  
  
|<span data-ttu-id="b6a18-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b6a18-113">Attribute</span></span>|<span data-ttu-id="b6a18-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6a18-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6a18-115">modalità</span><span class="sxs-lookup"><span data-stu-id="b6a18-115">mode</span></span>|<span data-ttu-id="b6a18-116">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="b6a18-116">-   Optional.</span></span> <span data-ttu-id="b6a18-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="b6a18-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b6a18-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="b6a18-118">The default is `Message`.</span></span><br /><span data-ttu-id="b6a18-119">: Questo attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b6a18-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b6a18-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="b6a18-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="b6a18-121">Value</span><span class="sxs-lookup"><span data-stu-id="b6a18-121">Value</span></span>|<span data-ttu-id="b6a18-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6a18-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6a18-123">Nessuna</span><span class="sxs-lookup"><span data-stu-id="b6a18-123">None</span></span>|<span data-ttu-id="b6a18-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="b6a18-124">Security is disabled.</span></span>|  
|<span data-ttu-id="b6a18-125">Trasporto</span><span class="sxs-lookup"><span data-stu-id="b6a18-125">Transport</span></span>|<span data-ttu-id="b6a18-126">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6a18-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="b6a18-127">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="b6a18-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="b6a18-128">Il messaggio è interamente protetto usando HTTPS e viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="b6a18-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="b6a18-129">L'autenticazione client è controllata tramite l'attributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="b6a18-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="b6a18-130">del > di [ trasporto.\<](transport-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b6a18-130">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="b6a18-131">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b6a18-131">Message</span></span>|<span data-ttu-id="b6a18-132">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="b6a18-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="b6a18-133">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="b6a18-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="b6a18-134">Questa modalità offre varie funzionalità, ad esempio la disponibilità o meno delle credenziali del servizio per il client fuori banda, il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà Security.Message.</span><span class="sxs-lookup"><span data-stu-id="b6a18-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="b6a18-135">L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="b6a18-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="b6a18-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="b6a18-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="b6a18-137">In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="b6a18-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="b6a18-138">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="b6a18-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6a18-139">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6a18-139">Child Elements</span></span>  
  
|<span data-ttu-id="b6a18-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6a18-140">Element</span></span>|<span data-ttu-id="b6a18-141">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b6a18-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6a18-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="b6a18-142">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="b6a18-143">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="b6a18-143">Defines the transport security settings.</span></span> <span data-ttu-id="b6a18-144">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b6a18-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="b6a18-145">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="b6a18-145">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="b6a18-146">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6a18-146">Defines the security settings for the message.</span></span> <span data-ttu-id="b6a18-147">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="b6a18-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6a18-148">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6a18-148">Parent Elements</span></span>  
  
|<span data-ttu-id="b6a18-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6a18-149">Element</span></span>|<span data-ttu-id="b6a18-150">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b6a18-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6a18-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b6a18-151">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="b6a18-152">Associazione protetta per applicazioni di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6a18-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6a18-153">Note</span><span class="sxs-lookup"><span data-stu-id="b6a18-153">Remarks</span></span>  
 <span data-ttu-id="b6a18-154">La classe WSHttpBinding è progettata per essere interoperabile con i servizi che implementano le specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="b6a18-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="b6a18-155">La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6a18-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a18-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6a18-156">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="b6a18-157">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="b6a18-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b6a18-158">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b6a18-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b6a18-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="b6a18-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b6a18-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="b6a18-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b6a18-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="b6a18-161">\<binding></span></span>](../../../misc/binding.md)
