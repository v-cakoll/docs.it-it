---
title: '&lt;security&gt; di &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
author: BrucePerlerMS
ms.openlocfilehash: 152087550d3fa881a7a88271d9c91dfcc5c894c8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176760"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="1439a-102">&lt;security&gt; di &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="1439a-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="1439a-103">Contiene le impostazioni di sicurezza associate a un canale peer, compreso il tipo di autenticazione usato e la sicurezza applicata al trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1439a-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="1439a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1439a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1439a-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1439a-105">\<bindings></span></span>  
<span data-ttu-id="1439a-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1439a-106">\<customBinding></span></span>  
<span data-ttu-id="1439a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1439a-107">\<binding></span></span>  
<span data-ttu-id="1439a-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="1439a-108">\<peerTransport></span></span>  
<span data-ttu-id="1439a-109">\<security></span><span class="sxs-lookup"><span data-stu-id="1439a-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1439a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1439a-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1439a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1439a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1439a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1439a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1439a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1439a-113">Attributes</span></span>  
  
|<span data-ttu-id="1439a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1439a-114">Attribute</span></span>|<span data-ttu-id="1439a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1439a-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="1439a-116">Specifica il tipo di sicurezza da applicare.</span><span class="sxs-lookup"><span data-stu-id="1439a-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="1439a-117">Il valore predefinito è Message.</span><span class="sxs-lookup"><span data-stu-id="1439a-117">The default value is Message.</span></span> <span data-ttu-id="1439a-118">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="1439a-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1439a-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="1439a-119">mode Attribute</span></span>  
  
|<span data-ttu-id="1439a-120">Valore</span><span class="sxs-lookup"><span data-stu-id="1439a-120">Value</span></span>|<span data-ttu-id="1439a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1439a-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="1439a-122">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="1439a-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="1439a-123">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1439a-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="1439a-124">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="1439a-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="1439a-125">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="1439a-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="1439a-126">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="1439a-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1439a-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1439a-127">Child Elements</span></span>  
  
|<span data-ttu-id="1439a-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1439a-128">Element</span></span>|<span data-ttu-id="1439a-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1439a-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1439a-130">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="1439a-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="1439a-131">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1439a-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="1439a-132">Questo elemento presenta un attributo `clientCredentialType` che specifica le credenziali da usare quando si interagisce con un servizio.</span><span class="sxs-lookup"><span data-stu-id="1439a-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="1439a-133">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="1439a-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="1439a-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="1439a-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1439a-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1439a-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1439a-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="1439a-136">Element</span></span>|<span data-ttu-id="1439a-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1439a-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1439a-138">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="1439a-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="1439a-139">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1439a-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1439a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1439a-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="1439a-141">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="1439a-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="1439a-142">Trasporti</span><span class="sxs-lookup"><span data-stu-id="1439a-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="1439a-143">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="1439a-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="1439a-144">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1439a-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1439a-145">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1439a-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1439a-146">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1439a-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1439a-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1439a-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
