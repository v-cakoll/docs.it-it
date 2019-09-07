---
title: <security> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399773"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="43307-102">\<> di sicurezza \<di peerTransport ></span><span class="sxs-lookup"><span data-stu-id="43307-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="43307-103">Contiene le impostazioni di sicurezza associate a un canale peer, compreso il tipo di autenticazione usato e la sicurezza applicata al trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="43307-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="43307-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43307-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43307-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="43307-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="43307-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="43307-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="43307-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="43307-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="43307-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="43307-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="43307-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> peerTransport**](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="43307-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="43307-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="43307-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43307-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43307-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43307-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="43307-112">Attributes and Elements</span></span>  
 <span data-ttu-id="43307-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="43307-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43307-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="43307-114">Attributes</span></span>  
  
|<span data-ttu-id="43307-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="43307-115">Attribute</span></span>|<span data-ttu-id="43307-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43307-116">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="43307-117">Specifica il tipo di sicurezza da applicare.</span><span class="sxs-lookup"><span data-stu-id="43307-117">Specifies the type of security to be applied.</span></span> <span data-ttu-id="43307-118">Il valore predefinito è Message.</span><span class="sxs-lookup"><span data-stu-id="43307-118">The default value is Message.</span></span> <span data-ttu-id="43307-119">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="43307-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="43307-120">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="43307-120">mode Attribute</span></span>  
  
|<span data-ttu-id="43307-121">Value</span><span class="sxs-lookup"><span data-stu-id="43307-121">Value</span></span>|<span data-ttu-id="43307-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43307-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="43307-123">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="43307-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="43307-124">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43307-124">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="43307-125">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="43307-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="43307-126">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="43307-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="43307-127">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="43307-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43307-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="43307-128">Child Elements</span></span>  
  
|<span data-ttu-id="43307-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="43307-129">Element</span></span>|<span data-ttu-id="43307-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43307-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43307-131">\<transport></span><span class="sxs-lookup"><span data-stu-id="43307-131">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="43307-132">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="43307-132">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="43307-133">Questo elemento presenta un attributo `clientCredentialType` che specifica le credenziali da usare quando si interagisce con un servizio.</span><span class="sxs-lookup"><span data-stu-id="43307-133">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="43307-134">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="43307-134">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="43307-135">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="43307-135">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43307-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="43307-136">Parent Elements</span></span>  
  
|<span data-ttu-id="43307-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="43307-137">Element</span></span>|<span data-ttu-id="43307-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43307-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43307-139">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="43307-139">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="43307-140">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="43307-140">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43307-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43307-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="43307-142">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="43307-142">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="43307-143">Trasporti</span><span class="sxs-lookup"><span data-stu-id="43307-143">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="43307-144">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="43307-144">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="43307-145">Associazioni</span><span class="sxs-lookup"><span data-stu-id="43307-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="43307-146">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="43307-146">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="43307-147">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="43307-147">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="43307-148">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="43307-148">\<customBinding></span></span>](custombinding.md)
