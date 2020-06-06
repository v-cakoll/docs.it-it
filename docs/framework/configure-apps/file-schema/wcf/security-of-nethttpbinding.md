---
title: <security> di <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736488"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="850e7-102">\<security> di \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="850e7-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="850e7-103">Definisce le funzionalità di sicurezza di [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="850e7-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  

## <a name="syntax"></a><span data-ttu-id="850e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="850e7-104">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="850e7-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="850e7-105">Attributes and elements</span></span>

<span data-ttu-id="850e7-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="850e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="850e7-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="850e7-107">Attributes</span></span>

|<span data-ttu-id="850e7-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="850e7-108">Attribute</span></span>|<span data-ttu-id="850e7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="850e7-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="850e7-110">mode</span><span class="sxs-lookup"><span data-stu-id="850e7-110">mode</span></span>|<span data-ttu-id="850e7-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="850e7-111">Optional.</span></span> <span data-ttu-id="850e7-112">Specifica il tipo di sicurezza usata.</span><span class="sxs-lookup"><span data-stu-id="850e7-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="850e7-113">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="850e7-113">The default is `None`.</span></span> <span data-ttu-id="850e7-114">L'attributo è di tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="850e7-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="850e7-115">attributo mode</span><span class="sxs-lookup"><span data-stu-id="850e7-115">mode attribute</span></span>

|<span data-ttu-id="850e7-116">Valore</span><span class="sxs-lookup"><span data-stu-id="850e7-116">Value</span></span>|<span data-ttu-id="850e7-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="850e7-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="850e7-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="850e7-118">None</span></span>|<span data-ttu-id="850e7-119">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="850e7-119">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="850e7-120">Trasporto</span><span class="sxs-lookup"><span data-stu-id="850e7-120">Transport</span></span>|<span data-ttu-id="850e7-121">La sicurezza è fornita mediante il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="850e7-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="850e7-122">I messaggi SOAP vengono protetti utilizzando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="850e7-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="850e7-123">Il servizio viene autenticato sul client mediante il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="850e7-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="850e7-124">Il client viene autenticato mediante il ClientCredentialType  fornito.</span><span class="sxs-lookup"><span data-stu-id="850e7-124">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="850e7-125">Message</span><span class="sxs-lookup"><span data-stu-id="850e7-125">Message</span></span>|<span data-ttu-id="850e7-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="850e7-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="850e7-127">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="850e7-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="850e7-128">Per questa associazione, il sistema richiede che il certificato server sia fornito al client fuori banda.</span><span class="sxs-lookup"><span data-stu-id="850e7-128">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="850e7-129">L'unico valore `ClientCredentialType` valido per questa associazione è `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="850e7-129">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="850e7-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="850e7-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="850e7-131">Integrità, riservatezza e autenticazione server sono fornite dalla sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="850e7-131">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="850e7-132">L'autenticazione del client è fornita per mezzo della sicurezza del messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="850e7-132">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="850e7-133">Questa modalità è appropriata quando l'utente esegue l'autenticazione usando nome utente/password in presenza di una distribuzione HTTP esistente per la sicurezza del trasferimento dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="850e7-133">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="850e7-134">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="850e7-134">TransportCredentialOnly</span></span>|<span data-ttu-id="850e7-135">Questa modalità non fornisce l'integrità e la riservatezza dei messaggi,</span><span class="sxs-lookup"><span data-stu-id="850e7-135">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="850e7-136">Fornisce autenticazione client basata su HTTP.</span><span class="sxs-lookup"><span data-stu-id="850e7-136">It provides http-based client authentication.</span></span> <span data-ttu-id="850e7-137">Tale modalità deve essere usata con cautela.</span><span class="sxs-lookup"><span data-stu-id="850e7-137">This mode should be used with caution.</span></span> <span data-ttu-id="850e7-138">Deve essere utilizzato in ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e l'infrastruttura WCF fornisce solo l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="850e7-138">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="850e7-139">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="850e7-139">Child elements</span></span>

|<span data-ttu-id="850e7-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="850e7-140">Element</span></span>|<span data-ttu-id="850e7-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="850e7-141">Description</span></span>|
|-------------|-----------------|
|[\<transport>](transport-of-nethttpbinding.md)|<span data-ttu-id="850e7-142">Definisce le impostazioni di sicurezza del trasporto per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="850e7-142">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="850e7-143">L'elemento corrisponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="850e7-143">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[\<message>](message-of-nethttpbinding.md)|<span data-ttu-id="850e7-144">Definisce le impostazioni di sicurezza del messaggio per un servizio HTTP di base.</span><span class="sxs-lookup"><span data-stu-id="850e7-144">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="850e7-145">L'elemento corrisponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="850e7-145">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="850e7-146">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="850e7-146">Parent elements</span></span>

|<span data-ttu-id="850e7-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="850e7-147">Element</span></span>|<span data-ttu-id="850e7-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="850e7-148">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="850e7-149">binding</span><span class="sxs-lookup"><span data-stu-id="850e7-149">binding</span></span>|<span data-ttu-id="850e7-150">Elemento di associazione di [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="850e7-150">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="850e7-151">Commenti</span><span class="sxs-lookup"><span data-stu-id="850e7-151">Remarks</span></span>

 <span data-ttu-id="850e7-152">Per impostazione predefinita, il messaggio SOAP non è protetto e il client non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="850e7-152">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="850e7-153">Questo elemento consente di configurare impostazioni di sicurezza aggiuntive per l'elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="850e7-153">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="850e7-154">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="850e7-154">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="850e7-155">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="850e7-155">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="850e7-156">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="850e7-156">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="850e7-157">Binding</span><span class="sxs-lookup"><span data-stu-id="850e7-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="850e7-158">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="850e7-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="850e7-159">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="850e7-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
