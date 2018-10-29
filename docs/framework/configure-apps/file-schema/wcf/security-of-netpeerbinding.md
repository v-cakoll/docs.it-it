---
title: '&lt;security&gt; di &lt;netPeerBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: d32b6426009c403d74ca3a05d3c3ba7be9163cae
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197327"
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="c71cf-102">&lt;security&gt; di &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="c71cf-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="c71cf-103">Definisce le impostazioni di sicurezza del [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), incluso il tipo di autenticazione utilizzato e la sicurezza per il trasporto dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="c71cf-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="c71cf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c71cf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c71cf-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="c71cf-105">\<bindings></span></span>  
<span data-ttu-id="c71cf-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="c71cf-106">\<netPeerBinding></span></span>  
<span data-ttu-id="c71cf-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c71cf-107">\<binding></span></span>  
<span data-ttu-id="c71cf-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c71cf-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c71cf-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c71cf-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c71cf-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c71cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c71cf-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c71cf-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c71cf-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c71cf-112">Attributes</span></span>  
  
|<span data-ttu-id="c71cf-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c71cf-113">Attribute</span></span>|<span data-ttu-id="c71cf-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c71cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c71cf-115">modalità</span><span class="sxs-lookup"><span data-stu-id="c71cf-115">mode</span></span>|<span data-ttu-id="c71cf-116">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c71cf-116">Optional.</span></span> <span data-ttu-id="c71cf-117">Specifica il tipo di sicurezza usata da peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="c71cf-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="c71cf-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="c71cf-118">The default value is `Message`.</span></span> <span data-ttu-id="c71cf-119">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c71cf-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c71cf-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="c71cf-120">mode Attribute</span></span>  
  
|<span data-ttu-id="c71cf-121">Valore</span><span class="sxs-lookup"><span data-stu-id="c71cf-121">Value</span></span>|<span data-ttu-id="c71cf-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c71cf-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c71cf-123">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c71cf-123">Message</span></span>|<span data-ttu-id="c71cf-124">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c71cf-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="c71cf-125">None</span><span class="sxs-lookup"><span data-stu-id="c71cf-125">None</span></span>|<span data-ttu-id="c71cf-126">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="c71cf-126">Security is disabled.</span></span>|  
|<span data-ttu-id="c71cf-127">Trasporto</span><span class="sxs-lookup"><span data-stu-id="c71cf-127">Transport</span></span>|<span data-ttu-id="c71cf-128">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c71cf-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="c71cf-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="c71cf-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="c71cf-130">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="c71cf-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="c71cf-131">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="c71cf-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c71cf-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c71cf-132">Child Elements</span></span>  
  
|<span data-ttu-id="c71cf-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="c71cf-133">Element</span></span>|<span data-ttu-id="c71cf-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c71cf-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c71cf-135">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="c71cf-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="c71cf-136">Definisce il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="c71cf-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="c71cf-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c71cf-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c71cf-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c71cf-138">Parent Elements</span></span>  
  
|<span data-ttu-id="c71cf-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="c71cf-139">Element</span></span>|<span data-ttu-id="c71cf-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c71cf-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c71cf-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="c71cf-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c71cf-142">Definisce tutte le funzionalità di associazione del [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="c71cf-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c71cf-143">Note</span><span class="sxs-lookup"><span data-stu-id="c71cf-143">Remarks</span></span>  
 <span data-ttu-id="c71cf-144">La sicurezza può essere specifica dei messaggi o del trasporto.</span><span class="sxs-lookup"><span data-stu-id="c71cf-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c71cf-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c71cf-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="c71cf-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="c71cf-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c71cf-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="c71cf-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="c71cf-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c71cf-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c71cf-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="c71cf-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c71cf-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="c71cf-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="c71cf-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="c71cf-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
