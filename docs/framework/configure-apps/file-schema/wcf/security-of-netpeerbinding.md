---
title: <security> di <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 88aa2898472c20c9e52cfd5830c0e41e8ea9ba21
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399812"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="732d2-102">\<> di sicurezza \<di netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="732d2-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="732d2-103">Definisce le impostazioni di sicurezza del [ \<> NetPeerTcpBinding](netpeertcpbinding.md), incluso il tipo di autenticazione utilizzato e la sicurezza utilizzata per il trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="732d2-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="732d2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="732d2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="732d2-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="732d2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="732d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="732d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="732d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netPeerTcpBinding**](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="732d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="732d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="732d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="732d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="732d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="732d2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="732d2-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="732d2-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="732d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="732d2-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="732d2-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="732d2-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="732d2-113">Attributes</span></span>  
  
|<span data-ttu-id="732d2-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="732d2-114">Attribute</span></span>|<span data-ttu-id="732d2-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="732d2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="732d2-116">modalità</span><span class="sxs-lookup"><span data-stu-id="732d2-116">mode</span></span>|<span data-ttu-id="732d2-117">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="732d2-117">Optional.</span></span> <span data-ttu-id="732d2-118">Specifica il tipo di sicurezza usata da peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="732d2-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="732d2-119">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="732d2-119">The default value is `Message`.</span></span> <span data-ttu-id="732d2-120">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="732d2-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="732d2-121">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="732d2-121">mode Attribute</span></span>  
  
|<span data-ttu-id="732d2-122">Value</span><span class="sxs-lookup"><span data-stu-id="732d2-122">Value</span></span>|<span data-ttu-id="732d2-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="732d2-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="732d2-124">Messaggio</span><span class="sxs-lookup"><span data-stu-id="732d2-124">Message</span></span>|<span data-ttu-id="732d2-125">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="732d2-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="732d2-126">Nessuna</span><span class="sxs-lookup"><span data-stu-id="732d2-126">None</span></span>|<span data-ttu-id="732d2-127">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="732d2-127">Security is disabled.</span></span>|  
|<span data-ttu-id="732d2-128">Trasporto</span><span class="sxs-lookup"><span data-stu-id="732d2-128">Transport</span></span>|<span data-ttu-id="732d2-129">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="732d2-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="732d2-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="732d2-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="732d2-131">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="732d2-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="732d2-132">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="732d2-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="732d2-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="732d2-133">Child Elements</span></span>  
  
|<span data-ttu-id="732d2-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="732d2-134">Element</span></span>|<span data-ttu-id="732d2-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="732d2-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="732d2-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="732d2-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="732d2-137">Definisce il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="732d2-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="732d2-138">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="732d2-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="732d2-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="732d2-139">Parent Elements</span></span>  
  
|<span data-ttu-id="732d2-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="732d2-140">Element</span></span>|<span data-ttu-id="732d2-141">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="732d2-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="732d2-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="732d2-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="732d2-143">Definisce tutte le funzionalità di associazione del [ \<> NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="732d2-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="732d2-144">Note</span><span class="sxs-lookup"><span data-stu-id="732d2-144">Remarks</span></span>  
 <span data-ttu-id="732d2-145">La sicurezza può essere specifica dei messaggi o del trasporto.</span><span class="sxs-lookup"><span data-stu-id="732d2-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732d2-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="732d2-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="732d2-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="732d2-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="732d2-148">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="732d2-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="732d2-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="732d2-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="732d2-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="732d2-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="732d2-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="732d2-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="732d2-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="732d2-152">\<binding></span></span>](../../../misc/binding.md)
