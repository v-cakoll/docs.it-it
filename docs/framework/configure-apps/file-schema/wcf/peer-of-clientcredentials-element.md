---
title: <peer> di <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 8bdb52ccaaa8b41b3321447d2d68f9021a093481
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758352"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="b3c65-102">\<peer > di \<clientCredentials > elemento</span><span class="sxs-lookup"><span data-stu-id="b3c65-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="b3c65-103">Specifica le credenziali usate per l'autenticazione di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b3c65-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="b3c65-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b3c65-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b3c65-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b3c65-105">\<behaviors></span></span>  
<span data-ttu-id="b3c65-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b3c65-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="b3c65-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b3c65-107">\<behavior></span></span>  
<span data-ttu-id="b3c65-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b3c65-108">\<clientCredentials></span></span>  
<span data-ttu-id="b3c65-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="b3c65-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3c65-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3c65-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3c65-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b3c65-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b3c65-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b3c65-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3c65-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b3c65-113">Attributes</span></span>  
 <span data-ttu-id="b3c65-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b3c65-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b3c65-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b3c65-115">Child Elements</span></span>  
  
|<span data-ttu-id="b3c65-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3c65-116">Element</span></span>|<span data-ttu-id="b3c65-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3c65-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3c65-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="b3c65-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="b3c65-119">Specifica un certificato X.509 da usare per firmare e crittografare i messaggi di client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b3c65-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="b3c65-120">.</span><span class="sxs-lookup"><span data-stu-id="b3c65-120">.</span></span>|  
|[<span data-ttu-id="b3c65-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="b3c65-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="b3c65-122">Specifica le opzioni di autenticazione dei client peer.</span><span class="sxs-lookup"><span data-stu-id="b3c65-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="b3c65-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="b3c65-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="b3c65-124">Specifica le opzioni di autenticazione dei mittenti di messaggi.</span><span class="sxs-lookup"><span data-stu-id="b3c65-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3c65-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b3c65-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b3c65-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3c65-126">Element</span></span>|<span data-ttu-id="b3c65-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3c65-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3c65-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b3c65-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="b3c65-129">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="b3c65-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3c65-130">Note</span><span class="sxs-lookup"><span data-stu-id="b3c65-130">Remarks</span></span>  
 <span data-ttu-id="b3c65-131">Questo elemento di configurazione specifica le credenziali che un nodo peer usa per autenticare se stesso agli altri nodi della rete, nonché le impostazioni di autenticazione usate da un nodo peer per autenticare altri nodi peer.</span><span class="sxs-lookup"><span data-stu-id="b3c65-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="b3c65-132">Per altre informazioni, vedere [l'autenticazione dei messaggi del canale Peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) e [protezione di applicazioni del canale Peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="b3c65-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c65-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3c65-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="b3c65-134">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b3c65-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="b3c65-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="b3c65-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- <span data-ttu-id="b3c65-136">[Autenticazione dei messaggi del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b3c65-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="b3c65-137">[Autenticazione personalizzata del canale peer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b3c65-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="b3c65-138">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="b3c65-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="b3c65-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="b3c65-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
