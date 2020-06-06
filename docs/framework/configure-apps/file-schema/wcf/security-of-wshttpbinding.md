---
title: <security> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738577"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="209c5-102">\<security> di \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="209c5-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="209c5-103">Rappresenta le funzionalità di sicurezza di [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="209c5-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="209c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="209c5-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="209c5-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="209c5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="209c5-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="209c5-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="209c5-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="209c5-107">Attributes</span></span>  
  
|<span data-ttu-id="209c5-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="209c5-108">Attribute</span></span>|<span data-ttu-id="209c5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="209c5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="209c5-110">mode</span><span class="sxs-lookup"><span data-stu-id="209c5-110">mode</span></span>|<span data-ttu-id="209c5-111">Opzionale.</span><span class="sxs-lookup"><span data-stu-id="209c5-111">-   Optional.</span></span> <span data-ttu-id="209c5-112">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="209c5-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="209c5-113">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="209c5-113">The default is `Message`.</span></span><br /><span data-ttu-id="209c5-114">: Questo attributo è di tipo <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="209c5-114">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="209c5-115">Attributo Mode</span><span class="sxs-lookup"><span data-stu-id="209c5-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="209c5-116">Valore</span><span class="sxs-lookup"><span data-stu-id="209c5-116">Value</span></span>|<span data-ttu-id="209c5-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="209c5-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="209c5-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="209c5-118">None</span></span>|<span data-ttu-id="209c5-119">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="209c5-119">Security is disabled.</span></span>|  
|<span data-ttu-id="209c5-120">Trasporto</span><span class="sxs-lookup"><span data-stu-id="209c5-120">Transport</span></span>|<span data-ttu-id="209c5-121">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="209c5-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="209c5-122">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="209c5-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="209c5-123">Il messaggio è interamente protetto usando HTTPS e viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="209c5-123">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="209c5-124">L'autenticazione client è controllata tramite l'attributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="209c5-124">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="209c5-125">dell'oggetto [\<transport>](transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="209c5-125">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="209c5-126">Message</span><span class="sxs-lookup"><span data-stu-id="209c5-126">Message</span></span>|<span data-ttu-id="209c5-127">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="209c5-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="209c5-128">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="209c5-128">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="209c5-129">Questa modalità offre varie funzionalità, ad esempio la disponibilità o meno delle credenziali del servizio per il client fuori banda, il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà Security.Message.</span><span class="sxs-lookup"><span data-stu-id="209c5-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="209c5-130">L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="209c5-130">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="209c5-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="209c5-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="209c5-132">In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="209c5-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="209c5-133">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="209c5-133">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="209c5-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="209c5-134">Child Elements</span></span>  
  
|<span data-ttu-id="209c5-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="209c5-135">Element</span></span>|<span data-ttu-id="209c5-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="209c5-136">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="209c5-137">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="209c5-137">Defines the transport security settings.</span></span> <span data-ttu-id="209c5-138">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="209c5-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="209c5-139">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="209c5-139">Defines the security settings for the message.</span></span> <span data-ttu-id="209c5-140">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="209c5-140">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="209c5-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="209c5-141">Parent Elements</span></span>  
  
|<span data-ttu-id="209c5-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="209c5-142">Element</span></span>|<span data-ttu-id="209c5-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="209c5-143">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="209c5-144">Associazione protetta per applicazioni di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="209c5-144">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="209c5-145">Commenti</span><span class="sxs-lookup"><span data-stu-id="209c5-145">Remarks</span></span>  
 <span data-ttu-id="209c5-146">La classe WSHttpBinding è progettata per essere interoperabile con i servizi che implementano le specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="209c5-146">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="209c5-147">La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.</span><span class="sxs-lookup"><span data-stu-id="209c5-147">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="209c5-148">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="209c5-148">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="209c5-149">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="209c5-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="209c5-150">Binding</span><span class="sxs-lookup"><span data-stu-id="209c5-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="209c5-151">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="209c5-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="209c5-152">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="209c5-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
