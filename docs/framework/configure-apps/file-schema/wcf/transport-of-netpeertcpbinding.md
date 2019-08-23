---
title: <transport> di <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915569"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="f79cd-102">\<> di trasporto \<di NetPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="f79cd-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="f79cd-103">Specifica le impostazioni per la [ \<](netpeertcpbinding.md)sicurezza a livello di trasporto quando si utilizza NetPeerTcpBinding >.</span><span class="sxs-lookup"><span data-stu-id="f79cd-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="f79cd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f79cd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f79cd-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="f79cd-105">\<bindings></span></span>  
<span data-ttu-id="f79cd-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="f79cd-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="f79cd-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f79cd-107">\<binding></span></span>  
<span data-ttu-id="f79cd-108">\<security></span><span class="sxs-lookup"><span data-stu-id="f79cd-108">\<security></span></span>  
<span data-ttu-id="f79cd-109">\<> di trasporto</span><span class="sxs-lookup"><span data-stu-id="f79cd-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f79cd-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f79cd-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f79cd-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f79cd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f79cd-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f79cd-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f79cd-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f79cd-113">Attributes</span></span>  
  
|<span data-ttu-id="f79cd-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="f79cd-114">Attribute</span></span>|<span data-ttu-id="f79cd-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f79cd-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f79cd-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="f79cd-116">credentialType</span></span>|<span data-ttu-id="f79cd-117">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f79cd-117">Optional.</span></span> <span data-ttu-id="f79cd-118">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="f79cd-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="f79cd-119">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f79cd-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="f79cd-120">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="f79cd-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="f79cd-121">Valore</span><span class="sxs-lookup"><span data-stu-id="f79cd-121">Value</span></span>|<span data-ttu-id="f79cd-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f79cd-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f79cd-123">Certificato</span><span class="sxs-lookup"><span data-stu-id="f79cd-123">Certificate</span></span>|<span data-ttu-id="f79cd-124">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="f79cd-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="f79cd-125">Password</span><span class="sxs-lookup"><span data-stu-id="f79cd-125">Password</span></span>|<span data-ttu-id="f79cd-126">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="f79cd-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f79cd-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f79cd-127">Child Elements</span></span>  
 <span data-ttu-id="f79cd-128">Nessuna</span><span class="sxs-lookup"><span data-stu-id="f79cd-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f79cd-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f79cd-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f79cd-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="f79cd-130">Element</span></span>|<span data-ttu-id="f79cd-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f79cd-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f79cd-132">\<security></span><span class="sxs-lookup"><span data-stu-id="f79cd-132">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="f79cd-133">Definisce le impostazioni di sicurezza per la [ \<> di NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f79cd-133">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f79cd-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f79cd-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="f79cd-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f79cd-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f79cd-136">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f79cd-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f79cd-137">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f79cd-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f79cd-138">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f79cd-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f79cd-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="f79cd-139">\<binding></span></span>](../../../misc/binding.md)
