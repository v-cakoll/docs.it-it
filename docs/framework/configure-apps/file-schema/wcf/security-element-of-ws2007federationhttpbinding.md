---
title: elemento <security> di <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738731"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="55884-102">\<elemento > Security di \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="55884-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="55884-103">Definisce le impostazioni di sicurezza dell'elemento [\<> WS2007FederationHttpBinding](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="55884-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="55884-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55884-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55884-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="55884-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="55884-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="55884-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="55884-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**WS2007FederationHttpBinding**](ws2007federationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="55884-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="55884-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="55884-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="55884-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="55884-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55884-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55884-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55884-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="55884-111">Attributes and Elements</span></span>  
 <span data-ttu-id="55884-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="55884-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55884-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="55884-113">Attributes</span></span>  
  
|<span data-ttu-id="55884-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="55884-114">Attribute</span></span>|<span data-ttu-id="55884-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55884-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="55884-116">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="55884-116">Optional.</span></span> <span data-ttu-id="55884-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="55884-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="55884-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="55884-118">The default value is `Message`.</span></span> <span data-ttu-id="55884-119">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="55884-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="55884-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="55884-120">mode Attribute</span></span>  
  
|<span data-ttu-id="55884-121">Value</span><span class="sxs-lookup"><span data-stu-id="55884-121">Value</span></span>|<span data-ttu-id="55884-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55884-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="55884-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="55884-123">None</span></span>|<span data-ttu-id="55884-124">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="55884-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="55884-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="55884-125">Message</span></span>|<span data-ttu-id="55884-126">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="55884-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="55884-127">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="55884-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="55884-128">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="55884-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="55884-129">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="55884-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="55884-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="55884-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="55884-131">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="55884-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="55884-132">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="55884-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="55884-133">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="55884-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55884-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="55884-134">Child Elements</span></span>  
  
|<span data-ttu-id="55884-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="55884-135">Element</span></span>|<span data-ttu-id="55884-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55884-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55884-137">\<message ></span><span class="sxs-lookup"><span data-stu-id="55884-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="55884-138">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="55884-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="55884-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="55884-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55884-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="55884-140">Parent Elements</span></span>  
  
|<span data-ttu-id="55884-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="55884-141">Element</span></span>|<span data-ttu-id="55884-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55884-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55884-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="55884-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="55884-144">Definisce tutte le funzionalità di associazione della [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="55884-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55884-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55884-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="55884-146">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="55884-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="55884-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="55884-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="55884-148">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="55884-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="55884-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="55884-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="55884-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="55884-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="55884-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="55884-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="55884-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="55884-152">\<binding></span></span>](bindings.md)
