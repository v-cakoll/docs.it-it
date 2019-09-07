---
title: <security> di <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 00a933892376c2dc9771752beaf76d4994554968
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399886"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="edaeb-102">\<> di sicurezza \<di BasicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="edaeb-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="edaeb-103">Definisce le funzionalità di sicurezza del [ \<> BasicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="edaeb-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="edaeb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="edaeb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="edaeb-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="edaeb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="edaeb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="edaeb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="edaeb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BasicHttpBinding >** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="edaeb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="edaeb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="edaeb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="edaeb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="edaeb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edaeb-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edaeb-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edaeb-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="edaeb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="edaeb-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="edaeb-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edaeb-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="edaeb-113">Attributes</span></span>  
  
|<span data-ttu-id="edaeb-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="edaeb-114">Attribute</span></span>|<span data-ttu-id="edaeb-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="edaeb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="edaeb-116">modalità</span><span class="sxs-lookup"><span data-stu-id="edaeb-116">mode</span></span>|<span data-ttu-id="edaeb-117">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="edaeb-117">Optional.</span></span> <span data-ttu-id="edaeb-118">Specifica il tipo di sicurezza usata.</span><span class="sxs-lookup"><span data-stu-id="edaeb-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="edaeb-119">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="edaeb-119">The default is `None`.</span></span> <span data-ttu-id="edaeb-120">L'attributo è di tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="edaeb-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="edaeb-121">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="edaeb-121">mode Attribute</span></span>  
  
|<span data-ttu-id="edaeb-122">Valore</span><span class="sxs-lookup"><span data-stu-id="edaeb-122">Value</span></span>|<span data-ttu-id="edaeb-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edaeb-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="edaeb-124">Nessuna</span><span class="sxs-lookup"><span data-stu-id="edaeb-124">None</span></span>|<span data-ttu-id="edaeb-125">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="edaeb-125">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="edaeb-126">Trasporto</span><span class="sxs-lookup"><span data-stu-id="edaeb-126">Transport</span></span>|<span data-ttu-id="edaeb-127">La sicurezza è fornita mediante il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="edaeb-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="edaeb-128">I messaggi SOAP vengono protetti utilizzando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="edaeb-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="edaeb-129">Il servizio viene autenticato sul client mediante il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="edaeb-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="edaeb-130">Il client viene autenticato mediante il ClientCredentialType  fornito.</span><span class="sxs-lookup"><span data-stu-id="edaeb-130">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="edaeb-131">Vedere il [ \<> di trasporto](transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="edaeb-131">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="edaeb-132">Messaggio</span><span class="sxs-lookup"><span data-stu-id="edaeb-132">Message</span></span>|<span data-ttu-id="edaeb-133">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="edaeb-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="edaeb-134">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="edaeb-134">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="edaeb-135">Per questa associazione, il sistema richiede che il certificato server sia fornito al client fuori banda.</span><span class="sxs-lookup"><span data-stu-id="edaeb-135">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="edaeb-136">L'unico valore `ClientCredentialType` valido per questa associazione è `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="edaeb-136">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="edaeb-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="edaeb-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="edaeb-138">Integrità, riservatezza e autenticazione server sono fornite dalla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="edaeb-138">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="edaeb-139">L'autenticazione del client è fornita per mezzo della sicurezza del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="edaeb-139">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="edaeb-140">Questa modalità è appropriata quando l'utente esegue l'autenticazione usando nome utente/password in presenza di una distribuzione HTTP esistente per la sicurezza del trasferimento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="edaeb-140">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="edaeb-141">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="edaeb-141">TransportCredentialOnly</span></span>|<span data-ttu-id="edaeb-142">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="edaeb-142">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="edaeb-143">Fornisce autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="edaeb-143">It provides http-based client authentication.</span></span> <span data-ttu-id="edaeb-144">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="edaeb-144">This mode should be used with caution.</span></span> <span data-ttu-id="edaeb-145">Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="edaeb-145">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edaeb-146">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="edaeb-146">Child Elements</span></span>  
  
|<span data-ttu-id="edaeb-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="edaeb-147">Element</span></span>|<span data-ttu-id="edaeb-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edaeb-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edaeb-149">\<transport></span><span class="sxs-lookup"><span data-stu-id="edaeb-149">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="edaeb-150">Definisce le impostazioni di sicurezza del trasporto per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="edaeb-150">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="edaeb-151">L'elemento corrisponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="edaeb-151">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="edaeb-152">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="edaeb-152">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="edaeb-153">Definisce le impostazioni di sicurezza del messaggio per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="edaeb-153">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="edaeb-154">L'elemento corrisponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="edaeb-154">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edaeb-155">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="edaeb-155">Parent Elements</span></span>  
  
|<span data-ttu-id="edaeb-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="edaeb-156">Element</span></span>|<span data-ttu-id="edaeb-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edaeb-157">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="edaeb-158">binding</span><span class="sxs-lookup"><span data-stu-id="edaeb-158">binding</span></span>|<span data-ttu-id="edaeb-159">Elemento di associazione della [ \<> BasicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="edaeb-159">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edaeb-160">Note</span><span class="sxs-lookup"><span data-stu-id="edaeb-160">Remarks</span></span>  
 <span data-ttu-id="edaeb-161">Per impostazione predefinita, il messaggio SOAP non è protetto e il client non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="edaeb-161">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="edaeb-162">Questo elemento consente di configurare impostazioni di sicurezza aggiuntive per l'elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="edaeb-162">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edaeb-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edaeb-163">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="edaeb-164">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="edaeb-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="edaeb-165">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="edaeb-165">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="edaeb-166">Associazioni</span><span class="sxs-lookup"><span data-stu-id="edaeb-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="edaeb-167">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="edaeb-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="edaeb-168">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="edaeb-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="edaeb-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="edaeb-169">\<binding></span></span>](../../../misc/binding.md)
