---
title: <transport> di <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 08be5d752f8422ebe6442b295195f21b16a274c0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399322"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="91a46-102">\<> di trasporto \<di NetPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="91a46-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="91a46-103">Specifica le impostazioni per la [ \<](netpeertcpbinding.md)sicurezza a livello di trasporto quando si utilizza NetPeerTcpBinding >.</span><span class="sxs-lookup"><span data-stu-id="91a46-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="91a46-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91a46-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91a46-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="91a46-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="91a46-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="91a46-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="91a46-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netPeerTcpBinding**](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="91a46-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="91a46-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="91a46-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="91a46-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="91a46-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="91a46-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di trasporto**</span><span class="sxs-lookup"><span data-stu-id="91a46-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a46-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91a46-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91a46-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91a46-112">Attributes and Elements</span></span>  
 <span data-ttu-id="91a46-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91a46-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91a46-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="91a46-114">Attributes</span></span>  
  
|<span data-ttu-id="91a46-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="91a46-115">Attribute</span></span>|<span data-ttu-id="91a46-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a46-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91a46-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="91a46-117">credentialType</span></span>|<span data-ttu-id="91a46-118">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="91a46-118">Optional.</span></span> <span data-ttu-id="91a46-119">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="91a46-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="91a46-120">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="91a46-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="91a46-121">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="91a46-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="91a46-122">Value</span><span class="sxs-lookup"><span data-stu-id="91a46-122">Value</span></span>|<span data-ttu-id="91a46-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a46-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="91a46-124">Certificato</span><span class="sxs-lookup"><span data-stu-id="91a46-124">Certificate</span></span>|<span data-ttu-id="91a46-125">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="91a46-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="91a46-126">Password</span><span class="sxs-lookup"><span data-stu-id="91a46-126">Password</span></span>|<span data-ttu-id="91a46-127">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="91a46-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91a46-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91a46-128">Child Elements</span></span>  
 <span data-ttu-id="91a46-129">Nessuna</span><span class="sxs-lookup"><span data-stu-id="91a46-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91a46-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91a46-130">Parent Elements</span></span>  
  
|<span data-ttu-id="91a46-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="91a46-131">Element</span></span>|<span data-ttu-id="91a46-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91a46-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91a46-133">\<security></span><span class="sxs-lookup"><span data-stu-id="91a46-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="91a46-134">Definisce le impostazioni di sicurezza per la [ \<> di NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="91a46-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91a46-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91a46-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="91a46-136">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="91a46-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="91a46-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="91a46-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="91a46-138">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="91a46-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="91a46-139">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="91a46-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="91a46-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="91a46-140">\<binding></span></span>](../../../misc/binding.md)
