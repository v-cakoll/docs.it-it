---
title: <security> di <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736488"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="07ac9-102">\<> di sicurezza di \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="07ac9-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="07ac9-103">Definisce le funzionalità di sicurezza del [\<> NetHttpBinding](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="07ac9-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

<span data-ttu-id="07ac9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="07ac9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="07ac9-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="07ac9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="07ac9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="07ac9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="07ac9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetHttpBinding**](nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="07ac9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="07ac9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="07ac9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="07ac9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="07ac9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="07ac9-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07ac9-110">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07ac9-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="07ac9-111">Attributes and elements</span></span>

<span data-ttu-id="07ac9-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="07ac9-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="07ac9-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="07ac9-113">Attributes</span></span>

|<span data-ttu-id="07ac9-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="07ac9-114">Attribute</span></span>|<span data-ttu-id="07ac9-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07ac9-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="07ac9-116">modalità</span><span class="sxs-lookup"><span data-stu-id="07ac9-116">mode</span></span>|<span data-ttu-id="07ac9-117">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="07ac9-117">Optional.</span></span> <span data-ttu-id="07ac9-118">Specifica il tipo di sicurezza usata.</span><span class="sxs-lookup"><span data-stu-id="07ac9-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="07ac9-119">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="07ac9-119">The default is `None`.</span></span> <span data-ttu-id="07ac9-120">L'attributo è di tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="07ac9-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="07ac9-121">attributo mode</span><span class="sxs-lookup"><span data-stu-id="07ac9-121">mode attribute</span></span>

|<span data-ttu-id="07ac9-122">Value</span><span class="sxs-lookup"><span data-stu-id="07ac9-122">Value</span></span>|<span data-ttu-id="07ac9-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07ac9-123">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="07ac9-124">Nessuno</span><span class="sxs-lookup"><span data-stu-id="07ac9-124">None</span></span>|<span data-ttu-id="07ac9-125">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="07ac9-125">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="07ac9-126">Trasporto</span><span class="sxs-lookup"><span data-stu-id="07ac9-126">Transport</span></span>|<span data-ttu-id="07ac9-127">La sicurezza è fornita mediante il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="07ac9-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="07ac9-128">I messaggi SOAP sono protetti mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="07ac9-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="07ac9-129">Il servizio viene autenticato sul client mediante il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="07ac9-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="07ac9-130">Il client viene autenticato mediante il ClientCredentialType  fornito.</span><span class="sxs-lookup"><span data-stu-id="07ac9-130">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="07ac9-131">Messaggio</span><span class="sxs-lookup"><span data-stu-id="07ac9-131">Message</span></span>|<span data-ttu-id="07ac9-132">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="07ac9-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="07ac9-133">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="07ac9-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="07ac9-134">Per questa associazione, il sistema richiede che il certificato server sia fornito al client fuori banda.</span><span class="sxs-lookup"><span data-stu-id="07ac9-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="07ac9-135">L'unico valore `ClientCredentialType` valido per questa associazione è `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="07ac9-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="07ac9-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="07ac9-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="07ac9-137">Integrità, riservatezza e autenticazione server sono fornite dalla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="07ac9-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="07ac9-138">L'autenticazione del client è fornita per mezzo della sicurezza del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="07ac9-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="07ac9-139">Questa modalità è appropriata quando l'utente esegue l'autenticazione usando nome utente/password in presenza di una distribuzione HTTP esistente per la sicurezza del trasferimento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="07ac9-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="07ac9-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="07ac9-140">TransportCredentialOnly</span></span>|<span data-ttu-id="07ac9-141">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="07ac9-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="07ac9-142">Fornisce autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="07ac9-142">It provides http-based client authentication.</span></span> <span data-ttu-id="07ac9-143">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="07ac9-143">This mode should be used with caution.</span></span> <span data-ttu-id="07ac9-144">Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="07ac9-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="07ac9-145">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="07ac9-145">Child elements</span></span>

|<span data-ttu-id="07ac9-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="07ac9-146">Element</span></span>|<span data-ttu-id="07ac9-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07ac9-147">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07ac9-148">> trasporto \<</span><span class="sxs-lookup"><span data-stu-id="07ac9-148">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="07ac9-149">Definisce le impostazioni di sicurezza del trasporto per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="07ac9-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="07ac9-150">L'elemento corrisponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="07ac9-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="07ac9-151">\<message ></span><span class="sxs-lookup"><span data-stu-id="07ac9-151">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="07ac9-152">Definisce le impostazioni di sicurezza del messaggio per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="07ac9-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="07ac9-153">L'elemento corrisponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="07ac9-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="07ac9-154">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="07ac9-154">Parent elements</span></span>

|<span data-ttu-id="07ac9-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="07ac9-155">Element</span></span>|<span data-ttu-id="07ac9-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07ac9-156">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="07ac9-157">binding</span><span class="sxs-lookup"><span data-stu-id="07ac9-157">binding</span></span>|<span data-ttu-id="07ac9-158">Elemento di associazione della [> BasicHttpBinding di\<](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="07ac9-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="07ac9-159">Note</span><span class="sxs-lookup"><span data-stu-id="07ac9-159">Remarks</span></span>

 <span data-ttu-id="07ac9-160">Per impostazione predefinita, il messaggio SOAP non è protetto e il client non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="07ac9-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="07ac9-161">Questo elemento consente di configurare impostazioni di sicurezza aggiuntive per l'elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="07ac9-161">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="07ac9-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07ac9-162">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="07ac9-163">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="07ac9-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="07ac9-164">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="07ac9-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="07ac9-165">Associazioni</span><span class="sxs-lookup"><span data-stu-id="07ac9-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="07ac9-166">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="07ac9-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="07ac9-167">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="07ac9-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="07ac9-168">\<binding ></span><span class="sxs-lookup"><span data-stu-id="07ac9-168">\<binding></span></span>](bindings.md)
