---
title: <security> di <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: f1e166bec2254ed6d2c306eaccfa13e9fba1d70d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670579"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="de80b-102">\<sicurezza > di \<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="de80b-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="de80b-103">Definisce le funzionalità di sicurezza del [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="de80b-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="de80b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="de80b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="de80b-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="de80b-105">\<bindings></span></span>  
<span data-ttu-id="de80b-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="de80b-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="de80b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="de80b-107">\<binding></span></span>  
<span data-ttu-id="de80b-108">\<security></span><span class="sxs-lookup"><span data-stu-id="de80b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de80b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de80b-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de80b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="de80b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="de80b-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="de80b-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de80b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="de80b-112">Attributes</span></span>  
  
|<span data-ttu-id="de80b-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="de80b-113">Attribute</span></span>|<span data-ttu-id="de80b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de80b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de80b-115">modalità</span><span class="sxs-lookup"><span data-stu-id="de80b-115">mode</span></span>|<span data-ttu-id="de80b-116">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="de80b-116">Optional.</span></span> <span data-ttu-id="de80b-117">Specifica il tipo di sicurezza usata.</span><span class="sxs-lookup"><span data-stu-id="de80b-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="de80b-118">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="de80b-118">The default is `None`.</span></span> <span data-ttu-id="de80b-119">L'attributo è di tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="de80b-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="de80b-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="de80b-120">mode Attribute</span></span>  
  
|<span data-ttu-id="de80b-121">Value</span><span class="sxs-lookup"><span data-stu-id="de80b-121">Value</span></span>|<span data-ttu-id="de80b-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de80b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de80b-123">nessuno</span><span class="sxs-lookup"><span data-stu-id="de80b-123">None</span></span>|<span data-ttu-id="de80b-124">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="de80b-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="de80b-125">Trasporto</span><span class="sxs-lookup"><span data-stu-id="de80b-125">Transport</span></span>|<span data-ttu-id="de80b-126">La sicurezza è fornita mediante il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="de80b-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="de80b-127">I messaggi SOAP sono protetti mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="de80b-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="de80b-128">Il servizio viene autenticato sul client mediante il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="de80b-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="de80b-129">Il client viene autenticato mediante il ClientCredentialType  fornito.</span><span class="sxs-lookup"><span data-stu-id="de80b-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="de80b-130">Vedere le [ \<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="de80b-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="de80b-131">Messaggio</span><span class="sxs-lookup"><span data-stu-id="de80b-131">Message</span></span>|<span data-ttu-id="de80b-132">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="de80b-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="de80b-133">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="de80b-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="de80b-134">Per questa associazione, il sistema richiede che il certificato server sia fornito al client fuori banda.</span><span class="sxs-lookup"><span data-stu-id="de80b-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="de80b-135">L'unico valore `ClientCredentialType` valido per questa associazione è `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="de80b-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="de80b-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="de80b-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="de80b-137">Integrità, riservatezza e autenticazione server sono fornite dalla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="de80b-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="de80b-138">L'autenticazione del client è fornita per mezzo della sicurezza del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="de80b-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="de80b-139">Questa modalità è appropriata quando l'utente esegue l'autenticazione usando nome utente/password in presenza di una distribuzione HTTP esistente per la sicurezza del trasferimento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="de80b-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="de80b-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="de80b-140">TransportCredentialOnly</span></span>|<span data-ttu-id="de80b-141">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="de80b-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="de80b-142">Fornisce autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="de80b-142">It provides http-based client authentication.</span></span> <span data-ttu-id="de80b-143">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="de80b-143">This mode should be used with caution.</span></span> <span data-ttu-id="de80b-144">Deve essere utilizzata nei ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e solo l'autenticazione client viene fornito dall'infrastruttura WCF.</span><span class="sxs-lookup"><span data-stu-id="de80b-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de80b-145">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="de80b-145">Child Elements</span></span>  
  
|<span data-ttu-id="de80b-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="de80b-146">Element</span></span>|<span data-ttu-id="de80b-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de80b-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de80b-148">\<transport></span><span class="sxs-lookup"><span data-stu-id="de80b-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="de80b-149">Definisce le impostazioni di sicurezza del trasporto per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="de80b-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="de80b-150">L'elemento corrisponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="de80b-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="de80b-151">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="de80b-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="de80b-152">Definisce le impostazioni di sicurezza del messaggio per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="de80b-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="de80b-153">L'elemento corrisponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="de80b-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de80b-154">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="de80b-154">Parent Elements</span></span>  
  
|<span data-ttu-id="de80b-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="de80b-155">Element</span></span>|<span data-ttu-id="de80b-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de80b-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de80b-157">binding</span><span class="sxs-lookup"><span data-stu-id="de80b-157">binding</span></span>|<span data-ttu-id="de80b-158">L'elemento di associazione del [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="de80b-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de80b-159">Note</span><span class="sxs-lookup"><span data-stu-id="de80b-159">Remarks</span></span>  
 <span data-ttu-id="de80b-160">Per impostazione predefinita, il messaggio SOAP non è protetto e il client non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="de80b-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="de80b-161">Questo elemento consente di configurare impostazioni di sicurezza aggiuntive per l'elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="de80b-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de80b-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de80b-162">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="de80b-163">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="de80b-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="de80b-164">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="de80b-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="de80b-165">Associazioni</span><span class="sxs-lookup"><span data-stu-id="de80b-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="de80b-166">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="de80b-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="de80b-167">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="de80b-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="de80b-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="de80b-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
