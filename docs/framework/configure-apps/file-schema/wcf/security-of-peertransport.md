---
title: <security> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 1aff79bf5867a3a1ebe05e3f812475dac4b413e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116863"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="ea4f6-102">\<security> of \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="ea4f6-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="ea4f6-103">Contiene le impostazioni di sicurezza associate a un canale peer, compreso il tipo di autenticazione usato e la sicurezza applicata al trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="ea4f6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ea4f6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ea4f6-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="ea4f6-105">\<bindings></span></span>  
<span data-ttu-id="ea4f6-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ea4f6-106">\<customBinding></span></span>  
<span data-ttu-id="ea4f6-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea4f6-107">\<binding></span></span>  
<span data-ttu-id="ea4f6-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="ea4f6-108">\<peerTransport></span></span>  
<span data-ttu-id="ea4f6-109">\<security></span><span class="sxs-lookup"><span data-stu-id="ea4f6-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4f6-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea4f6-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea4f6-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea4f6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ea4f6-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea4f6-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea4f6-113">Attributes</span></span>  
  
|<span data-ttu-id="ea4f6-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ea4f6-114">Attribute</span></span>|<span data-ttu-id="ea4f6-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea4f6-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="ea4f6-116">Specifica il tipo di sicurezza da applicare.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="ea4f6-117">Il valore predefinito è Message.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-117">The default value is Message.</span></span> <span data-ttu-id="ea4f6-118">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ea4f6-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="ea4f6-119">mode Attribute</span></span>  
  
|<span data-ttu-id="ea4f6-120">Value</span><span class="sxs-lookup"><span data-stu-id="ea4f6-120">Value</span></span>|<span data-ttu-id="ea4f6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea4f6-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="ea4f6-122">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="ea4f6-123">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="ea4f6-124">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="ea4f6-125">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="ea4f6-126">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea4f6-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea4f6-127">Child Elements</span></span>  
  
|<span data-ttu-id="ea4f6-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea4f6-128">Element</span></span>|<span data-ttu-id="ea4f6-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea4f6-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea4f6-130">\<transport></span><span class="sxs-lookup"><span data-stu-id="ea4f6-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="ea4f6-131">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="ea4f6-132">Questo elemento presenta un attributo `clientCredentialType` che specifica le credenziali da usare quando si interagisce con un servizio.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="ea4f6-133">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="ea4f6-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea4f6-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea4f6-135">Parent Elements</span></span>  
  
|<span data-ttu-id="ea4f6-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea4f6-136">Element</span></span>|<span data-ttu-id="ea4f6-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea4f6-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea4f6-138">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="ea4f6-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="ea4f6-139">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ea4f6-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea4f6-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea4f6-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ea4f6-141">Protezione del trasporto</span><span class="sxs-lookup"><span data-stu-id="ea4f6-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="ea4f6-142">Trasporti</span><span class="sxs-lookup"><span data-stu-id="ea4f6-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="ea4f6-143">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="ea4f6-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ea4f6-144">Associazioni</span><span class="sxs-lookup"><span data-stu-id="ea4f6-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ea4f6-145">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="ea4f6-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ea4f6-146">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ea4f6-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ea4f6-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ea4f6-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
