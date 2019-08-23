---
title: <security>elemento di<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 61b56ca1fae5c328cda0bbebef4026f0784095a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936825"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="286cb-102">\<Security > elemento di \<WS2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="286cb-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="286cb-103">Definisce le impostazioni di sicurezza dell' [ \<elemento > WS2007FederationHttpBinding](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="286cb-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="286cb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="286cb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="286cb-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="286cb-105">\<bindings></span></span>  
<span data-ttu-id="286cb-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="286cb-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="286cb-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="286cb-107">\<binding></span></span>  
<span data-ttu-id="286cb-108">\<security></span><span class="sxs-lookup"><span data-stu-id="286cb-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286cb-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="286cb-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="286cb-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="286cb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="286cb-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="286cb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="286cb-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="286cb-112">Attributes</span></span>  
  
|<span data-ttu-id="286cb-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="286cb-113">Attribute</span></span>|<span data-ttu-id="286cb-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="286cb-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="286cb-115">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="286cb-115">Optional.</span></span> <span data-ttu-id="286cb-116">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="286cb-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="286cb-117">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="286cb-117">The default value is `Message`.</span></span> <span data-ttu-id="286cb-118">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="286cb-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="286cb-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="286cb-119">mode Attribute</span></span>  
  
|<span data-ttu-id="286cb-120">Value</span><span class="sxs-lookup"><span data-stu-id="286cb-120">Value</span></span>|<span data-ttu-id="286cb-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="286cb-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="286cb-122">Nessuna</span><span class="sxs-lookup"><span data-stu-id="286cb-122">None</span></span>|<span data-ttu-id="286cb-123">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="286cb-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="286cb-124">Messaggio</span><span class="sxs-lookup"><span data-stu-id="286cb-124">Message</span></span>|<span data-ttu-id="286cb-125">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="286cb-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="286cb-126">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="286cb-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="286cb-127">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="286cb-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="286cb-128">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="286cb-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="286cb-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="286cb-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="286cb-130">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="286cb-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="286cb-131">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="286cb-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="286cb-132">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="286cb-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="286cb-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="286cb-133">Child Elements</span></span>  
  
|<span data-ttu-id="286cb-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="286cb-134">Element</span></span>|<span data-ttu-id="286cb-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="286cb-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="286cb-136">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="286cb-136">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="286cb-137">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="286cb-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="286cb-138">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="286cb-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="286cb-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="286cb-139">Parent Elements</span></span>  
  
|<span data-ttu-id="286cb-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="286cb-140">Element</span></span>|<span data-ttu-id="286cb-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="286cb-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="286cb-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="286cb-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="286cb-143">Definisce tutte le funzionalità di associazione del [ \<> WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="286cb-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="286cb-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="286cb-144">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="286cb-145">Procedura: Creare un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="286cb-145">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="286cb-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="286cb-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="286cb-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="286cb-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="286cb-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="286cb-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="286cb-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="286cb-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="286cb-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="286cb-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="286cb-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="286cb-151">\<binding></span></span>](../../../misc/binding.md)
