---
title: <security> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399773"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="4f0f6-102">\<security> di \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="4f0f6-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="4f0f6-103">Contiene le impostazioni di sicurezza associate a un canale peer, compreso il tipo di autenticazione usato e la sicurezza applicata al trasporto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="4f0f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f0f6-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f0f6-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4f0f6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4f0f6-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f0f6-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f0f6-107">Attributes</span></span>  
  
|<span data-ttu-id="4f0f6-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4f0f6-108">Attribute</span></span>|<span data-ttu-id="4f0f6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f0f6-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="4f0f6-110">Specifica il tipo di sicurezza da applicare.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="4f0f6-111">Il valore predefinito è Message.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-111">The default value is Message.</span></span> <span data-ttu-id="4f0f6-112">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4f0f6-113">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="4f0f6-113">mode Attribute</span></span>  
  
|<span data-ttu-id="4f0f6-114">Valore</span><span class="sxs-lookup"><span data-stu-id="4f0f6-114">Value</span></span>|<span data-ttu-id="4f0f6-115">Description</span><span class="sxs-lookup"><span data-stu-id="4f0f6-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4f0f6-116">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="4f0f6-117">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="4f0f6-118">La sicurezza SOAP fornisce autenticazione, integrità e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="4f0f6-119">HTTPS fornisce autenticazione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="4f0f6-120">I messaggi SOAP forniscono tipi di credenziale dettagliati.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f0f6-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4f0f6-121">Child Elements</span></span>  
  
|<span data-ttu-id="4f0f6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f0f6-122">Element</span></span>|<span data-ttu-id="4f0f6-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f0f6-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="4f0f6-124">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="4f0f6-125">Questo elemento presenta un attributo `clientCredentialType` che specifica le credenziali da usare quando si interagisce con un servizio.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="4f0f6-126">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="4f0f6-127">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f0f6-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4f0f6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="4f0f6-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f0f6-129">Element</span></span>|<span data-ttu-id="4f0f6-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f0f6-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="4f0f6-131">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4f0f6-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f0f6-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4f0f6-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4f0f6-133">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="4f0f6-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="4f0f6-134">Trasporti</span><span class="sxs-lookup"><span data-stu-id="4f0f6-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="4f0f6-135">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="4f0f6-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4f0f6-136">Binding</span><span class="sxs-lookup"><span data-stu-id="4f0f6-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4f0f6-137">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4f0f6-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4f0f6-138">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4f0f6-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
