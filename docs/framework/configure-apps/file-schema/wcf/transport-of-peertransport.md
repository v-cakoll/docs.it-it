---
title: <transport> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399295"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="8825c-102">\<> di trasporto \<di peerTransport ></span><span class="sxs-lookup"><span data-stu-id="8825c-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="8825c-103">Specifica il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="8825c-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
<span data-ttu-id="8825c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8825c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8825c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8825c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8825c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8825c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8825c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8825c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8825c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="8825c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8825c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> peerTransport**](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="8825c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="8825c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="8825c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)</span></span>\
<span data-ttu-id="8825c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di trasporto**</span><span class="sxs-lookup"><span data-stu-id="8825c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8825c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8825c-112">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8825c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8825c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8825c-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8825c-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8825c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="8825c-115">Attributes</span></span>  
  
|<span data-ttu-id="8825c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="8825c-116">Attribute</span></span>|<span data-ttu-id="8825c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8825c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8825c-118">credentialType</span><span class="sxs-lookup"><span data-stu-id="8825c-118">credentialType</span></span>|<span data-ttu-id="8825c-119">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8825c-119">Optional.</span></span> <span data-ttu-id="8825c-120">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="8825c-120">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="8825c-121">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8825c-121">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="8825c-122">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="8825c-122">credentialType Attribute</span></span>  
  
|<span data-ttu-id="8825c-123">Value</span><span class="sxs-lookup"><span data-stu-id="8825c-123">Value</span></span>|<span data-ttu-id="8825c-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8825c-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8825c-125">Certificato</span><span class="sxs-lookup"><span data-stu-id="8825c-125">Certificate</span></span>|<span data-ttu-id="8825c-126">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="8825c-126">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="8825c-127">Password</span><span class="sxs-lookup"><span data-stu-id="8825c-127">Password</span></span>|<span data-ttu-id="8825c-128">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="8825c-128">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8825c-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8825c-129">Child Elements</span></span>  
 <span data-ttu-id="8825c-130">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8825c-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8825c-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8825c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8825c-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="8825c-132">Element</span></span>|<span data-ttu-id="8825c-133">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8825c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8825c-134">\<security></span><span class="sxs-lookup"><span data-stu-id="8825c-134">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="8825c-135">Definisce le impostazioni di sicurezza di un trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="8825c-135">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8825c-136">Note</span><span class="sxs-lookup"><span data-stu-id="8825c-136">Remarks</span></span>  
 <span data-ttu-id="8825c-137">Questo elemento viene impostato solo se l'attributo mode del [ \<> di sicurezza](security-of-peertransport.md) è impostato `Transport` su `TransportWithMessageCredential`o su.</span><span class="sxs-lookup"><span data-stu-id="8825c-137">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8825c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8825c-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8825c-139">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="8825c-139">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="8825c-140">Trasporti</span><span class="sxs-lookup"><span data-stu-id="8825c-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="8825c-141">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="8825c-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="8825c-142">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8825c-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8825c-143">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="8825c-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8825c-144">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8825c-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8825c-145">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8825c-145">\<customBinding></span></span>](custombinding.md)
