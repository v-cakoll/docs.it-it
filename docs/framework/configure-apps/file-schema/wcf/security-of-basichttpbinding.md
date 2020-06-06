---
title: <security> di <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: c8e4f2d000a155eecd2a6c7faaaf4af525b24ca3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738711"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="7e662-102">\<security> di \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7e662-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="7e662-103">Definisce le funzionalità di sicurezza di [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7e662-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="7e662-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e662-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e662-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e662-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7e662-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e662-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e662-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e662-107">Attributes</span></span>  
  
|<span data-ttu-id="7e662-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e662-108">Attribute</span></span>|<span data-ttu-id="7e662-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e662-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e662-110">mode</span><span class="sxs-lookup"><span data-stu-id="7e662-110">mode</span></span>|<span data-ttu-id="7e662-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7e662-111">Optional.</span></span> <span data-ttu-id="7e662-112">Specifica il tipo di sicurezza usata.</span><span class="sxs-lookup"><span data-stu-id="7e662-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="7e662-113">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="7e662-113">The default is `None`.</span></span> <span data-ttu-id="7e662-114">L'attributo è di tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7e662-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7e662-115">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="7e662-115">mode Attribute</span></span>  
  
|<span data-ttu-id="7e662-116">Valore</span><span class="sxs-lookup"><span data-stu-id="7e662-116">Value</span></span>|<span data-ttu-id="7e662-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e662-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e662-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="7e662-118">None</span></span>|<span data-ttu-id="7e662-119">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="7e662-119">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="7e662-120">Trasporto</span><span class="sxs-lookup"><span data-stu-id="7e662-120">Transport</span></span>|<span data-ttu-id="7e662-121">La sicurezza è fornita mediante il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7e662-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="7e662-122">I messaggi SOAP vengono protetti utilizzando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7e662-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="7e662-123">Il servizio viene autenticato sul client mediante il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="7e662-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="7e662-124">Il client viene autenticato mediante il ClientCredentialType  fornito.</span><span class="sxs-lookup"><span data-stu-id="7e662-124">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="7e662-125">Vedere [\<transport>](transport-of-basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7e662-125">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="7e662-126">Message</span><span class="sxs-lookup"><span data-stu-id="7e662-126">Message</span></span>|<span data-ttu-id="7e662-127">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="7e662-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="7e662-128">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="7e662-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="7e662-129">Per questa associazione, il sistema richiede che il certificato server sia fornito al client fuori banda.</span><span class="sxs-lookup"><span data-stu-id="7e662-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="7e662-130">L'unico valore `ClientCredentialType` valido per questa associazione è `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="7e662-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="7e662-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7e662-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="7e662-132">Integrità, riservatezza e autenticazione server sono fornite dalla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="7e662-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="7e662-133">L'autenticazione del client è fornita per mezzo della sicurezza del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="7e662-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="7e662-134">Questa modalità è appropriata quando l'utente esegue l'autenticazione usando nome utente/password in presenza di una distribuzione HTTP esistente per la sicurezza del trasferimento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="7e662-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="7e662-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="7e662-135">TransportCredentialOnly</span></span>|<span data-ttu-id="7e662-136">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="7e662-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="7e662-137">Fornisce autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e662-137">It provides http-based client authentication.</span></span> <span data-ttu-id="7e662-138">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="7e662-138">This mode should be used with caution.</span></span> <span data-ttu-id="7e662-139">Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="7e662-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e662-140">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e662-140">Child Elements</span></span>  
  
|<span data-ttu-id="7e662-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e662-141">Element</span></span>|<span data-ttu-id="7e662-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e662-142">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="7e662-143">Definisce le impostazioni di sicurezza del trasporto per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="7e662-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="7e662-144">L'elemento corrisponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="7e662-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="7e662-145">Definisce le impostazioni di sicurezza del messaggio per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="7e662-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="7e662-146">L'elemento corrisponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="7e662-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e662-147">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e662-147">Parent Elements</span></span>  
  
|<span data-ttu-id="7e662-148">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e662-148">Element</span></span>|<span data-ttu-id="7e662-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e662-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e662-150">binding</span><span class="sxs-lookup"><span data-stu-id="7e662-150">binding</span></span>|<span data-ttu-id="7e662-151">Elemento di associazione di [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7e662-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e662-152">Commenti</span><span class="sxs-lookup"><span data-stu-id="7e662-152">Remarks</span></span>  
 <span data-ttu-id="7e662-153">Per impostazione predefinita, il messaggio SOAP non è protetto e il client non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="7e662-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="7e662-154">Questo elemento consente di configurare impostazioni di sicurezza aggiuntive per l'elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="7e662-154">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e662-155">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7e662-155">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="7e662-156">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="7e662-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7e662-157">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="7e662-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="7e662-158">Binding</span><span class="sxs-lookup"><span data-stu-id="7e662-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7e662-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="7e662-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7e662-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="7e662-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
