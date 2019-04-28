---
title: <transport> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 9b6f548515afbba5068659bd5c6f7f2b33f80cda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788284"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="47de5-102">\<Transport > di \<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="47de5-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="47de5-103">Specifica il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="47de5-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="47de5-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="47de5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="47de5-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="47de5-105">\<bindings></span></span>  
<span data-ttu-id="47de5-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="47de5-106">\<customBinding></span></span>  
<span data-ttu-id="47de5-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="47de5-107">\<binding></span></span>  
<span data-ttu-id="47de5-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="47de5-108">\<peerTransport></span></span>  
<span data-ttu-id="47de5-109">\<security></span><span class="sxs-lookup"><span data-stu-id="47de5-109">\<security></span></span>  
<span data-ttu-id="47de5-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="47de5-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47de5-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47de5-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47de5-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="47de5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="47de5-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="47de5-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47de5-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="47de5-114">Attributes</span></span>  
  
|<span data-ttu-id="47de5-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="47de5-115">Attribute</span></span>|<span data-ttu-id="47de5-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47de5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47de5-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="47de5-117">credentialType</span></span>|<span data-ttu-id="47de5-118">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="47de5-118">Optional.</span></span> <span data-ttu-id="47de5-119">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="47de5-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="47de5-120">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="47de5-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="47de5-121">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="47de5-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="47de5-122">Value</span><span class="sxs-lookup"><span data-stu-id="47de5-122">Value</span></span>|<span data-ttu-id="47de5-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47de5-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47de5-124">Certificato</span><span class="sxs-lookup"><span data-stu-id="47de5-124">Certificate</span></span>|<span data-ttu-id="47de5-125">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="47de5-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="47de5-126">Password</span><span class="sxs-lookup"><span data-stu-id="47de5-126">Password</span></span>|<span data-ttu-id="47de5-127">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="47de5-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47de5-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="47de5-128">Child Elements</span></span>  
 <span data-ttu-id="47de5-129">nessuno</span><span class="sxs-lookup"><span data-stu-id="47de5-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47de5-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="47de5-130">Parent Elements</span></span>  
  
|<span data-ttu-id="47de5-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="47de5-131">Element</span></span>|<span data-ttu-id="47de5-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47de5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47de5-133">\<security></span><span class="sxs-lookup"><span data-stu-id="47de5-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="47de5-134">Definisce le impostazioni di sicurezza di un trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="47de5-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47de5-135">Note</span><span class="sxs-lookup"><span data-stu-id="47de5-135">Remarks</span></span>  
 <span data-ttu-id="47de5-136">Questo elemento viene impostato solo se l'attributo mode di [ \<sicurezza >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) è impostata su `Transport` o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="47de5-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47de5-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47de5-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="47de5-138">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="47de5-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="47de5-139">Trasporti</span><span class="sxs-lookup"><span data-stu-id="47de5-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="47de5-140">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="47de5-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="47de5-141">Associazioni</span><span class="sxs-lookup"><span data-stu-id="47de5-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="47de5-142">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="47de5-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="47de5-143">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="47de5-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="47de5-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="47de5-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
