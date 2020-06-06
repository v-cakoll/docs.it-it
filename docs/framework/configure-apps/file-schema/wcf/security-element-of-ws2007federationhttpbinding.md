---
title: <security>elemento di<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738731"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="2ef3b-102">\<security>elemento di\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2ef3b-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="2ef3b-103">Definisce le impostazioni di sicurezza dell' [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="2ef3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ef3b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ef3b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2ef3b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2ef3b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ef3b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="2ef3b-107">Attributes</span></span>  
  
|<span data-ttu-id="2ef3b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="2ef3b-108">Attribute</span></span>|<span data-ttu-id="2ef3b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ef3b-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="2ef3b-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-110">Optional.</span></span> <span data-ttu-id="2ef3b-111">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="2ef3b-112">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-112">The default value is `Message`.</span></span> <span data-ttu-id="2ef3b-113">L'attributo è di tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2ef3b-114">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="2ef3b-114">mode Attribute</span></span>  
  
|<span data-ttu-id="2ef3b-115">Valore</span><span class="sxs-lookup"><span data-stu-id="2ef3b-115">Value</span></span>|<span data-ttu-id="2ef3b-116">Description</span><span class="sxs-lookup"><span data-stu-id="2ef3b-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ef3b-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="2ef3b-117">None</span></span>|<span data-ttu-id="2ef3b-118">Il messaggio SOAP non viene protetto durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="2ef3b-119">Message</span><span class="sxs-lookup"><span data-stu-id="2ef3b-119">Message</span></span>|<span data-ttu-id="2ef3b-120">L'integrità, la riservatezza e l'autenticazione server e client sono fornite usando la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="2ef3b-121">Per impostazione predefinita, il corpo viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="2ef3b-122">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="2ef3b-123">L'autenticazione client è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="2ef3b-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="2ef3b-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="2ef3b-125">Integrità, riservatezza e autenticazione server sono fornite tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="2ef3b-126">Il servizio deve essere configurato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="2ef3b-127">L'autenticazione client è fornita tramite la sicurezza dei messaggi SOAP ed è basata sul token rilasciato al client da un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ef3b-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2ef3b-128">Child Elements</span></span>  
  
|<span data-ttu-id="2ef3b-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ef3b-129">Element</span></span>|<span data-ttu-id="2ef3b-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ef3b-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="2ef3b-131">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="2ef3b-132">L'elemento è di tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ef3b-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2ef3b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="2ef3b-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ef3b-134">Element</span></span>|<span data-ttu-id="2ef3b-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ef3b-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="2ef3b-136">Definisce tutte le funzionalità di associazione di [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2ef3b-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ef3b-137">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2ef3b-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="2ef3b-138">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2ef3b-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="2ef3b-139">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="2ef3b-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2ef3b-140">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="2ef3b-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2ef3b-141">Binding</span><span class="sxs-lookup"><span data-stu-id="2ef3b-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2ef3b-142">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="2ef3b-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2ef3b-143">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="2ef3b-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
