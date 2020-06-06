---
title: <transport> di <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399295"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="ce290-102">\<transport> di \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="ce290-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="ce290-103">Specifica il tipo di trasporto per messaggi protetti inviati dai peer configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="ce290-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="ce290-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce290-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce290-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ce290-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ce290-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ce290-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce290-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ce290-107">Attributes</span></span>  
  
|<span data-ttu-id="ce290-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ce290-108">Attribute</span></span>|<span data-ttu-id="ce290-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce290-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce290-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="ce290-110">credentialType</span></span>|<span data-ttu-id="ce290-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ce290-111">Optional.</span></span> <span data-ttu-id="ce290-112">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="ce290-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="ce290-113">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ce290-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="ce290-114">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="ce290-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="ce290-115">Valore</span><span class="sxs-lookup"><span data-stu-id="ce290-115">Value</span></span>|<span data-ttu-id="ce290-116">Description</span><span class="sxs-lookup"><span data-stu-id="ce290-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ce290-117">Certificato</span><span class="sxs-lookup"><span data-stu-id="ce290-117">Certificate</span></span>|<span data-ttu-id="ce290-118">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="ce290-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="ce290-119">Password</span><span class="sxs-lookup"><span data-stu-id="ce290-119">Password</span></span>|<span data-ttu-id="ce290-120">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="ce290-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce290-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ce290-121">Child Elements</span></span>  
 <span data-ttu-id="ce290-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="ce290-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce290-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ce290-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ce290-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce290-124">Element</span></span>|<span data-ttu-id="ce290-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce290-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="ce290-126">Definisce le impostazioni di sicurezza di un trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="ce290-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce290-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="ce290-127">Remarks</span></span>  
 <span data-ttu-id="ce290-128">Questo elemento viene impostato solo se l'attributo mode di [\<security>](security-of-peertransport.md) è impostato su `Transport` o `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="ce290-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce290-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ce290-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ce290-130">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="ce290-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="ce290-131">Trasporti</span><span class="sxs-lookup"><span data-stu-id="ce290-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="ce290-132">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="ce290-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ce290-133">Binding</span><span class="sxs-lookup"><span data-stu-id="ce290-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ce290-134">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="ce290-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ce290-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ce290-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
