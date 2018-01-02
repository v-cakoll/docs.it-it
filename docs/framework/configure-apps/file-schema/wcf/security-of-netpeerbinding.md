---
title: '&lt;security&gt; di &lt;netPeerBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b9228ccbed2b0f612986d59b72c920d57f38f69a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="8db88-102">&lt;security&gt; di &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8db88-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="8db88-103">Definisce le impostazioni di sicurezza di [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), incluso il tipo di autenticazione utilizzato e la sicurezza per il trasporto dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="8db88-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="8db88-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8db88-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8db88-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="8db88-105">\<bindings></span></span>  
<span data-ttu-id="8db88-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="8db88-106">\<netPeerBinding></span></span>  
<span data-ttu-id="8db88-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="8db88-107">\<binding></span></span>  
<span data-ttu-id="8db88-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="8db88-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db88-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8db88-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8db88-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8db88-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8db88-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8db88-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8db88-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8db88-112">Attributes</span></span>  
  
|<span data-ttu-id="8db88-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="8db88-113">Attribute</span></span>|<span data-ttu-id="8db88-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db88-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8db88-115">modalità</span><span class="sxs-lookup"><span data-stu-id="8db88-115">mode</span></span>|<span data-ttu-id="8db88-116">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8db88-116">Optional.</span></span> <span data-ttu-id="8db88-117">Specifica il tipo di sicurezza usata da peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="8db88-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="8db88-118">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="8db88-118">The default value is `Message`.</span></span> <span data-ttu-id="8db88-119">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8db88-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="8db88-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="8db88-120">mode Attribute</span></span>  
  
|<span data-ttu-id="8db88-121">Valore</span><span class="sxs-lookup"><span data-stu-id="8db88-121">Value</span></span>|<span data-ttu-id="8db88-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db88-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8db88-123">Messaggio</span><span class="sxs-lookup"><span data-stu-id="8db88-123">Message</span></span>|<span data-ttu-id="8db88-124">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="8db88-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="8db88-125">None</span><span class="sxs-lookup"><span data-stu-id="8db88-125">None</span></span>|<span data-ttu-id="8db88-126">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="8db88-126">Security is disabled.</span></span>|  
|<span data-ttu-id="8db88-127">Trasporto</span><span class="sxs-lookup"><span data-stu-id="8db88-127">Transport</span></span>|<span data-ttu-id="8db88-128">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8db88-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="8db88-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="8db88-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="8db88-130">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="8db88-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="8db88-131">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="8db88-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8db88-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8db88-132">Child Elements</span></span>  
  
|<span data-ttu-id="8db88-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="8db88-133">Element</span></span>|<span data-ttu-id="8db88-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db88-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8db88-135">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="8db88-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="8db88-136">Definisce il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="8db88-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="8db88-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8db88-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8db88-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8db88-138">Parent Elements</span></span>  
  
|<span data-ttu-id="8db88-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="8db88-139">Element</span></span>|<span data-ttu-id="8db88-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db88-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8db88-141">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="8db88-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8db88-142">Definisce tutte le funzionalità di associazione di [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8db88-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8db88-143">Note</span><span class="sxs-lookup"><span data-stu-id="8db88-143">Remarks</span></span>  
 <span data-ttu-id="8db88-144">La sicurezza può essere specifica dei messaggi o del trasporto.</span><span class="sxs-lookup"><span data-stu-id="8db88-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db88-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8db88-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="8db88-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="8db88-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="8db88-147">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="8db88-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="8db88-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8db88-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8db88-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="8db88-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8db88-150">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8db88-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="8db88-151">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="8db88-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
