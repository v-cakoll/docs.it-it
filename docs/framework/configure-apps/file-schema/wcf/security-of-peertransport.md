---
title: <security> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: aadf2058c66cea4919d5dc9aa5aeab7850fcc395
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283764"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="6d90b-102">\<security> of \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="6d90b-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="6d90b-103">Contiene le impostazioni di sicurezza associate a un canale peer, compreso il tipo di autenticazione usato e la sicurezza applicata al trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="6d90b-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="6d90b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6d90b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6d90b-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="6d90b-105">\<bindings></span></span>  
<span data-ttu-id="6d90b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6d90b-106">\<customBinding></span></span>  
<span data-ttu-id="6d90b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6d90b-107">\<binding></span></span>  
<span data-ttu-id="6d90b-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="6d90b-108">\<peerTransport></span></span>  
<span data-ttu-id="6d90b-109">\<security></span><span class="sxs-lookup"><span data-stu-id="6d90b-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d90b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d90b-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d90b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6d90b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6d90b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6d90b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d90b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="6d90b-113">Attributes</span></span>  
  
|<span data-ttu-id="6d90b-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="6d90b-114">Attribute</span></span>|<span data-ttu-id="6d90b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d90b-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="6d90b-116">Specifica il tipo di sicurezza da applicare.</span><span class="sxs-lookup"><span data-stu-id="6d90b-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="6d90b-117">Il valore predefinito è Message.</span><span class="sxs-lookup"><span data-stu-id="6d90b-117">The default value is Message.</span></span> <span data-ttu-id="6d90b-118">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6d90b-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="6d90b-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="6d90b-119">mode Attribute</span></span>  
  
|<span data-ttu-id="6d90b-120">Valore</span><span class="sxs-lookup"><span data-stu-id="6d90b-120">Value</span></span>|<span data-ttu-id="6d90b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d90b-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="6d90b-122">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="6d90b-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="6d90b-123">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d90b-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="6d90b-124">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="6d90b-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="6d90b-125">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="6d90b-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="6d90b-126">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="6d90b-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d90b-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6d90b-127">Child Elements</span></span>  
  
|<span data-ttu-id="6d90b-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d90b-128">Element</span></span>|<span data-ttu-id="6d90b-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d90b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d90b-130">\<transport></span><span class="sxs-lookup"><span data-stu-id="6d90b-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="6d90b-131">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6d90b-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="6d90b-132">Questo elemento presenta un attributo `clientCredentialType` che specifica le credenziali da usare quando si interagisce con un servizio.</span><span class="sxs-lookup"><span data-stu-id="6d90b-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="6d90b-133">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6d90b-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="6d90b-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="6d90b-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d90b-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6d90b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="6d90b-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d90b-136">Element</span></span>|<span data-ttu-id="6d90b-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d90b-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d90b-138">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="6d90b-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="6d90b-139">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6d90b-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d90b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d90b-140">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6d90b-141">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="6d90b-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="6d90b-142">Trasporti</span><span class="sxs-lookup"><span data-stu-id="6d90b-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="6d90b-143">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="6d90b-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="6d90b-144">Associazioni</span><span class="sxs-lookup"><span data-stu-id="6d90b-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6d90b-145">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="6d90b-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6d90b-146">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="6d90b-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6d90b-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6d90b-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
