---
title: <security> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738577"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="8497f-102">\<> di sicurezza di \<WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8497f-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="8497f-103">Rappresenta le funzionalità di sicurezza di [\<wshttpbinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8497f-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="8497f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8497f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8497f-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8497f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8497f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="8497f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="8497f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**wsHttpBinding**](wshttpbinding.md)\<</span><span class="sxs-lookup"><span data-stu-id="8497f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\</span></span>
<span data-ttu-id="8497f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="8497f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8497f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="8497f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8497f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8497f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8497f-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8497f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8497f-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8497f-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8497f-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8497f-113">Attributes</span></span>  
  
|<span data-ttu-id="8497f-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="8497f-114">Attribute</span></span>|<span data-ttu-id="8497f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8497f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8497f-116">modalità</span><span class="sxs-lookup"><span data-stu-id="8497f-116">mode</span></span>|<span data-ttu-id="8497f-117">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="8497f-117">-   Optional.</span></span> <span data-ttu-id="8497f-118">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="8497f-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="8497f-119">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="8497f-119">The default is `Message`.</span></span><br /><span data-ttu-id="8497f-120">: Questo attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8497f-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="8497f-121">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="8497f-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="8497f-122">Value</span><span class="sxs-lookup"><span data-stu-id="8497f-122">Value</span></span>|<span data-ttu-id="8497f-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8497f-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8497f-124">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8497f-124">None</span></span>|<span data-ttu-id="8497f-125">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="8497f-125">Security is disabled.</span></span>|  
|<span data-ttu-id="8497f-126">Trasporto</span><span class="sxs-lookup"><span data-stu-id="8497f-126">Transport</span></span>|<span data-ttu-id="8497f-127">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8497f-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="8497f-128">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="8497f-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="8497f-129">Il messaggio è interamente protetto usando HTTPS e viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="8497f-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="8497f-130">L'autenticazione client è controllata tramite l'attributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="8497f-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="8497f-131">del [> di trasporto\<](transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8497f-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="8497f-132">Messaggio</span><span class="sxs-lookup"><span data-stu-id="8497f-132">Message</span></span>|<span data-ttu-id="8497f-133">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="8497f-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="8497f-134">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="8497f-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="8497f-135">Questa modalità offre varie funzionalità, ad esempio la disponibilità o meno delle credenziali del servizio per il client fuori banda, il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà Security.Message.</span><span class="sxs-lookup"><span data-stu-id="8497f-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="8497f-136">L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="8497f-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="8497f-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="8497f-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="8497f-138">In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="8497f-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="8497f-139">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="8497f-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8497f-140">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8497f-140">Child Elements</span></span>  
  
|<span data-ttu-id="8497f-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="8497f-141">Element</span></span>|<span data-ttu-id="8497f-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8497f-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8497f-143">> trasporto \<</span><span class="sxs-lookup"><span data-stu-id="8497f-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="8497f-144">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="8497f-144">Defines the transport security settings.</span></span> <span data-ttu-id="8497f-145">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8497f-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="8497f-146">\<message ></span><span class="sxs-lookup"><span data-stu-id="8497f-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="8497f-147">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="8497f-147">Defines the security settings for the message.</span></span> <span data-ttu-id="8497f-148">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="8497f-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8497f-149">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8497f-149">Parent Elements</span></span>  
  
|<span data-ttu-id="8497f-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="8497f-150">Element</span></span>|<span data-ttu-id="8497f-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8497f-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8497f-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8497f-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="8497f-153">Associazione protetta per applicazioni di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="8497f-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8497f-154">Note</span><span class="sxs-lookup"><span data-stu-id="8497f-154">Remarks</span></span>  
 <span data-ttu-id="8497f-155">La classe WSHttpBinding è progettata per essere interoperabile con i servizi che implementano le specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="8497f-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="8497f-156">La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8497f-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8497f-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8497f-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="8497f-158">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="8497f-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8497f-159">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8497f-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8497f-160">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="8497f-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8497f-161">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="8497f-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8497f-162">\<binding ></span><span class="sxs-lookup"><span data-stu-id="8497f-162">\<binding></span></span>](bindings.md)
