---
title: <security>elemento di<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 450b2403b8cd4ec43a41fd27bccb3b77202820bb
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399897"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="2e947-102">\<Security > elemento di \<WS2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2e947-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="2e947-103">Definisce le impostazioni di sicurezza dell' [ \<elemento > WS2007FederationHttpBinding](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2e947-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="2e947-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e947-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e947-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2e947-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2e947-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2e947-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2e947-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> ws2007FederationHttpBinding**](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2e947-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="2e947-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="2e947-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2e947-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="2e947-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e947-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e947-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e947-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2e947-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2e947-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2e947-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e947-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2e947-113">Attributes</span></span>  
  
|<span data-ttu-id="2e947-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2e947-114">Attribute</span></span>|<span data-ttu-id="2e947-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e947-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="2e947-116">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2e947-116">Optional.</span></span> <span data-ttu-id="2e947-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="2e947-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="2e947-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="2e947-118">The default value is `Message`.</span></span> <span data-ttu-id="2e947-119">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2e947-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2e947-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="2e947-120">mode Attribute</span></span>  
  
|<span data-ttu-id="2e947-121">Value</span><span class="sxs-lookup"><span data-stu-id="2e947-121">Value</span></span>|<span data-ttu-id="2e947-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e947-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e947-123">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2e947-123">None</span></span>|<span data-ttu-id="2e947-124">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="2e947-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="2e947-125">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2e947-125">Message</span></span>|<span data-ttu-id="2e947-126">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="2e947-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="2e947-127">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="2e947-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="2e947-128">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="2e947-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="2e947-129">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2e947-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="2e947-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="2e947-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="2e947-131">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2e947-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="2e947-132">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="2e947-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="2e947-133">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2e947-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e947-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2e947-134">Child Elements</span></span>  
  
|<span data-ttu-id="2e947-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e947-135">Element</span></span>|<span data-ttu-id="2e947-136">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2e947-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e947-137">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="2e947-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="2e947-138">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2e947-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="2e947-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="2e947-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e947-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2e947-140">Parent Elements</span></span>  
  
|<span data-ttu-id="2e947-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e947-141">Element</span></span>|<span data-ttu-id="2e947-142">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2e947-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e947-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="2e947-143">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="2e947-144">Definisce tutte le funzionalità di associazione del [ \<> WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2e947-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e947-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e947-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="2e947-146">Procedura: Creare un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2e947-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="2e947-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="2e947-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2e947-148">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="2e947-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2e947-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="2e947-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2e947-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="2e947-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2e947-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="2e947-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2e947-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="2e947-152">\<binding></span></span>](../../../misc/binding.md)
