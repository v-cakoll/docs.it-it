---
title: <transport> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 5dbc55db25c0c49d72ec2cd8dd1041a3f8705d8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940640"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="5da4a-102">\<> di trasporto \<di peerTransport ></span><span class="sxs-lookup"><span data-stu-id="5da4a-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="5da4a-103">Specifica il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="5da4a-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="5da4a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5da4a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5da4a-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="5da4a-105">\<bindings></span></span>  
<span data-ttu-id="5da4a-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5da4a-106">\<customBinding></span></span>  
<span data-ttu-id="5da4a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5da4a-107">\<binding></span></span>  
<span data-ttu-id="5da4a-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="5da4a-108">\<peerTransport></span></span>  
<span data-ttu-id="5da4a-109">\<security></span><span class="sxs-lookup"><span data-stu-id="5da4a-109">\<security></span></span>  
<span data-ttu-id="5da4a-110">\<> di trasporto</span><span class="sxs-lookup"><span data-stu-id="5da4a-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5da4a-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5da4a-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5da4a-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5da4a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5da4a-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5da4a-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5da4a-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="5da4a-114">Attributes</span></span>  
  
|<span data-ttu-id="5da4a-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="5da4a-115">Attribute</span></span>|<span data-ttu-id="5da4a-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5da4a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5da4a-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="5da4a-117">credentialType</span></span>|<span data-ttu-id="5da4a-118">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5da4a-118">Optional.</span></span> <span data-ttu-id="5da4a-119">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="5da4a-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="5da4a-120">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5da4a-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="5da4a-121">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="5da4a-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="5da4a-122">Value</span><span class="sxs-lookup"><span data-stu-id="5da4a-122">Value</span></span>|<span data-ttu-id="5da4a-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5da4a-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5da4a-124">Certificato</span><span class="sxs-lookup"><span data-stu-id="5da4a-124">Certificate</span></span>|<span data-ttu-id="5da4a-125">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="5da4a-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="5da4a-126">Password</span><span class="sxs-lookup"><span data-stu-id="5da4a-126">Password</span></span>|<span data-ttu-id="5da4a-127">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="5da4a-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5da4a-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5da4a-128">Child Elements</span></span>  
 <span data-ttu-id="5da4a-129">Nessuna</span><span class="sxs-lookup"><span data-stu-id="5da4a-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5da4a-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5da4a-130">Parent Elements</span></span>  
  
|<span data-ttu-id="5da4a-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="5da4a-131">Element</span></span>|<span data-ttu-id="5da4a-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5da4a-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5da4a-133">\<security></span><span class="sxs-lookup"><span data-stu-id="5da4a-133">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="5da4a-134">Definisce le impostazioni di sicurezza di un trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="5da4a-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5da4a-135">Note</span><span class="sxs-lookup"><span data-stu-id="5da4a-135">Remarks</span></span>  
 <span data-ttu-id="5da4a-136">Questo elemento viene impostato solo se l'attributo mode del [ \<> di sicurezza](security-of-peertransport.md) è impostato `Transport` su `TransportWithMessageCredential`o su.</span><span class="sxs-lookup"><span data-stu-id="5da4a-136">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da4a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5da4a-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5da4a-138">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="5da4a-138">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="5da4a-139">Trasporti</span><span class="sxs-lookup"><span data-stu-id="5da4a-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="5da4a-140">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="5da4a-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="5da4a-141">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5da4a-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5da4a-142">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="5da4a-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5da4a-143">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5da4a-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5da4a-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5da4a-144">\<customBinding></span></span>](custombinding.md)
