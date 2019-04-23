---
title: <security> di <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 6348bc6f6c0d3a9656fbe57bf71f531d1287a949
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170092"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="f0318-102">\<security> of \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="f0318-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="f0318-103">Definisce le impostazioni di sicurezza del [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), incluso il tipo di autenticazione utilizzato e la sicurezza per il trasporto dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f0318-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="f0318-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f0318-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f0318-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="f0318-105">\<bindings></span></span>  
<span data-ttu-id="f0318-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="f0318-106">\<netPeerBinding></span></span>  
<span data-ttu-id="f0318-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f0318-107">\<binding></span></span>  
<span data-ttu-id="f0318-108">\<security></span><span class="sxs-lookup"><span data-stu-id="f0318-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0318-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0318-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0318-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f0318-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f0318-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f0318-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0318-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f0318-112">Attributes</span></span>  
  
|<span data-ttu-id="f0318-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="f0318-113">Attribute</span></span>|<span data-ttu-id="f0318-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0318-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0318-115">modalità</span><span class="sxs-lookup"><span data-stu-id="f0318-115">mode</span></span>|<span data-ttu-id="f0318-116">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f0318-116">Optional.</span></span> <span data-ttu-id="f0318-117">Specifica il tipo di sicurezza usata da peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="f0318-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="f0318-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="f0318-118">The default value is `Message`.</span></span> <span data-ttu-id="f0318-119">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f0318-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f0318-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="f0318-120">mode Attribute</span></span>  
  
|<span data-ttu-id="f0318-121">Value</span><span class="sxs-lookup"><span data-stu-id="f0318-121">Value</span></span>|<span data-ttu-id="f0318-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0318-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f0318-123">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f0318-123">Message</span></span>|<span data-ttu-id="f0318-124">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="f0318-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="f0318-125">nessuno</span><span class="sxs-lookup"><span data-stu-id="f0318-125">None</span></span>|<span data-ttu-id="f0318-126">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f0318-126">Security is disabled.</span></span>|  
|<span data-ttu-id="f0318-127">Trasporto</span><span class="sxs-lookup"><span data-stu-id="f0318-127">Transport</span></span>|<span data-ttu-id="f0318-128">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f0318-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="f0318-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="f0318-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="f0318-130">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="f0318-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="f0318-131">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="f0318-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0318-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f0318-132">Child Elements</span></span>  
  
|<span data-ttu-id="f0318-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0318-133">Element</span></span>|<span data-ttu-id="f0318-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0318-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0318-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="f0318-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="f0318-136">Definisce il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="f0318-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="f0318-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f0318-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0318-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f0318-138">Parent Elements</span></span>  
  
|<span data-ttu-id="f0318-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0318-139">Element</span></span>|<span data-ttu-id="f0318-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0318-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0318-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="f0318-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f0318-142">Definisce tutte le funzionalità di associazione del [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f0318-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0318-143">Note</span><span class="sxs-lookup"><span data-stu-id="f0318-143">Remarks</span></span>  
 <span data-ttu-id="f0318-144">La sicurezza può essere specifica dei messaggi o del trasporto.</span><span class="sxs-lookup"><span data-stu-id="f0318-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0318-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0318-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="f0318-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f0318-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f0318-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="f0318-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="f0318-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f0318-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f0318-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f0318-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f0318-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f0318-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f0318-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="f0318-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
