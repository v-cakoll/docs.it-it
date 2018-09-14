---
title: '&lt;security&gt; di &lt;netHttpBinding'
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 6357593be17c2d008204598d51610fa3dbf77c27
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45527473"
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a><span data-ttu-id="fd0f9-102">&lt;security&gt; di &lt;netHttpBinding</span><span class="sxs-lookup"><span data-stu-id="fd0f9-102">&lt;security&gt; of &lt;netHttpBinding</span></span>
<span data-ttu-id="fd0f9-103">Definisce le funzionalità di sicurezza del [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fd0f9-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="fd0f9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd0f9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd0f9-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="fd0f9-105">\<bindings></span></span>  
<span data-ttu-id="fd0f9-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fd0f9-106">\<netHttpBinding></span></span>  
<span data-ttu-id="fd0f9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="fd0f9-107">\<binding></span></span>  
<span data-ttu-id="fd0f9-108">\<security></span><span class="sxs-lookup"><span data-stu-id="fd0f9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0f9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd0f9-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd0f9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fd0f9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd0f9-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd0f9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fd0f9-112">Attributes</span></span>  
  
|<span data-ttu-id="fd0f9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="fd0f9-113">Attribute</span></span>|<span data-ttu-id="fd0f9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd0f9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd0f9-115">modalità</span><span class="sxs-lookup"><span data-stu-id="fd0f9-115">mode</span></span>|<span data-ttu-id="fd0f9-116">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-116">Optional.</span></span> <span data-ttu-id="fd0f9-117">Specifica il tipo di sicurezza usata.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="fd0f9-118">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-118">The default is `None`.</span></span> <span data-ttu-id="fd0f9-119">Questo attributo è di tipo <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-119">This attribute is of type <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> -->`System.ServiceModel.NetHttpSecurityMode`.</span></span>|
  
## <a name="mode-attribute"></a><span data-ttu-id="fd0f9-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="fd0f9-120">mode Attribute</span></span>  
  
|<span data-ttu-id="fd0f9-121">Valore</span><span class="sxs-lookup"><span data-stu-id="fd0f9-121">Value</span></span>|<span data-ttu-id="fd0f9-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd0f9-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd0f9-123">nessuno</span><span class="sxs-lookup"><span data-stu-id="fd0f9-123">None</span></span>|<span data-ttu-id="fd0f9-124">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="fd0f9-125">Trasporto</span><span class="sxs-lookup"><span data-stu-id="fd0f9-125">Transport</span></span>|<span data-ttu-id="fd0f9-126">La sicurezza è fornita mediante il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="fd0f9-127">I messaggi SOAP sono protetti mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="fd0f9-128">Il servizio viene autenticato sul client mediante il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="fd0f9-129">Il client viene autenticato mediante il ClientCredentialType  fornito.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|  
|<span data-ttu-id="fd0f9-130">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fd0f9-130">Message</span></span>|<span data-ttu-id="fd0f9-131">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="fd0f9-132">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="fd0f9-133">Per questa associazione, il sistema richiede che il certificato server sia fornito al client fuori banda.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="fd0f9-134">L'unico valore `ClientCredentialType` valido per questa associazione è `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="fd0f9-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="fd0f9-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="fd0f9-136">Integrità, riservatezza e autenticazione server sono fornite dalla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="fd0f9-137">L'autenticazione del client è fornita per mezzo della sicurezza del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="fd0f9-138">Questa modalità è appropriata quando l'utente esegue l'autenticazione usando nome utente/password in presenza di una distribuzione HTTP esistente per la sicurezza del trasferimento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="fd0f9-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="fd0f9-139">TransportCredentialOnly</span></span>|<span data-ttu-id="fd0f9-140">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="fd0f9-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="fd0f9-141">Fornisce autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-141">It provides http-based client authentication.</span></span> <span data-ttu-id="fd0f9-142">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-142">This mode should be used with caution.</span></span> <span data-ttu-id="fd0f9-143">Deve essere utilizzata nei ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e solo l'autenticazione client viene fornito dall'infrastruttura WCF.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd0f9-144">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fd0f9-144">Child Elements</span></span>  
  
|<span data-ttu-id="fd0f9-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd0f9-145">Element</span></span>|<span data-ttu-id="fd0f9-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd0f9-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd0f9-147">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="fd0f9-147">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|<span data-ttu-id="fd0f9-148">Definisce le impostazioni di sicurezza del trasporto per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="fd0f9-149">L'elemento corrisponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="fd0f9-150">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="fd0f9-150">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|<span data-ttu-id="fd0f9-151">Definisce le impostazioni di sicurezza del messaggio per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="fd0f9-152">Questo elemento corrisponde a <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-152">This element corresponds to <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd0f9-153">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fd0f9-153">Parent Elements</span></span>  
  
|<span data-ttu-id="fd0f9-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd0f9-154">Element</span></span>|<span data-ttu-id="fd0f9-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd0f9-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd0f9-156">binding</span><span class="sxs-lookup"><span data-stu-id="fd0f9-156">binding</span></span>|<span data-ttu-id="fd0f9-157">L'elemento di associazione del [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fd0f9-157">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0f9-158">Note</span><span class="sxs-lookup"><span data-stu-id="fd0f9-158">Remarks</span></span>  
 <span data-ttu-id="fd0f9-159">Per impostazione predefinita, il messaggio SOAP non è protetto e il client non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="fd0f9-160">Questo elemento consente di configurare impostazioni di sicurezza aggiuntive per l'elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="fd0f9-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0f9-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd0f9-161">See Also</span></span>  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>    
 [<span data-ttu-id="fd0f9-162">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="fd0f9-162">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fd0f9-163">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="fd0f9-163">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="fd0f9-164">Associazioni</span><span class="sxs-lookup"><span data-stu-id="fd0f9-164">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fd0f9-165">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="fd0f9-165">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fd0f9-166">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fd0f9-166">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fd0f9-167">\<binding></span><span class="sxs-lookup"><span data-stu-id="fd0f9-167">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
