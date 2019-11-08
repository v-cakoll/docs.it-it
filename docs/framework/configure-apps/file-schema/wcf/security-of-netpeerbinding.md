---
title: <security> di <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738654"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="52e68-102">\<> di sicurezza di \<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="52e68-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="52e68-103">Definisce le impostazioni di sicurezza del [\<> NetPeerTcpBinding](netpeertcpbinding.md), incluso il tipo di autenticazione utilizzato e la sicurezza utilizzata per il trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="52e68-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="52e68-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52e68-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52e68-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="52e68-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="52e68-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="52e68-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="52e68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetPeerTcpBinding**](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="52e68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="52e68-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="52e68-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="52e68-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**sicurezza** ></span><span class="sxs-lookup"><span data-stu-id="52e68-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e68-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52e68-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52e68-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="52e68-111">Attributes and Elements</span></span>  
 <span data-ttu-id="52e68-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="52e68-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52e68-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="52e68-113">Attributes</span></span>  
  
|<span data-ttu-id="52e68-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="52e68-114">Attribute</span></span>|<span data-ttu-id="52e68-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52e68-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52e68-116">modalità</span><span class="sxs-lookup"><span data-stu-id="52e68-116">mode</span></span>|<span data-ttu-id="52e68-117">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="52e68-117">Optional.</span></span> <span data-ttu-id="52e68-118">Specifica il tipo di sicurezza usata da peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="52e68-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="52e68-119">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="52e68-119">The default value is `Message`.</span></span> <span data-ttu-id="52e68-120">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="52e68-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="52e68-121">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="52e68-121">mode Attribute</span></span>  
  
|<span data-ttu-id="52e68-122">Value</span><span class="sxs-lookup"><span data-stu-id="52e68-122">Value</span></span>|<span data-ttu-id="52e68-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52e68-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="52e68-124">Messaggio</span><span class="sxs-lookup"><span data-stu-id="52e68-124">Message</span></span>|<span data-ttu-id="52e68-125">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="52e68-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="52e68-126">Nessuno</span><span class="sxs-lookup"><span data-stu-id="52e68-126">None</span></span>|<span data-ttu-id="52e68-127">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="52e68-127">Security is disabled.</span></span>|  
|<span data-ttu-id="52e68-128">Trasporto</span><span class="sxs-lookup"><span data-stu-id="52e68-128">Transport</span></span>|<span data-ttu-id="52e68-129">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="52e68-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="52e68-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="52e68-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="52e68-131">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="52e68-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="52e68-132">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="52e68-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52e68-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="52e68-133">Child Elements</span></span>  
  
|<span data-ttu-id="52e68-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="52e68-134">Element</span></span>|<span data-ttu-id="52e68-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52e68-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52e68-136">> trasporto \<</span><span class="sxs-lookup"><span data-stu-id="52e68-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="52e68-137">Definisce il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="52e68-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="52e68-138">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="52e68-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52e68-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="52e68-139">Parent Elements</span></span>  
  
|<span data-ttu-id="52e68-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="52e68-140">Element</span></span>|<span data-ttu-id="52e68-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52e68-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52e68-142">\<binding ></span><span class="sxs-lookup"><span data-stu-id="52e68-142">\<binding></span></span>](bindings.md)|<span data-ttu-id="52e68-143">Definisce tutte le funzionalità di associazione della [\<> NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="52e68-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52e68-144">Note</span><span class="sxs-lookup"><span data-stu-id="52e68-144">Remarks</span></span>  
 <span data-ttu-id="52e68-145">La sicurezza può essere specifica dei messaggi o del trasporto.</span><span class="sxs-lookup"><span data-stu-id="52e68-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e68-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52e68-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="52e68-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="52e68-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="52e68-148">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="52e68-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="52e68-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="52e68-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="52e68-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="52e68-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="52e68-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="52e68-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="52e68-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="52e68-152">\<binding></span></span>](bindings.md)
